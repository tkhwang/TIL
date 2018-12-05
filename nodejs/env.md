# 환경 변수 이용

## Node.js

### `dotenv` package

```bash
npm install dotenv --save
```

### 환경 변수 저장

#### 1. `.env`

```
APP_ACCESS_KEY=...
APP_SECRET=...
CALLBACK_URL=...
```

#### 2. 환경변수

```bash
$ export APP_ACCESS_KEY="..." npm start
```

### How to use

```javascript
require('dotenv').config();
...
process.env.APP_ACCESS_KEY
process.env.APP_SECRET=...
process.env.CALLBACK_URL=...
```

## React

최신 `create-react-app` 에서는 `env`를 기본으로 제공함.

#### 1. `.env`

```
REACT_APP_APP_ACCESS_KEY=...
REACT_APP_APP_SECRET=...
REACT_APP_CALLBACK_URL=...
```

### How to use.

```javascript
process.env.REACT_APP_APP_ACCESS_KEY
process.env.REACT_APP_APP_SECRET=...
process.env.REACT_APP_CALLBACK_URL=...
```
