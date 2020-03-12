# deploy
deploy

# 세팅 절차
- git에 새로운 저장소 생성
- https://github.com/YeongJaeHan/deploy.git
- 로컬 PC에서 aws 폴더를 vs code에 오픈
- terminal 오픈
- $ git clone https://github.com/YeongJaeHan/deploy.git
- cd deploy

# 파일 세팅 (~/aws/deploy)
- fabfile.py, deploy.json 파일을 deploy에 위치
- 서버파일을 생성
- wsgi.py(엔트리포인트), run.py 생성
- 코드 작성
- 배포 관련 환경변수 파일 수정( deploy.json ) 
- git 주소, 서버의 IP, 도메인은 향후 IP와 연결(호스팅쪽에서 할 일), 리눅스 접속 계정 ID등 설정
- requirement.txt : 본서비스를 구동하기 위해 사용된 모든 파이썬 패키지를 기술한다

# 구동
- python3 버전 기반으로 수행
- 운영체계 및 서버 셋팅 및 배포, 업데이트 관리등등을 자동화하는 모듈 =>febric3
- $ pip install fabric3
- git에 최종소스 반영