# GO Language

```go
변수명 타입

a := 1  // 변수 선언과 동시에 대입
```

## array

```go
var a [5]int

var a [5]int = [5]int{1,2,3,4,5}   // 초기값을 { , ... } 에 넣어준다.
a := [5]int{1,2,3,4,5}
```

## slice

- array 와 비슷하지만 길이가 고정되어 있지 않으며 **동적으로 크기가 늘어난다.**
- 배열과 달리 **레퍼런스 타입**.
- `make([]type, size)` 함수 사용하여 공간을 할당해야 값을 넣을 수 있음.
- 레퍼런스 타입임. 내장된 배열에 대한 포인터이므로 슬라이스끼리 대입하면 값이 복사되지 않고 참조 (레퍼런스)만 한다.

```go
var a []int   // 배열과 달리 [] 안에 길이를 지정하지 않는다.
```

### `make([]type, 길이, 용량)`

```go
var a []int = make([]int, 5)
var b = make([]int, 5)
```

### `append(slice, value1, value2, value3, ...)`

```go
a := []int{1,2,3}
a = append(a, 4, 5, 6)
```

## map

- Map, dictionary, hash table
- 레퍼런스 타입
-

```go
map[key]value
var a map[string]int

solarSystem := make(map[string]float32)
value, ok := solarSystem

// key validity check
if value, ok := solarSystem["Saturn"]; ok {
  fmt.Println(value)
}

// map 순회 => key, value
for key, value := range solarSystem {
  fmt.Println(key, value)
}

// map 삭제
a := map[string]int{"Hello": 10, "world": 20}
delete(a, "world")
fmt.Println(a)    // map[Hello:10]
```

## Function

- 가변인수 : 자료형 앞에 ... 붙여서 가변인자 지정.
  - 가변인자로 받은 변수 : 슬라이스 타입 => `range` 키워드를 사용하여 값을 꺼내어 사용.

```go
func funcName(매개변수명 자료형) 리턴값_자료형 {}

// 가변인수 : 자료형 앞에 ... 붙여서 가변인자 지정.
func sum(n ...int) int {
  total := 0
  for _, value := range n {
    total += value
  }
}
```

## Pointer

- 자료형 앞에 `*` 붙임.
- 포인터형 변수를 선언하면 `nil`으로 초화화됨. (nil 은 0 아님.
- **허용하지 않는 오퍼레이션**
  - 메모리 주소를 직접 대입
  - 포인터 연산

```go
var numPrt *int = new(int

var num int = 1
var numPrt *it = &num
```

## Structure

```go
type Rectangle struct {
  width int
  height int
}
```

### Receiver : 구조체에 메서드 연결

- 구조체 인스턴스의 값을 변경하는 경우 : 포인터 형태
- 그렇지 않은 경우 : 값 형태

```go
func (rect *Rectangle) area() int {
  return rect.width * rect.height
}
```

### 구조체 임베딩 => 상속처럼 이용

- Structure in structure => embedding
- `ls-a` 관계

## Interface

- 인페페이스 : 메서스 집합
- 메서드 자체를 구현하지는 않음.
- 다른 자료형과 동일하게 함수의 매개변수, 리턴값, 구조체의 필드로 사용 가능함.

```go
type interfaceName interface {
```

## Command option

```bash
$ go get -t

The -t flag instructs get to also download the packages required to build
the tests for the specified packages.

The -u flag instructs get to use the network to update the named packages
and their dependencies. By default, get uses the network to check out
missing packages but does not use it to look for updates to existing packages.
```
