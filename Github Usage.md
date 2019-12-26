#  Github Usage

## (1) Git으로 프로젝트 관리 : `git init`
```shell
$ git init
```

## (2) Commit : `git add`
- 현재 코드 상태의 스냅샷을 찍는다
```shell
$ git add [파일이름]
```

## (3) 저장 : `git commit`
- 현재 상태에 대한 스냅샷을 `commit`
```shell
$ git commit -m 'message'
```

## (4) 원격 저장소 연결 : `git remote`
- Github 원격(remote) 저장소(repository) 를 생성하고 저장 폴더와 연결.
- 처음 한번만 입력
```shell
$ git remote add origin [github 저장소 주소]
```

## (5) 원격 저장소에 저장 :  `git push`
- 최종적으로 저장
```shell
$ git push origin master
```

## (6) 그 외 명령어
- 현재 `git`의 상태를 조회 `git status`
```shell
$ git status
```
- 버전 관리 이력 조회
```shell
$ git log
```
- `git` 설정(user.name & user.email) : **최초 1회 설정**
```shell
$ git config --global user.name "name"
$ git config --global user.email "your@email.com"
```

## README.md
> 원격(remote) 저장소(repository)에 대한 정보를 기록하는 마크다운 문서. 일반적으로 해당 프로젝트를 사용 하기 위한 방법 등을 기재한다.

## (1) `README.md` 파일 생성
- `README.md` 파일을 폴더 최상단에 생성.
```shell
$ touch README.md
```

## (2) 버전관리 : `add`, `commit`, `push`
- 작성 한 뒤, commit 이력을 남기고 원격 저장소로 push한다.
```shell
$ git add README.md
$ git commit -m 'add README.md'
$ git push origin master
```

## Branch 관리
- 종류
    - Master Branch
    배포(Release) 이력을 관리하기 위해 사용. 배포 가능한 상태만 관리
    - Develop Branch
    다음 출시 버전을 개발하는 브랜치 배포 가능하다 판단되면 Master Branch에 Merge 
    - Feature Brance
    기능을 개발하는 브랜치, Develop Branch로부터 분기된것 완료되면 develop Branch에 Merge한다.
    ```shell
    // feature 브랜치(feature/login)를 'develop' 브랜치('master' 브랜치에서 따는 것이 아니다!)에서 분기
    $ git checkout -b feature/login develop

    /* ~ 새로운 기능에 대한 작업 수행 ~ */

    /* feature 브랜치에서 모든 작업이 끝나면 */
    // 'develop' 브랜치로 이동한다.
    $ git checkout develop
    // 'develop' 브랜치에 feature/login 브랜치 내용을 병합(merge)한다.
    # --no-ff 옵션: 아래에 추가 설명
    $ git merge --no-ff feature/login
    // -d 옵션: feature/login에 해당하는 브랜치를 삭제한다.
    $ git branch -d feature/login
    // 'develop' 브랜치를 원격 중앙 저장소에 올린다.
    $ git push origin develop
    https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html
    ```
    - Release Branch
    
    - Hotfix Branch
