# springboot-jenkins-docker-slack
- 참고 자료 https://jojoldu.tistory.com/139

## 1. 컨테이너 실행 
  -> docker run -d -p 32700:8080 -p 32701:50000 imageName
## 2. jenkins 컨테이너 초기 비밀번호 입력 및 default plugins 다운로드
  -> docker exec -it contanaiterName /bin/bash
  -> shell  진입 후 cat /var/jenkins_home/secrets/initailAdminPassword
  -> 확인된 password를 localhost:32700(docker port) 접속 후 입력 
![image](https://user-images.githubusercontent.com/41417504/115197401-eace8200-a12b-11eb-920e-52cfbe3b49e9.png)
## 3. job 생성
![image](https://user-images.githubusercontent.com/41417504/115198972-a47a2280-a12d-11eb-9d9d-522f11b4efa3.png)
-> job 생성
4. job 설정
 ![image](https://user-images.githubusercontent.com/41417504/115199051-b9ef4c80-a12d-11eb-842c-11a18b2ea29e.png)
-> 빌드할 github repogitory 및 credential 설정(추후 ssh 로 업데이트 예정)
-> Branches to build (push 시 자동 빌드할 브랜치 설정)
-> 빌드 유발은 gitHub hook trigger 사용
![image](https://user-images.githubusercontent.com/41417504/115199494-3a15b200-a12e-11eb-9800-ca629cd05f86.png)
### webhooks 설정
1. repositoy home에서 settings -> webhooks -> Add webhook
