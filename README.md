# springboot-jenkins-docker-slack
- 참고 자료 https://jojoldu.tistory.com/139

1. 컨테이너 실행 
-> docker run -d -p 32700:8080 -p 32701:50000 imageName
2. jenkins 컨테이너 초기 비밀번호 입력 및 default plugins 다운로드
-> docker exec -it contanaiterName /bin/bash
-> shell  진입 후 cat /var/jenkins_home/secrets/initailAdminPassword
-> 확인된 password를 localhost:32700(docker port) 접속 후 입력 
![image](https://user-images.githubusercontent.com/41417504/115197401-eace8200-a12b-11eb-920e-52cfbe3b49e9.png)
