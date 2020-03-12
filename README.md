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