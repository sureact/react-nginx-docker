## 첫 번째 시도

1. 테스트용 ec2 생성함.
2. 보안규칙에서 http랑 https 포트 열어줌.
3. 새로 생성한 ec2에 도커 설치
4. 내 프로젝트에 도커파일 생성.

### cicd 구축 전에 이미지 제대로 받아와지는지 테스트

1. 내 로컬에서 도커허브로 이미지 올리기
    1. 터미널에서 도커허브 로그인
    2. 내 프로젝트 도커빌드 (amd 어쩌구 해서 리눅스 명시)
    3. 도커허브로 이미지 푸시
2. Ec2에서 도커 이미지 받아오기
3. 받아온 도커 이미지 실행

### 본격적으로 cicd 구축하기

1. [https://bgpark.tistory.com/85](https://bgpark.tistory.com/85) Ec2 비밀번호로 로그인 설정
2. 깃헙 레포지토리 시크릿에 도커허브 계정정보, aws 접속관련정보 저장
3. 깃헙 워크플로우 작성. (https://github.com/docker/metadata-action 참고함) Semver 로 했는데 버전이 어디에 적히는지 모르겠음.
4. deploy 부분은 https://github.com/appleboy/ssh-action 참고함.
5. Ec2 주소로 들어가니 사이트 정상 동작함.
