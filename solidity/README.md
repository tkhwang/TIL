# Solidity

[이더리움 솔리디티 실습 튜토리얼 | 프로그래머스](https://programmers.co.kr/learn/courses/36)내용 정리

## 문법

### Transfer

```
<받는 사람의 주소>.transfer(<송금할 금액>);
```

```solidity
function buy() public {
    seller.transfer(10)
}
```

### Transaction

```
트랜잭션이 담은 정보
transactionHash : 트랜잭션의 해시값
transactionIndex : 트랜잭션의 인덱스 값
blockHash : 이 트랜잭션이 추가된 블록의 해시값
blockNumber : 이 트랜잭션이 추가된 블록의 번호
gasUsed : 이 트랜잭션 호출에 소비한 가스양
cumulativeGasUsed : 누적으로 사용된 가스량
contractAddress : 계약의 주소
logs : event로 로깅된 정보 ( 후속 강의로 다룰 예정 )
```

### 접근 제어자

- public 접근 제어자
- internal 접근 제어자
- private 접근 제어자
- external 접근 제어자

### 가스비 절약

#### `View` 함수

- 상태를 변경하지 않습니다: 블록체인 네트워크 상의 데이터를 읽기만 할 수 있고 데이터를 수정할 수 없습니다.
- 가스를 소모하지 않습니다: 호출할 때 Gas 를 사용하지 않습니다.

#### `pure` 함수

상태변수가 아닌 pure function 으로 구현.

- 블록체인 네트워크에 기록된 데이터에 아예 접근하지 않습니다.
- 파라미터로 주어지지 않은 상태 변수는 읽거나 쓸 수 없습니다.

(Q) Functin parameter의 값이 state variable일 수는 없는가 ?

### Event

- 계약이 수행된 정보는 트랜잭션으로 남습니다. 
- 이벤트 안에 명시된 데이터를 트랜젝션에 로깅.
- indexed 키워드가 붙은 데이터는 log 검색 시 사용할 수 있음.



