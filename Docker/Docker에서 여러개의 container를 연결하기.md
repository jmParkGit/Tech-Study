# Docker에서 여러개의 container를 연결하기
- Docker container는 분리된 filesystem과 network를 가짐
- 따로 설정이 없으면 filesystem과 network는 통신이 불가

## 명령어
### docker network 만들기
```Shell
docker network crete {네트워크명}
```

### docker network 연결해서 container실행하기
- 아래는 예제
```Shell
docker run -d -p 24017:24017 --network test --network-alias mongo mongo
```

### Docker network로 앱에 DB연결하기
1. 네트워크 만들기
```Shell
docker network create memo
```

2. mongoDB network 연결
```Shell
docker run -d -p 24017:24017 --network memo --network-alias mongo mongo
```

3. pymongo사용시 주소 변경
```Shell
client = MongoClient('mongo', 27017) # localhost -> mongo로 변경
```

4. 새로운 이미지 생성
```Shell
docker build -t simple-memo-app:version3 .
```
5. app network연결
```Shell
docker run -p 5000:5000 --network memo simple-memo-app:version3
```
