# 1. Git bash를 사용하기 위한 기본 개념과 Linux 명령어


### 1-1. 기본 개념
![](https://media.vlpt.us/images/toffg6450/post/5843f7a7-a7f7-4b41-aa12-48347bfb3187/image.png)

>
- **커널** : HW와 응용 프로그램을 이어주는 운영체제의 핵심 시스템SW
- **shell** : 운영자와 커널을 이어준다, 시스템 sw에게 명령을 내려준다.
- **$** : 사용자의 입력을 받을 준비가 됐다.
- **~** : 로그인한 사용자의 최상위 폴더를 의미한다.
- **/** : 운영체제가 접근할 수 있는 최상위 폴더이다.
>

### 1-2. 명령어 & 의미
>
- **cd** : change directory, 해당 directory로 이동한다.
단, 파일 목록 안에 있는 directory로만 이동이 가능하다.
ex) cd Documents
- **cd ..** : 상위 directory로 이동
- **cd .** : 현재 directory로 이동 (의미없음)
- "-" : flag(옵션) ex) ls -a
- **--** : 단어 전체를 쓸 때 --사용 
ex) ls --all
- **ls** : list segment, 파일의 목록을 출력한다.
- **ls -l** : line by line 한줄 한줄 표현(상세정보까지)
- **ls -a** : 숨긴파일을 포함한 모든 파일의 목록 출력한다.(all)
- **/** : directory간에 단계를 구분하기 위한 구분자
- **pwd** : 현재 directory, 현재 작업중인 directory 출력
- **mkdir** : make directory, directory를 생성한다.
 ex) mkdir dev
