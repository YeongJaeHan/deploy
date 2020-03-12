# deploy
deploy

# 세팅 절차
- git에 새로운 저장소 생성
- https://github.com/YeongJaeHan/deploy.git
- 로컬 PC에서 aws 폴더를 vs code에 오픈
- terminal 오픈
- $ git clone https://github.com/YeongJaeHan/deploy.git
- cd deploy

# 파일 세팅 (~/aws/deploy) //파일이름 정확하게 쓸것
- fabfile.py, deploy.json 파일을 deploy에 위치
- 서버파일을 생성
- wsgi.py(엔트리포인트), run.py 생성
- 코드 작성
- 배포 관련 환경변수 파일 수정( deploy.json ) 
- git 주소, 서버의 IP, 도메인은 향후 IP와 연결(호스팅쪽에서 할 일), 리눅스 접속 계정 ID등 설정
- requirements.txt : 본서비스를 구동하기 위해 사용된 모든 파이썬 패키지를 기술한다

# 구동
- python3 버전 기반으로 수행
- 운영체계 및 서버 셋팅 및 배포, 업데이트 관리등등을 자동화하는 모듈 =>fabric3
- $ pip install fabric3
- git에 최종소스 반영
- $ fab new_server
- 중간에 y, git 로그인등등이 나올 수 있다
- 브라우저 가동
- 13.125.245.21에 접속
- 접속로그 확인 (리눅스에서 진행)(/home/ubuntu인 상태)
- $ tail -f /var/log/apache2/access.log
- 모니터링 하다가
- 빠져나가기 => ctrl+c
- 에러로그
- $ tail -f /var/log/apache2/error.log
# 이후작업
- 코드수정
- git 최신반영
- 서버 업데이트
 $ fab deploy

# 잘 안된다
- 소스코드상에 파일명, 설정값등 오타가 없어야 함
- git에 최종 소스가 모두 반영되어야 함
- 리눅스에서 기존의 흔적을 모두 제거한다
  현재위치 : /home/ubuntu
  프로젝트 삭제 : $ rm -r -f deploy //project name에 적어둔거 적어줘야함
  가상환경 삭제 : $ ls -a //숨김파일 확인 .virtualenvs가 파란색 글씨로 적혀 있음 이게 숨겨져있다는 뜻
                  $ rm -r -f .virtualenvs
- 로컬 PC
  $ fab new_server

# 가상 호스트가 설정된 부분
- deploy는 프로젝트명(deploy.json)
- /etc/apache2/sites-available/deploy.conf
- 파일 읽기
  $ cat /etc/apache2/sites-available/{}.conf