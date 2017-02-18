# openssl

OpenSSL은 SSL과 TLS 프로토콜과 각종 암호화 라이브러리를 구현한 오픈소스 툴킷



[DER vs. CRT vs. CER vs. PEM Certificates and How To Convert Them](http://info.ssl.com/article.aspx?id=12149)


At its core an X.509 certificate is a digital document that has been encoded and/or digitally signed according to RFC 5280.

In fact, the term X.509 certificate usually refers to the IETF’s PKIX Certificate and CRL Profile of the X.509 v3 certificate standard, as specified in RFC 5280, commonly referred to as PKIX for Public Key Infrastructure (X.509).

## X509 File Extensions

- The first thing we have to understand is what each type of file extension is.   
- There is a lot of confusion about what DER, PEM, CRT, and CER are and many have incorrectly said that they are all interchangeable.  
- While in certain cases some can be interchanged the best practice is to identify how your certificate is encoded and then label it correctly.  
- Correctly labeled certificates will be much easier to manipulat

## Encodings (also used as extensions)

.DER = The DER extension is used for binary DER encoded certificates. These files may also bear the CER or the CRT extension.   Proper English usage would be “I have a DER encoded certificate” not “I have a DER certificate”.
.PEM = The PEM extension is used for different types of X.509v3 files which contain ASCII (Base64) armored data prefixed with a “—– BEGIN …” line.
Common Extensions

.CRT = The CRT extension is used for certificates. The certificates may be encoded as binary DER or as ASCII PEM. The CER and CRT extensions are nearly synonymous.  Most common among *nix systems
CER = alternate form of .crt (Microsoft Convention) You can use MS to convert .crt to .cer (.both DER encoded .cer, or base64[PEM] encoded .cer)  The .cer file extension is also recognized by IE as a command to run a MS cryptoAPI command (specifically rundll32.exe cryptext.dll,CryptExtOpenCER) which displays a dialogue for importing and/or viewing certificate contents.
.KEY = The KEY extension is used both for public and private PKCS#8 keys. The keys may be encoded as binary DER or as ASCII PEM.
The only time CRT and CER can safely be interchanged is when the encoding type can be identical.  (ie  PEM encoded CRT = PEM encoded CER)




## Certificate

X.509 표준을 준수하는 인증서는 다음과 같은 데이타와 서명(signature) 영역을 가지고 있음.

- **공개키 그 자체**
- 공개키를 소유하고 있는 자의 구별 가능한 이름 
- 공개키를 발급(issue)한 자의 구별 가능한 이름 
- 이 인증서가 언제까지 유효한지를 나타내는 유효기간 


## Format

### PEM(Privacy-enhanced Electronic Mail) 

```bash
$ openssl x509 -in ca.crt -text   
```


- 인증기관에서 가장 많이 사용하는 포맷
- PEM 인증서는 보통 `.pem`, `.crt`, `.cer`, `.key` 와 같은 확장자
- Base64로 인코딩된 ASCII 텍스트 파일

```
------BEGIN CERTIFICATE----

----END CERTIFICATE----
```

### DER(Distinguished Encoding Rules) 

```bash
$ openssl x509 -in ca.der -inform DER -text 
```

- PEM과 달리 바이너리 포맷입니다. 확장자는 주로 `.der`이 쓰이지만 종종 `.cer`로 쓰이는 경우도 있습니다. 
- 그러므로 `.cer` 확장자를 보면 편집기로 열어 보아야 PEM 포맷인지 DER 포맷인지 알 수 있습니다. 
- DER은 주로 Java 플랫폼에서 쓰입니다. 


## PKCS#12(Public Key Cryptography Standards #12)

- 보통 .`pfx`, `.p12` 등의 확장자로 저장됨. 
- 바이너리 형식으로 저장되며 pkcs#12 포멧의 파일은 인증서, 개인키 내용을 파일하나에 모두 담고 있습니다. 
- 백업 또는 이동용으로 주로 사용됩니다. 




 