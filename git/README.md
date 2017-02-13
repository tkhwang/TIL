# git command

## `remote set-url`

- git remote repository configuration 확인

```bash
$ git remote -v
# View existing remotes
origin  https://github.com/user/repo.git (fetch)
origin  https://github.com/user/repo.git (push)
```

- remote repository 이름이 변경이 되어 이에 따라서 `git remote set-url` 로 `origin` 변경

```bash
$ git remote set-url origin https://github.com/user/repo2.git
# Change the 'origin' remote's URL
```


## self-signed certifcate

[version control - How can I make git accept a self signed certificate? - Stack Overflow](http://stackoverflow.com/questions/11621768/how-can-i-make-git-accept-a-self-signed-certificate)

```bash
$ git -c http.sslVerify=false clone https://domain.com/path/to/git
git config http.sslVerify false
```

