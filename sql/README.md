# SQL

## MySQL

### Mac에서 mysql8.0 사용 시 원걱 허용

- [OS X에서 MySQL을 잘못 설치했을 때 다시 설치하는 방법 · Issue #4 · appkr/l5code](https://github.com/appkr/l5code/issues/4)
- [맥에서 mysql 설치 후 환경설정하기 · helloheesu/SecretlyGreatly Wiki](https://github.com/helloheesu/SecretlyGreatly/wiki/%EB%A7%A5%EC%97%90%EC%84%9C-mysql-%EC%84%A4%EC%B9%98-%ED%9B%84-%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)

```bash
// Remove
brew services stop mysql
rm -rf /usr/local/var/mysql
brew uninstall mysql

// Install
brew install mysql
brew services start mysql
mysql -uroot

// Secure config
mysql_secure_installation
...
// allow remote
```

MySQL 8.0 에서는 `mysql_native_password` 로 써야 한다. 이걸로 무지 고생함. T_T;

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'MyNewPass';
```
