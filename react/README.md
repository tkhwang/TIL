# React

## Basic

### `React.renderROM()`

```javascirpt
ReactDOM.render(

);
```

### `React.createElement()`

```javascript
```

## Component life-cycle

- `componentWillMount()`
  - `render()` 직전에 불림.
- `componentDidmount()`
  - component가 DOM 에 mount 직후 => `this` 사용 가능함. (`this.state`)
  - Preparation for API usage.
- `componentWillReceiveProps()`
  - `props` update 시
  - `nextProps` 와 `this.props` 비교.
- `componentDidUpdate()`
  - component re-render 한 직후에 불림.

## Counter example

[Redux: Write a Counter with Redux | Learn freeCodeCamp](https://learn.freecodecamp.org/front-end-libraries/redux/write-a-counter-with-redux)

```javascript
const INCREMENT = "INCREMENT";
const DECREMENT = "DECREMENT";

const counterReducer = (state = 0, action) => {
  switch (action.type) {
    case INCREMENT:
      return state + 1;
    case DECREMENT:
      return state - 1;
    default:
      return state;
  }
};

const incAction = () => {
  return {
    type: INCREMENT
  };
};

const decAction = () => {
  return {
    type: DECREMENT
  };
};

const store = Redux.createStore(counterReducer);
```
