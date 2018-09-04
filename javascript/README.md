# Javascript

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

# AJAX (Asynchronous Javascript and XML)

```javascript
var xhr = new XMLHttpReques();
```
