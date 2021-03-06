# Git 공부

* svn
  * 중앙집중식 버전 관리 시스템
  * 파일을 관리하는 서버가 별도로 있고, 클라이언트가 중앙서버에서 파일을 받아서 사용
  * 파일을 관리하는 서버에 문제가 생기면, 각 클라이언트가 작업을 진행하는데 문제가 있다.
* Git 
  * 분산 버전 관리 시스템
  * 저장소를 전부 복제. 이 복제물로 서버를 복원할 수 있다.
  * 모든 Checkout는 백업 데이터라 생각할 수 있다.
 
 
 # 기본 명령어
 
 * git init : 기존 프로젝트를 git으로 관리
 
 * git add : 파일 추가
 
 * git clone [url] : 기존 fit 저장소 복사
 
 * git status : 파일 상태 확인
 
 * 커밋할 파일 무시
  * .gitignore 파일 생성하여 무시할 파일 패턴 설정
  
* gif diff : 변경 내용 확인

* git commit : 변경 사항 커밋
  * --amend : 기존의 커밋을 덮어씀 
  * ex) $ git commit -m 'initial commit' $ git add forgotten_file $ git commit --amend 
   ==> 두 번째 커밋이 세 번째 커밋을 덮어씀 

* git log : 커밋 히스토리 조회



# 리모트 저장소

* remote 저장소
  * 인터넷이나 네트워크 어딘가에 있는 저장소
  * 데이터를 push, pull 할 수 있는곳.
  * 저장소를 추가, 삭제. 브랜치를 관리, 추적 할 수 있다.
    
* git remote : 저장소 확인
  * 저장소를 clone 하면 origin이라는 리모트 저장소가 자동 등록
  * -v : 단축이름 URL 확인
  
* git remote add [단축이름] [url] : 리모트 저장소 추가
* git fetch [단축이름] : 로컬에는 없지만 리모트 저장소에 있는 데이터를 모두 가져옴. merge는 하지 않음(로컬에서 수동으로 해줘야함)
  * 저장소를 clone 하면 리모트 저장소를 origin 이라는 이름으로 추가
  * git fetch origin :  clone한 이휴에 수정된 것을 모두 가져온다.
* git pull : 리모트 저장소 브랜티에서 데이터를 가져올 뿐만 아니라 자동으로 로컬 브랜치와 머지시킬 수 있다.

* git push [리모트 저장소 이름][브랜치 이름] : 리모트 저장소에 push
  * 해당 명령은 clone한 리모트 저장소에 쓰기 권한 있어야한다.
  * 다른 사람이 push 한 후에 push 할 수 없다.
  * 다른 사람이 작업한 것을 merge 한 후에 push 할 수 있다.

* git remote show [저장소 이름] : 리모트 저장소 구체적인 정보 확인


  
# Git 브랜치

* Git은 데이터를 change set이나 변경사항으로 기록하지 않고 일련의 스냅삿으로 기록
* commit 하면 Git 현 staging area에 있는 있는 데이터의 스냅샷에 대한 포인터, 
  저자나 커밋 메시지 같은 메타 데이터, 
  이전 커밋에 대한 포인터 등을 포함하는 커밋 개체를 저장한다.
* 이전 커밋 포인터가 있어서 현재 커밋이 무엇을 기준으로 바뀌었는지 알 수 있다.
* 최초 커밋을 제외한 나머지 커밋은 이전 커밋 포인터가 적어도 하나씩 있고 브랜치를 합친 merge 커밋 같은 경우에는 이전 커밋 포인터가 여러개 있다.

* Git은 최초로 커밋하면 master라는 이름의 브랜치를 만들어서 자동으로 가장 마지막 커밋을 가리키게 한다.

* git branch [브랜치 이름] : 브랜치 생성

* Git은 'HEAD'라는 특수한 포인터가 있다. 이 포인터는 지금 작업하는 로컬 브랜치를 가리킨다.

* git checkout [브랜치 이름] : 새로 만든 브랜치로 'HEAD' 이동
  * -b [브랜치 이름] : 브랜치를 만들면서 Checkout까지 한 번 함.
  * ex) $ git checkout -b iss53 ==> $ git branch iss53   $ git checkout iss53
  
* git merge [브랜치 이름]

# 참고
* 프로 git
  * http://www.kyobobook.co.kr/product/detailViewKor.laf?ejkGb=KOR&mallGb=KOR&barcode=9788966261789&orderClick=LAH&Kc=
* 스프링5 레시피
  * http://www.kyobobook.co.kr/product/detailViewKor.laf?ejkGb=KOR&mallGb=KOR&barcode=9791162241035&orderClick=LAH&Kc=
* 자바 네트워크 소녀 Netty
  * http://www.kyobobook.co.kr/product/detailViewKor.laf?ejkGb=KOR&mallGb=KOR&barcode=9788968482243&orderClick=LEA&Kc=