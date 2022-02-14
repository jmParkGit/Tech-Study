# dom 소개
- ```<div>Hello</div>```, ```<p>안녕하세요</p>``` 등을 elements라고 부름
- tag는 ```<></>```를 말함

## DOM
- 문서객체모델
- DOM은 html단위 하나하나를 객체로 생각하느 모델
- DOM은 트리구조

## dom 트리 확인
- document와 body, head는 부모-자식 관계
- body, head는 형제관계(sibling).  
```jsx
// 현재 dom 트리를 볼 수 있어요.
document

// dom 트리 중, body의 내용을 확인합니다.
document.body

// dom 트리 중, head의 내용을 확인합니다.
document.head
```

## 자식 요소 접근하기
- childNodes
```jsx
document.body.childNodes
```

- children
```jsx
document.body.children
```

- getElementsByTagName("태그 이름")
```
document.getElementsByTagName("div")
```

## Reference
- MDN 링크: https://developer.mozilla.org/ko/docs/Web/API/Document
