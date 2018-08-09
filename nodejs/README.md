# Nodejs

## How to install node.js

[Nodejs - Mac(OSX)에 nodejs를 설치하는 최고의 방법](http://hochulshin.com/node-install-osx/)

brew 이용하여 npm 없이 node 설치한 후 `PATH` 추가한 이후 `npm` 설치함.

```shell
$ brew install node --without-npm
$ export PATH="/usr/local/Cellar/node/0.12.7/bin:$PATH"
$ . .bash_profile
$ curl -L https://www.npmjs.com/install.sh | sh
```

## `npm start` using `pm2`

[node.js - Can pm2 run an 'npm start' script - Stack Overflow](https://stackoverflow.com/questions/31579509/can-pm2-run-an-npm-start-script)

```bash
$ pm2 start npm -- start
```

## `forever`

```bash
$ forever start script
$ forever stop script
$ forever ls
$ forever stop 0
$ forever stopall
```
