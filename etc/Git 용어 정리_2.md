# Git 용어 정리_2
## issue
- 프로젝트에서 issue는 프로젝트에서 해결해야하느 문제
- 버그신고, 기능추가 등으 제안, 앞의 문제를 해결하기 위하 작업단위등이 해당함
<img width="641" alt="스크린샷 2022-01-16 오후 10 07 16" src="https://user-images.githubusercontent.com/84515872/149661205-e2d3dc2f-927a-4c68-843b-7b37a424baff.png">


## branch
- branch를 이용하면 각각의 feature단위, 혹은 목적단위로 나누어 작업할수 있음
<img width="320" alt="스크린샷 2022-01-16 오후 10 05 30" src="https://user-images.githubusercontent.com/84515872/149661158-16dd794d-5618-46da-9775-04cbd515b8d8.png">


## merge
- merge는 다르 브랜치르 다른 브랜치에 합치는 것
- 특정 브랜치의 commit들을 다르 브랜치의 commit 내역에 모두 반영
- 기본설정은 해당 브랜치으 모드 commit을 모두 다 반영

## merge conflict
- 하나의 파일을 여러 브랜치에서 수정하고 하나의 branch에 merge하려고 할떄 merge conflict이 발생
- <<<<<<< 에서 >>>>>>> 까지가 충돌이 나는 부분
```
<<<<<<< HEAD
{현재 브랜치의 다른 파일 내용}
=======
{충돌나는 브랜치명 또는 commit에서의 다른 파일 내용}
>>>>>>> 충돌나는 브랜치명 또는 commmit 아이디
```
