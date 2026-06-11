docker build -t custom-jenkins .



docker run -d \
  --name jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  my-jenkins <- 이건 리눅스용



  docker run -d ^
    --name jenkins ^
    -p 8080:8080 ^
    -p 50000:50000 ^
    -v jenkins_home:/var/jenkins_home ^
    -v //var/run/docker.sock:/var/run/docker.sock ^
    custom-jenkins


  docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -v //var/run/docker.sock:/var/run/docker.sock custom-jenkins

  699d56b90ff86f7fd9ffe93b38259a3bf3d492ef6000f7b0e58cd3954cca2a49

  4f26fa9c802e47c398c520d3af108b5c
  **비번임 중요**

  5. 자주 사용하는 관리 명령
  컨테이너 중지
  docker stop jenkins
  컨테이너 시작
  docker start jenkins
  로그 확인
  docker logs -f jenkins
  컨테이너 삭제
  docker rm -f jenkins
  이미지 삭제
  docker rmi custom-jenkin

  docker exec -it jenkins bash

   docker ps -a  후 status에 up이 있어야됨

   docker rmi my-jenkins 이미지 삭제

   678cf3c1788b4b7bbced2f7854bb070a

   docker rm -f jenkins

   docker rmi -f my-jenkins

   docker volume rm jenkins_home

   docker builder prune -af

   docker system prune -af

   docker build --no-cache -t my-jenkins .

   docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --restart unless-stopped my-jenkins

   docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword