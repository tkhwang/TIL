# Standard C Library

##  `setvbuf`

```
int setvbuf ( FILE * stream, char * buffer, int mode, size_t size );
```

- stream : 작업을 수행할 열린 스트림의 FILE 객체를 가리키는 포인터. 
- buffer : 유저가 할당한 버퍼로 최소한 1 바이트의 크기는 되야 한다.  만일 NULL 로 설정하면 함수는 자동으로 지정한 크기의 버퍼를 할당하게 된다
- mode : 파일 버퍼링의 형식을 지정한다.

```
_IOFBF  완전한 버퍼링(Full Buffering): 앞에서 설명한 fully buffered 스트림을 일컫는다. 
_IOLBF  행 버퍼링(Line Buffering): 출력시, 버퍼가 채워지거나 스트림에 개행 문자가 입력되었다면 데이터가 버퍼에서 출력된다. 입력 시에는 버퍼가 개행 문자를 만날 때 까지 버퍼를 채우게 된다. 
_IONBF  버퍼링 사용 안함(No Buffering): 버퍼를 사용하지 않는다. 각각의 입출력 작업은 버퍼를 지나지 않고 요청 즉시 진행되며 이 겨우 buffer 인자와 size 인자는 모두 무시된다. 
```

- size : 지정할 버퍼의 크기로 단위는 바이트 이다. 이 때, 버퍼로 지정한 배열의 크기 보다 반드시 작거나 같아야 한다.  만일 이 인자가 NULL 이라면 컴퓨터가 스스로 버퍼가 취할 수 있는 최소의 크기를 결정하게 된다. 

### Example 

```c
int __cdecl main(int argc, const char **argv, const char **envp)
{
  char s; // [sp+8h] [bp-20h]@7
  FILE *stream; // [sp+18h] [bp-10h]@1
  char *v6; // [sp+1Ch] [bp-Ch]@1

  setvbuf(stdin, 0, 2, 0);
  setvbuf(stdout, 0, 2, 0);
  setvbuf(_bss_start, 0, 2, 0);
...
```
