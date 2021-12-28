# WARNING: The requested image's platform (linux/arm64/v8) does not match the detected host platform (linux/amd64) and no specific platform was requested
## 에러로그
```Shell
WARNING: The requested image's platform (linux/arm64/v8) does not match the detected host platform (linux/amd64) and no specific platform was requested
standard_init_linux.go:228: exec user process caused: exec format error
```

## 원인
- 애플 M1 맥북으로 빌드 후, 타 CPU에서 동작하는 우분투에서 docker run시 위의 에러가 나옴.

## 해결책
- 빌드 시 --platform linux/amd64 추가
```Shell
docker build . --platform linux/amd64 -t jmparkdocker/docker-memo:version_linuxAmd64_1
```
