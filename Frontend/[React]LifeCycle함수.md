# LifeCycle함수
- 라이프 사이클 함수는 클래스형 컴포넌트에서만 사용가능

## constructor()
- 생성자
- 컴포넌트가 생성되면 가장 처음 호출됨

## render()
- 컴포넌트의 모양을 정의
- state, props에 접근해서 데이터를 보여줄 수 있음
- state, props를 render에서 수정하면 안됨

## componentDidMount()
- 컴포넌트가 화면에 나타나는것을 Mount한다 라고 함.
- 이 함수는 첫번째 렌더링을 마친 후에 딱 한번만 실행
- 컴포넌트가 리렌더링할 때는 실행 안됨
- componentDidMount()함수 안에서, ajax요청, 이벤트 등록, 함수 호출 등 작업
- 가상돔이 실제돔으로 올라간 후이므로, DOM관련 처리해도 됨

##  componentDidUpdate(prevProps, prevState, snapshot)
- DidUpdate는 리렌더링을 완료한 후 실행되는 함수
- prevProps와 prevState는 업데이트되기전 props, state
- 가상돔이 실제돔으로 올라간 후여서, DOM관련 처리 해도됨.

## componentWillUnmount()
- 컴포넌트가 DOM에거 제거될떄 실행하는 함수
- 만약 스크롤 위치를 추적중이거나, 이벤트 리스너를 등록했다면, 이 함수에서 해제를 해줘야됨.

## Reference
- https://ko.reactjs.org/docs/react-component.html
