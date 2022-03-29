Git의 초기 설정
git config --list : 현재 상태 확인
git config --global user.name ""
git config --global user.email ""
git config --global core.editor "vim"
git config --global core.pager "cat"

삭제 시  명령어
git config --global --unset


이후
git clone 깃주소 를 입력하고 ls를 눌러보면 해당 깃 주소에 등록된 파일들이 불러와진다

파일 수정 후
git status - > 변경 사항이 있으면 Changes not staged for commit이 뜸
로컬 저장소로 올리기전의 대기장소 :  stage
변경 사항을 등록하기 위해 git add 파일명 사용
이후 git status를 사용해 반영이 됐는지 확인
git commit 입력 -> commit 메세지를 작성할 수 있는 vim 환경이 나옴
i를 눌러 50자 내에 설명할 수 있게 작성
★가급적 영작을 하도록 연습한다.
혹은 git commit -m "내용"으로 작성도 가능
맨 위 : 제목
두 줄 엔터 후 내용 작성
이후 esc :wq
git status로 확인
확인이 끝나면 git push origin main

분할 commit
작업단위를 분할하는 이유 -> 한번에 commit을 하면 내용을 적기가 애매함, 뭐가 어디에서 바뀐지 찾기 힘듬
하나만 git add 함
docs : 문서작업
feat : 코드

git remote : origin이라는 별명을 가지고 있다 (alias)
git remote -v : 주소

------------------------------------------
clone은 remote 시 다 붙어서 오지만
init은 하나하나 다 설정해줘야한다

git remote remove 별명
이후 git remote add origin

push를 늦게 해도 commit을 한 시점을 기준으로 등록된다


새로운 폴더에 git init을 하면 레포지토리를 만들게 된다
가상의 stage와 localrepo를 만들게 된다 이러면 remote repo가 없다
-> github 등에서 repo를 만들고 디렉토리와 이름을 똑같게 만든다


git init 사용 -> clone과는 다름
git init은 조심히 사용할것
git init 취소 시키는 방법 : .git을 지우면 된다 : rm -rf .git(ls -a로 확인)

git branch name을 맞춰줘야한다
git branch -M 바꿀이름(ex   master -> main : 이름 바꾸기가 일어나고있음)
git push -u 받는사람별명(mask) 브랜치이름(main) : (u: upstream set)서로 상관관계에 대해 연결이 안되어 있는 상태, local에서 github으로 보낼때 둘 다 같은 상태로 유지하기 위해 사용

과제 : clone의 방법으로 저장소 하나 가져오기 repo name: TIL
description: Today I Learned..
Add READMe.md

github에 TIL만들기 위에 전부 입력 체크 후
dev에서 git clone TIL 주소
