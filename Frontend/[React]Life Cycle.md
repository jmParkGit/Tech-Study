# Life Cycle
<img width="699" alt="image" src="https://user-images.githubusercontent.com/84515872/155947190-1e4bbd05-943f-45a1-8483-d09eb594d083.png">.  
- 컴포넌트가 렌더링을 준비하는 순간부터, 페이지에서 사라질 때까지가 라이프 사이클.
- 컴포넌트는 생성되고 -> 업데이트되고 -> 사라짐.  
- 생성은 처음으로 컴포넌트를 불러오는 단계.  
- 업데이트는 사용자의 행동(클릭, 데이터 입력)으로 데이터가 바뀌거나, 부모 컴포넌트가 렌더링할떄 업데이트 됨.  
  - props가 바뀔 때
  - state가 바뀔 때
  - 부모 컴포넌트가 업데이트 되었을 때(=리렌더링했을때)
  - 강제로 업데이트 했을 경우(forceUpdate()를 통해 강제로 컴포넌트를 업데이트를 할 수도 있음)
 - 제거는 페이지를 이동하거나, 사용자의 행동(삭제 버튼 클릭 등)으로 인해 컴포넌트가 화면에서 사라지는 단계

## Reference
- https://ko.reactjs.org/docs/react-component.html
- https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/
