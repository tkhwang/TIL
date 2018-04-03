# Javascript

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
