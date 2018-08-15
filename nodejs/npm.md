# npm

## `npm audit`

```bash
$ npm audit
$ npm audit fix
```

## `n` utility

`node` 버전 관리를 위한 utility

```bash
$ npm install -g n
$ n ls
$ sudo n lts
$ sudo n latest
```

## npm `--save` 와 `--save-dev` 차이점

### `npm install module`

그냥 install 하면 ./node_modules 디렉터리에 패키지 설치를 하고 끝.

### `--save`, `--save-dev`

`--save`, `--save-dev` 옵션은 `./package.json` 업데이트를 같이해준다.

- `--save` : dependencies object 에 추가
  - `npm install` 시 항상 설치
- `--save-dev` : devDepenencies object 에 추가
  - `npm install --production` 옵션을 붙이면 빠진다.
  - `npm install package --dev` 옵션 붙여야 설치.
