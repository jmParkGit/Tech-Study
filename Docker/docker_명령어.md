# docker_명령어
## container 조작하기
### docker container 실행하기
```shell
docker run [options] {image_name} [command]
```
- ```-p host_port:container_port``` 옵션은 컨테이너의 포트와 호스트의 포트를 연결해 줌.
- ```-d``` 옵션은 docker container가 백그라운드에서 실행됨을 의미

### docker container 상태 확인하기
```shell
docker ps
```
- CONTAINER_ID: container의 고유 ID
- IMAGE: container를 뛰우는데 사용한 image 이름
- CREATED: container가 생성 시간
- STATUS: container의 상태
- PORT: port를 publish하는 경우 어떻게 되어 있는지
- NAMES: container의 이름
  
### docker container 멈추기
```shell
docker stop {container_id|container_name}
```
```shell
docker kill {container_id|container_name}
```
- stop: SIGTERM 신호를 보냄
- kill: SIGKILL 신호를 보냄

### docker container 되살리기
```shell
docker restart {container_id|container_name}
```

- 실행중인 container에서 명령어 실행하기
```shell
docker exec [options] {container_id|container_name} [command]
```

### docker container삭제하기
```shell
docker rm {container_id}
```

### docker image build 하기
```shell
docker build [OPTIONS] PATH
```
- ```-t```옵션은 이미지에 이름을 붙일수 있게 함.-> {image_name}:tag}
- 예제
```shell
docker build . -t jmparkdocker/docker-memo:version1
```

### docker image 목록 확인하기
```shell
docker images
```

### docker hub에 로그인
```shell
docker login
```

### docker hub에 이미지 올리기
```shell
docker push {user_id}/{image_name}:{image_tag}
```

### docker hub에서 이미지 가져오기
```shell
docker pull {user_id}/{image_name}:{image_tag}
```

### reference
https://docs.docker.com/engine/reference/commandline/cli/
