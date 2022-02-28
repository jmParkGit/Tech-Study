# redux
- 리덕스는 상태관리 라이브러리
- 전역 상태관리를 편히할수 있음
- 리덕스 패키지 설치하기
```Shell
yarn add redux react-redux
```

## redux의 상태흐름도
![image](https://user-images.githubusercontent.com/84515872/155952305-00c192a6-bb0e-411c-9cce-8e8a57b4ba7d.png).   
(1) 리덕스 store를 Component에 연결한다.   
(2) Component에서 상태변화가 필요할 때, Action을 부른다.   
(3) Reducer를 통해서 새로운 상태값을 만듬.   
(4) 새 상태값을 Store에 저장.  
(5) Component는 새로운 상태값을 받아옴.(props를 통해 받아옴, 즉 다시 랜더린됨).  

## 리덕스 개념 및 용어
(1) State
- 리덕스에서 저장하고 있는 상태값(데이터)를 state라고 함
- 딕셔너리({key:value})형태로 보관

(2) Action
- 상태 변화가 필요할때(데이터를 변경할때) 발생
```jsx
{type: 'CHANGE_STATE', data: {...}}
```

(3) ActionCreator
- 액션 생성함수
- 액션을 만들기 위해 사용
```jsx
const changeState = (new_data) => {
	return {
		type: 'CHANGE_STATE',
		data: new_data
	}
}
```

(4) Reducer
- 리덕스에 저장된 상태(데이터)를 변경하는 함수
- 액션생성함수 호출 -> 액션 만들기 -> 리듀서가 현재상태(데이터)와 액션을 받음 -> 새로운 데이터 생성 -> 리턴
```jsx
const initialState = {
	name: 'mean0'
}

function reducer(state = initialState, action) {
	switch(action.type){
		case CHANGE_STATE: 
			return {name: 'mean1'};

		default: 
			return false;
	}	
}
```

(5) Store
- 리듀서, 현재 어플리케이션 상태, 리덕스에서 값을 가져오고 액션을 호출하기 위한 몇가지 내장 함수가 포함
- 생김새는 딕셔너리 혹은 json처럼 생김
- 내장함수는 공식문서에처 살펴볼것!

(6) dispacth
- 디스패치는 액션을 발생시키는 역활을 함
```jsx
dispatch(action); 
```

## 리덕스 특징
- store는 1개만 사용
- store의 state(데이터)는 오직 action으로만 변경할 수 있음
- 리듀서는 순수한 함수여야함.

## Reference
- https://ko.redux.js.org/introduction/getting-started/
