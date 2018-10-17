# Javascript

## Random

[Basic JavaScript: Generate Random Whole Numbers within a Range | Learn freeCodeCamp](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/basic-javascript/generate-random-whole-numbers-within-a-range/)

```javascript
Math.floor(Math.random() * (max - min + 1)) + min;
```

## Object

- 객체는 키 (식별자 또는 문자열)와 값(속성)으로 이루어짐.
- `{}` 중괄호로 객체 생성.
- 객체의 속성 값에 접근할 때 키로 접근
- 객체의 키로 식별자가 아닌 문자로 사용했을 때는 무조건 대괄호를 사용하여 접근

```javascript
> obj = { a: 1, b: 2 }
{ a: 1, b: 2 }
> obj
{ a: 1, b: 2 }
> obj.a
1
> obj.b
2
> obj['a']
1
> obj['b']
2
```

## Sort Object

### Object 의 key property 에 따라서 sort 하기

- key 로 sort 한 이후에 이에 따라서 새로 object 를 만들어서 return 해야 한다.

[Session 10 - Recursion | Code States](https://learn.codestates.com/courses/386527/lectures/5894776)

```javascript
function sortObject(obj) {
  return Object.keys(obj)
    .sort()
    .reduce(function(result, key) {
      result[key] = obj[key];
      return result;
    }, {});
}
```

### Object 의 property value 값에 따라서 sort 하기

[javascript - How to sort objects by value - Stack Overflow](https://stackoverflow.com/questions/43773092/how-to-sort-objects-by-value)

```javascript
let obj = { a: 24, b: 12, c: 21, d: 15 };

// Get an array of the keys:
let keys = Object.keys(obj);

// Then sort by using the keys to lookup the values in the original object:
keys.sort(function(a, b) {
  return obj[a] - obj[b];
});

console.log(keys);

["b", "d", "c", "a"];
```

[Sorting JavaScript Object by property value - Stack Overflow](https://stackoverflow.com/questions/1069666/sorting-javascript-object-by-property-value)

```javascript
var maxSpeed = {
  car: 300,
  bike: 60,
  motorbike: 200,
  airplane: 1000,
  helicopter: 400,
  rocket: 8 * 60 * 60
};
var sortable = [];
for (var vehicle in maxSpeed) {
  sortable.push([vehicle, maxSpeed[vehicle]]);
}

sortable.sort(function(a, b) {
  return a[1] - b[1];
});

//[["bike", 60], ["motorbike", 200], ["car", 300],
//["helicopter", 400], ["airplane", 1000], ["rocket", 28800]]
```

## 원본 그대로 vs 연산 결과 사용

- 원본 그대로
  - `unshift()`
  - `shift()`
- 연산 결과 사용
  ```javascript
  var new_str = str.toUpperCase();
  return new_str;
  ```

## Closure

```javascript
function makeIncreaseByFunction(increaseByAmount) {
  return function(numberToIncrease) {
    return numberToIncrease + increaseByAmount;
  };
}

var increaseBy3 = makeIncreaseByFunction(3);
var increaseBy5 = makeIncreaseByFunction(5);

increaseBy3(10) + increaseBy5(10) = ?
```

#### Closure 활용 예

```javascript
var getCompletedStr = (function() {
  var buffAr = ["I am ", "", " I live in ", "", "I 'am ", "", " years old"];

  return function(name, city, age) {
    buffAr[1] = name;
    buffAr[3] = city;
    buffAr[5] = age;

    return buffAr.join("");
  };
})();

var str = getCompletedStr("zzoon", "seoul", 16);
console.log(str);
```

#### Stage1

```javascript
var increaseBy3 = makeIncreaseByFunction(3)
  = return function(numberToIncrease) {
    return numberToIncrease + 3;
  };
```

`increaseBy3` 는 `numberToIncrease` local variable 가지고 있는 closure 가 된다.

이를 `increaseBy3(10)` 으로 실행을 시키면

```javascript
increaseBy3(10)
increaseBy3(10) = makeIncreaseByFunction(3)(10) = 13;
```

## Promise

```javascript
// Define
const condition = true;
const promise = new Promise((resolve, reject) => {
  if (condition) {
    resolve("success");
  } else {
    reject("fail");
  }
});

// Use
promise
  .then(message => {
    // Success
    console.log(message);
  })
  .catch(error => {
    // Fail
    console.error(error);
  });
```

## Promise chainning

[Example for how to chain multiple requests? · Issue #708 · axios/axios](https://github.com/axios/axios/issues/708)

```javascript
axios.get(...)
  .then((response) => {
    return axios.get(...); // using response.data
  })
  .then((response) => {
    console.log('Response', response);
  });
```

## Promise.all

Promise 가 여러 개 있을 때 `promise.all`에 넣으면 모두 resolve 될 때까지 기다렸다가 then 으로 넘어갑니다.

```javascript
const promise1 = Promise.resolve('success1');
const promise2 = Promise.resolve('success2');
Promise.all([promise1, promise2])
.then((result) => {
    console.log(result);
})
.catch((error) => {
    console.error(error);
}
```

## Async / await

### Promise version

```
function findAndSaveUser(Users) {
    User.findOne({
        .then((user) => {
            user.name = 'zero';
            return user.save();
        })
        .then((user) => {
            return Users.findOne({ gender: 'm' });
        })
        .then((user) => {
            // ...
        })
        .catch((err => {
            console.error(err;
        }));
}
```

### async/await version

- `function` 대신에 `async function` 사용.
- `promise` 앞에 `await` 사용 ==> 해당 promise 가 resolve 될때까지 기다린 뒤 다음 로직으로 넘어감.

```javascript
async function findAndSaveUser (Users {
    let user = await Users.findOne({;
    user.name = 'zero';
    user = await user.save();
    user = wait Users.findOne({ gender: 'm' });
    // ...
}
```

## `Math.max()`

`array[]` 에 대한 `Math.max()` 사용의 경우

```javascript
let arr = [1, 2, 3, 4, 5];
```

- array 가 직접 올 수 없음.

```javascript
console.log(Math.max(arr));
NaN;
```

- 전개 연산자 이용할 것.

```javascript
console.log(Math.max(...arr));
5;
```

- `Math.max.apply(null, arr)` 이용할 것.

```javascript
console.log(Math.max.apply(null, arr));
5;
```

## Number

#### Number 의 length  구하기.

[jquery - Length of Number in JavaScript - Stack Overflow](https://stackoverflow.com/questions/10952615/length-of-number-in-javascript)

Array 와 달리 `.length` property 가 없다. `.toString()` 한 이후에 이용 할 수 있음.

```javascript
n.toString().length
```

## Covert

#### Decimal ==> Binary

```javascript
// number.toString(2)

// 11..toString(2) // '1011'
(11).toString(2); // '1011'
"11".toString(2); // '11'
```

## Padding algorithm

```javascript
var n = 123;

String("00000" + n).slice(-5); // returns 00123
String("00000" + n).slice(-5); // returns 00123
String("     " + n).slice(-5); // returns "  123" (with two spaces)
```