- **touch** : 파일 생성, 새파일 생성, 빈파일 생성 / 생성할 수 있는것이 제한되어 있다.(컴파일러 과정때문에) 
ex) touch index.html
- **mv 파일 directory/** : 파일을 해당 directory로 이동한다.
- **mv 파일 ..** : 파일의 위치를 상위 directory 이동시킨다.
- * ****: 에스터리스크(모두), 와일드 카드
- **cp 파일 파일위치/** : 파일을 똑같이 복사, 현재 위치에도 존재
- **rm 파일** : 해당 파일을 삭제한다.
directory는 rm으로 지울 수 없다 : 빈 directory 제거 => rm -r directory/
- **f** : 강제로 명령 
ex) rm -rf directory
- **cat 파일명** : 파일 들어가지 않고 안의 내용 출력 
ex) cat README.md
>

### 1-3. Vim

Vim은 vi 호환 텍스트 편집기이다.

`vi 파일이름.프로그램명(py,txt..)`를 입력하면 vim을 사용할 수 있다.
 어떤 프로그램으로 열어라 명시해줘야한다.


>
- **i** : Insert mode (수정모드)
- **esc** : normal mode (일반모드)
- "**:**" : command mode, shift + ; 를 normal mode(esc)에서 눌러 진입한다. 
( : )를 누른 뒤 아래의 명령어들을 사용할 수 있다.
- **w** : 현재 파일 명으로 저장, 나가지 않는다.
- **q!** : 수정한 것이 없던 것처럼 해서 나간다. 강제 종료한다.
- **wq** : 저장 후 종료한다.
- **wq!** : 강제 저장 후 종료한다.
>

# 2. Git & Github

### 2-1. Git과 Github

1. Git : VSC(Version Control System) 버전 관리 도구
== SCM(Source Code Management : 형상관리의 하위분류)
< SCM(Softwqre Configuration Management : 형상관리, software 개발에서 관리 해야 하는 것 인력, 코드 제원...등의 크게 묶음)

2. Git object 
- Blob
파일 하나의 내용에 대한 정보(파일에 대한 수정사항)
- Tree
Blob이나 subtree의 메타데이터(디렉토리 위치, 속성, 이름 등)
- Commit
커밋 순간의 스냅샷 (Blob+Tree)

3. 주로 사용하는 대표적인 원격저장소
- Github : opensource
- Bigbuket : jira, trello와 함께 많이 사용, 대기업이 주로 사용한다.
- Gitlab : 사설 서버 구성 가능해 보안이 중요한 프로젝트에 사용한다.
>
★ **Git과 Github는 다르다**
**Git** :  **버전관리 시스템 tool |** **Tool**
**Github** : **원격저장소 웹 서비스 | Web Service**

### 2-2. git Process Flow and Command
![](https://media.vlpt.us/images/toffg6450/post/12c4f7ab-b17c-4aa5-a4b1-520560626f88/image.png)
- `git add` -> staging area(분류하기 위한 임시공간) 에 올린다., blob 생산
- `git commit` -> blob에 대한 메타데이터 작성, 메세지를 남긴다.
- `git push` -> githib(원격 저장소)에 저장한다.


# 3. Git의 기본 사용

### 3-1. Git의 초기 설정
>
기본 초기 설정 시 사용하는 명령어들
`git config --list` : 확인
`git config --global user.name ""`
`git config --global user.email ""`
`git config --global core.editor "vim"`
`git config --global core.pager "cat"`
>
`git config --global --unset` : 잘못 입력 했을 경우 삭제하기 위한 명령어
`git clone gitcloneurl` : 해당 깃 주소에 등록된 파일들이 불러와진다.
gitcloneurl에 해당 깃 주소를 그대로 입력하면 된다.

### 3-2. Git에서 Github로 push하기
![](https://media.vlpt.us/images/toffg6450/post/04542853-2894-4830-aff9-a64bdd66e1e0/image.png)

1. `git status` - > 현재 Git의 상태를 의미하며 변경 사항이 있는지 확인할 수 있다. 변경 사항이 있으면 Changes not staged for commit 문구가 뜬다.
**git status는 각 구간 마다 한 번씩 사용하여 확인하는 습관을 들이자.**
로컬 저장소로 올리기전의 대기장소 : stage

2. `git add filename` : 올리고 싶은 파일 혹은 변경 사항이 있는 file을 등록한다.

3. `git commit` : commit 메세지를 작성할 수 있는 vim 환경이 나온다.
아래의 Commit Convention을 참고하자.

4. `git push origin main` 으로 마무리 한다.
- Github에 push를 한 시간이 내가 실제로 push한 시간과 다르게 보일 때가 있다.
 이는 push를 한 시점이 기준이 아닌 commit을 한 시점을 기준으로 등록되기 때문이다.

- 로그인을 요구하는 팝업이 뜨는 경우가 존재한다.
이러한 경우에는 Github에서 나의 프로필 옆의 화살표를 눌러서
 "Settings" -> "Developer Settings" -> "Personal Access Tokens" -> "Generate new token"
위의 과정을 거쳐 나온 토큰을 생성하여 나온 패스워드를 입력해주면 된다.


### 3-3. git fetch & git pull의 차이

- `git fetch` : 원격 저장소의 데이터를 모두 local로 가져온다.
코드를 가져와서 fetch라는 임시 브랜치에 담아둔다고 생각하면 된다.
수동으로 Merge를 해줘야 한다.

- `git pull` : 원격 저장소의 정보를 가져오면서 자동으로 local branch에 병합까지 수행시켜준다. 자동으로 merge가 되기 때문에 어떤 내용이 변경 되었는지 확인할 수 없다.

### 3-4. 분할 commit

작업 단위를 분할하여 commit을 하자!
그 이유는 한번에 commit을 하면 commit할 내용을 적는 것과 어떤 것이 어디에서 바뀐지 찾기 힘들기 때문이다.

하나 씩 `git add`를 해서 commit하는 습관을 들여보자!


### 3-5. git init

새로운 폴더에 `git init`을 하면 repository를 만들게 된다.
가상의 stage와 local repository를 만들게 되는데 이렇게 되면 remote repository를 없다.
-> Github 등의 원격 저장소에서 repository를 만들고 디렉토리와 이름을 똑같게 만든다.

- **git init은 조심히 사용 해야 한다.**
`git init`을 취소 시키는 방법은  .git을 지우면 된다.
-> `rm -rf .git` (이후 `ls -a`로 확인)

- **git branch name을 맞춰줘야 한다.**
`git branch -M name`(ex   master -> main : main으로 바꾸는 이유는 최근 이름 바꾸기 운동이 일어나고 있어서이다.)
서로 상관 관계에 대해 연결이 안되어 있는 상태이기에, local에서 github으로 보낼 때 둘 다 같은 상태로 유지하기 위해 다음의 방법을 사용한다.
`git push -u 받는사람별명 브랜치이름` : (u: upstream set)

- **clone과 init은 서로 다르다.**
clone은 remote 시 check한 내용이 전부 오지만
init은 하나하나 다 설정해주고 만들어야 한다.

- **원격 저장소 관련 명령어**
>`git remote remove name` : 해당 name의 branch 제거
`git remote add name` : 해당 name의 branch 추가
`git remote` : 현재 프로젝트에 등록된 remote 저장소를 확인할 수 있다.
`git remote -v` : 해당 branch의 git 주소가 나온다.




# 4. Commit Convention

Commit시 지켜야하는 규약이다. 아래의 규약을 따르면 깔끔한 관리가 가능하다!

1. 커밋 제목은 50자 이내로 요약하여 작성한다.

2. 제목과 내용사이 한 칸의 여유를 두고 작성한다.

3. prefix를 사용하여 한 눈에 커밋의 용도를 알기 쉽게 한다.
작업을 어떻게 나눌 것인가(동작하는 단위로)에 대한 고민을 하고 commit을 하자!

> - feat : 기능개발 (java poject, frontend project..기능 구현일어날때)
- dosc : 문서작업(.md)
- conf : 환경설정(npm init)
- test : 테스트 (본 코드에 대한 테스트 코드 작성, 부산물일경우)
- fix : 버그 픽스(기능에 대해 mal function, 동작안되거나 잘목되는 경우)
- refactor : 잘 돌아가는 코드를 inhancement (기능 향상)
- ci : 기능 개발 시 테스트코드를 자동으로 돌려주어 다른 작업을 할 수 있게 한다.
- build : 빌드테스트의 부산물을 커밋한다.
- perf : 퍼포먼스테스트의 부산물을 커밋한다.
>

