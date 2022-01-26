# docker_명령어_리소스 삭제하기

## 리소스 확인하는 명령어
```Shell
docker ps -a
docker images
docker network ls
docekr volume ls
```

## 리소스 삭제하기
```Shell
docker rm {container_id}
docker rmi {image_id}
docker network rm {network_id}
docker volume rm {volume_id}
docker system prune
```
