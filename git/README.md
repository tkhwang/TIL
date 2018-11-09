# git command

## Basic command

### Branch

생성

```bash
git checkout -b BRANCH_NAME

//OR

git branch BRANCH_NAME
git checkout BRANCH_NAME
```

로컬 브랜치 삭제

```bash
git branch -d BRANCH_NAME
```

원격 브랜치 삭제

```bash
git push origin --delete BRANCH

// OR

git branch -d BRANCH_NAME
git push origin BRANCH_NAME
```

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

## Fork 한 github source 원래 소스와 sync 하기

[[Tip] Fork한 Github 소스 원래 소스와 싱크 하기 – Not for Me](http://www.notforme.kr/archives/1631)

- pull : update 한 이후 merge 까지 자동 수행
- fetch : just get update

```bash
// Upstream remote repository 설정하기
$ git remote add upstream https://github.com/XXX

// Fetch from upstream
$ git fetch upstream

// Merge to master
$ git checkout master
$ git merge upstream/master
```

## self-signed certifcate

[version control - How can I make git accept a self signed certificate? - Stack Overflow](http://stackoverflow.com/questions/11621768/how-can-i-make-git-accept-a-self-signed-certificate)

```bash
$ git -c http.sslVerify=false clone https://domain.com/path/to/git
git config http.sslVerify false
```
