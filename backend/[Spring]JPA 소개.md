# [Spring]JPA 소개
- JPA는 자바가 SQL을 쓰지 않고 데이터르 생성, 조회, 수정, 삭제할수 있도로 해주는 도구
- "테이블"은 Domain, "SQL"은 Repository
- JPA는 Repository를 통해서만 사용 가능
```Java
public interface CourseRepository extends JpaRepository<Course, Long> {
}
```

## CRUD
- 생성 (Create)
- 조회 (Read)
- 변경 (Update)
- 삭제 (Delete)
- 예제
  - [https://localhost:8080/api/persons](https://localhost:8080/api/persons) POST : 친구 생성
  - [https://localhost:8080/api/persons](https://localhost:8080/api/persons) GET : 친구 목록 조회
  - [https://localhost:8080/api/persons](https://localhost:8080/api/persons)/{id} PUT : 친구 정보 변경
  - [https://localhost:8080/api/persons](https://localhost:8080/api/persons)/{id} DELETE : 친구 정보 삭제


## Service으 개념
- Controller: 가장 바깥부분, 요청/응답을 처리함.
- Service: 중간 부분, Update는 Service부분에 작성
- Repo: 가장 안쪼 부분, DB와 맞닿아 있음
  - Repository, Entitiy

## Lombok 소개
- Lombok은 자바 프로젝트르 진헹하는데 거으 필수적으로 필요한 메소드/생성자 등을 자동생성해줌으로써 코드를 절약할 수 있도록 도와주는 라이브러리

## DTO
- read, update 할때 원본 테이블 클래스를 막 사용하면 안됨.
- 완충재(?)로 사용하는것이 DTO(Data Transfer Object)
