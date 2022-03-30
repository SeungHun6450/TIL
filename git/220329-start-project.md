# Git 초기 설정

`git config --list` : 확인
`git config --global user.name ""`
`git config --global user.email ""`
`git config --global core.editor "vim"`
`git config --global core.pager "cat"`
삭제 시  명령어
`git config --global --unset`

이후
git clone 깃주소 를 입력하고 ls를 눌러보면 해당 깃 주소에 등록된 파일들이 불러와진다

## 파일 수정 후

1. `git status` - > 변경 사항이 있으면 Changes not staged for commit이 뜬다.
**git status는 각 구간 마다 한 번씩 사용하여 확인하는 습관을 들이자.**
로컬 저장소로 올리기전의 대기장소 : stage
2. `git add 파일명` : 변경 사항을 등록한다.
3. `git commit` : commit 메세지를 작성할 수 있는 vim 환경이 나온다.
아래의 Commit Convention을 참고하자.
4. `git push origin main` 으로 마무리 한다.
- Github에 push를 했는데 시간이 다르게 보일 때가 있는데 이는 push를 한 시점이 기준이 아닌 commit을 한 시점을 기준으로 등록되기 때문이다.

### 분할 commit

작업 단위를 분할하여 commit을 하는 이유는 한번에 commit을 하면
commit된 내용을 적기가 애매하고 어떤 것이 어디에서 바뀐지 찾기 힘들어서 이다.

하나 씩 `git add`를 해서 commit하는 습관을 들여보자!

### git init

새로운 폴더에 `git init`을 하면 레포지토리를 만들게 된다.
가상의 stage와 localrepo를 만들게 되는데 이렇게 되면 remote repo가 없다.
-> github 등에서 repo를 만들고 디렉토리와 이름을 똑같게 만든다.

**git init은 조심히 사용 해야 한다.**
`git init` 취소 시키는 방법 :  .git을 지우면 된다
-> `rm -rf .git` (이후 `ls -a`로 확인)

**git branch name을 맞춰줘야한다**

`git branch -M 바꿀이름`(ex   master -> main : main으로 바꾸는 이유는 최근 이름 바꾸기 운동이 일어나고 있어서임)
`git push -u 받는사람별명(mask) 브랜치이름(main)` : (u: upstream set)

서로 상관 관계에 대해 연결이 안되어 있는 상태이기에, local에서 github으로 보낼 때 둘 다 같은 상태로 유지하기 위해 위의 방법을 사용한다.

- clone과 init은 서로 다르다.
clone은 remote 시 check한 내용이 전부 오지만 
init은 하나하나 다 설정해 줘야 한다.
- `git remote remove 별명` : branch 제거
- `git remote add origin` : origin branch 추가
- `git remote` : branch가 뭐가 있는지 확인이 가능하다.  ex)origin이라는 별명을 가진 branch가 있다
- `git remote -v` : git의 주소가 나온다.

# Commit Convention

1. 커밋 제목은 50자 이내로 요약하여 작성한다
2. 제목과 내용사이 한 칸의 여유를 두고 작성한다.
3. prefix를 사용하여 한 눈에 커밋의 용도를 알기 쉽게 한다.
작업을 어떻게 쪼갤것인가(동작하는 단위로)에 대한 고민을 하고 commit을 하자!

> feat : 기능개발 (java poject, frontend project..기능 구현일어날때)
dosc : 문서작업(.md)
conf : 환경설정(npm init)
test : 테스트 (본 코드에 대한 테스트 코드 작성, 부산물일경우)
fix : 버그 픽스(기능에 대해 mal function, 동작안되거나 잘목되는 경우)
refactor : 잘 돌아가는 코드를 inhancement (기능 향상)
ci : 기능 개발 시 테스트코드를 자동으로 돌려주어 다른 작업을 할 수 있게 함
build : 빌드테스트의 부산물을 커밋
perf : 퍼포먼스테스트의 부산물을 커밋
> 

```
과제 : clone의 방법으로 저장소 하나 가져오기 repo name: TIL
description: Today I Learned..
Add README.md

github에 TIL만들기 위에 전부 입력 체크 후
dev에서 git clone TIL 주소

```
