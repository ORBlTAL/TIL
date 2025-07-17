## GIT이란?

코드의 ‘변경 이력’을 기록하고 ‘협업’을 원활하게 하는 도구

- 버전관리 - 변화를 기록하고 추적하는 것

※ 버전으로 쌓아나가면서 작업을 하면 문제가 생기 이전 지점으로 가기가 편하다.( 저장은 이게 불가)

- Git의 역할
1. 코드의 버전(히스토리)을 관리
2. 개발되어 온 과정 파악
3. 이전 버전과의 변경 사항 비교

- Git 의 영역
1. Working Direction : 실제 작업 중인 파일들이 위치하는 영역
2. Staging Area : Working Directory 에서 변경된 파일 중, 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 준비 영역
3. Repository : 버전 이력과 파일들이 영구적으로 저장되는 영역. 모든 버전과 변경 이력이 기록됨. 

※ 요약하자면 WD에서 변경사항을 넣고, SA에서 RP로 최종 버전을 보낸다(역순으로도 가능).

## GIT 명령어

- git inti : 로컬 저장소 설정(초기화) / git의 버전 관리를 시작할 디렉토리에서 진행
- git add : 변경 사항이 있는 파일을 staging area에 추가
- git commit : staging area에 있는 파일들만 저장소(Repository) 에 기록 : 
해당 시점의 버전을 생성하고 변경 이력을 남기는 것…. 이렇게 하면 stagiing area는 비게된다.
- git status : git의 상태를 살펴본다.
- git log : 마지막 영역인 repository를 확인한다. 
commit이 여러개면 여러줄이 뜬다. author와 만든 날짜와 시간이 나온다.
- git log - -oneline : commit의 버전을 한줄씩만 출력되게 한다.
- git config - -global -l : git global 설정 정보 보기
- git commit - -amend

---

---

- git remote add origin remote_repo_url
    
    origin 은 추가하는 원격 저장소의 별칭 , remote_repo_url이 추가하는 원격 저장소의 url
    
- git remote -v : 등록된 원격 저장소의 주소를 출력해줌.
- git push origin master : 원격 저장소에 commit 목록을 업로드 (변경사항 만큼 업로드, 동일한건  안올림)

※ 원격 저장소에는 commit이 올라가는 것! commit이 없다면 push 할 수 없으므로 주의!

- git clone remote_repo_url(원격 저장소 전체를 다운로드)
- git pull origin master (원격 저장소에 변경사항 만큼 다운로드)

### git commit 생성)

git commit -m “first commit” >> -m “first commit” … 버전 설정 하는 과정

이렇게만 명령어를 치면 Author identity unknown 이라면서 책임자가 누구냐고 묻는다.

※밑의 2가지 명령어가 필요)

- git config —global [user.email](http://user.email) “you@example.com”
- git config —global [user.name](http://user.name) “Your Name”
- commit 할 때 버전이름 같아도 commit됨(해시값이 다르기에). 수정도 가능

 

### Git 주의사항

1. git 저장소 내부에 git 저장소는 위치할 수 없다.
2. git init을 하는 순간 어떤 숨김 폴더가 생성됨.

※ git init을 잘못 하면 해당 디렉토리에서 숨긴 파일을 보이게 활성화 하고, git 폴더를 삭제

1. online 과 local은 서로를 모른다. commit이 안맞아 떨어지면 push, pull이 안됨!!

### 로컬

- 현재 사용자가 직접 접속하고 있는 기기 또는 시스템.
개인 컴퓨터, 노트북, 태블릿 등 사용자가 직접 조작하는 환경

## VIM 에디터는 2가지 Mode가 존재

1. 수정 모드 (내용을 작성하는 모드)
2. 명령 모드 (쓰기(write), 삭제, 종료(quit)….) shitf+: 하고 나서 작성…ex) :wq(쓰고 나가기)

명령 → 수정 : i

수정 → 명령 : ESC

명령은 : 이후에 특정 키워드를 입력하여 작성

### GitIgnore

- Git 에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일
- git 의 관리를 받은 이력이 있는 파일이나 디렉토리는 나중에 gitignore를 작성해도 적용되지 않으므로 처음에 다 설정해야함.
- [gitignore.io](http://gitignore.io) 사이트에서 사용하는 os, 언어, 프로그램에 맞게 불필요한 거를 정리해줌.

### TIL

- 매일 내가 배운 것을 마크다운으로 정리해서 문서화 하는것.

※ 단순히 배운 것만을 필기하는 것이 아닌 스스로 더 나아가 어떤 학습을 했는지를 기록

- TIL을 통해 **문서화** 하는 능력을 길러야 한다.
    
    ㄴ 스스로 학습해 성장할 수 있고 문서화를 통해 내 생각을 정리하고 팀에게 공유할 수 있는 능력.
    

---

### tip)

git status에서 나온 문장이 **빨간색** 이면 WD영역 , **초록색**이면 SA 영역이다.

업로드는 push , 변경된 사항만 다운로드는 pull, 전부 다운로드는 clone

clone의 경우 주소가 필요함(remote_repo_url)

처음 다운로드 받을 때는 clone사용, 그 뒤로는 pull을 사용하면 된다.!!