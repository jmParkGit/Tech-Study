# mac에서 mongo 실행,중지,재실행 시키는 명령어
## mongo 실행 시키기
```shell
brew services start mongodb-community
```

## 실행중인 리스트 확인
```shell
brew services list
```

## 중지
```shell
brew services stop mongodb-community
```

## 재실행
```shell
brew servcies restart mongodb-community
```
