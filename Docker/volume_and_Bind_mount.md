# volume과 Bind mounts
-  volume은 Docker container에 의해서 생성됨.
-  volmue은 Docker CLI 혹은 API로 관리가능
-  Bind mounts는 host system의 파일 혹은 디렉토리가 마운트도니다. 
-  Bind mounts는 docker이외 프로세스가 수정가능.
-  일반적으로 volume이 더 관리가 용이함.

## volume CLI
- volume 만들기
```Shell
docker volume create {volume이름}
```

- named volmue에 대한 정보보기
```Shell
docker volume inspect {volume이름}
```

- App에 named volume 연결하기 예제
  - 사용할 app은 mongoDB mongo
```Shell
docker volume create memo
docker run -d -p 27017:27017 -v memo:/data/db mongo
```

## Bind mount
- 예제
```Shell
docker run -v {host_path}:{container_path} <docker_image>
```
```Shell
docker run -v "$(pwd)/templates:/templates" -p 80:5000 jmparkdocker-memo:version2
```


## docker docs
https://docs.docker.com/storage/volumes/
