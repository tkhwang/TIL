# PCAP

## Convert from `.pcapng` to `.pcap`

[Wireshark: converting pcapng to pcap](http://seclists.org/wireshark/2012/Sep/269)

```shell
$ editcap -F libpcap -T ether package.pcapng package.pcap
```
