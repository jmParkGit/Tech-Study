# Middleware란?
- 그림
- Node.js에서 Middleware란, 데이터를 처리하기 위한 모듈 개념
- Express.j에서의 예제 (ex: urlencoded, json)
```jsx
app.use(express.urlencoded({ extended: false }));
app.use(express.json());
```
## Middleware 작성방법
```jsx
app.use((req, res, next) => {
  // code
});
```
### req
- HTTP Headers, Query Parameters, URL등 Client가 보낸 정보가 존재
### res
- HTTP Stauts Code, 응답 데이터 형식, 헤더등의 응답을 위한 정보
## Middleware 호출 순서
- 그림
