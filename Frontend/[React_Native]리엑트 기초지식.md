# 리엑트 기초지식

## 기초지식
![image](https://user-images.githubusercontent.com/84515872/139265639-2aa9edbd-92bb-419d-85de-a55101368d50.png)
- Component: 정해진 엘리먼트들(요소)를 사용하여 만든 화면의 일부분
  - 버튼 하나가 컴포넌트가 될수도 있고, 버튼으 모아두 영역이 컴포넌트가 될수도 있다.
  - 코드 재사용 용이
  ![image](https://user-images.githubusercontent.com/84515872/139266882-cc88b4d8-ea04-455e-9e13-4c883812c188.png)

- State,useState: component에서 데이터랄 유지하고 관리하기 위한 유일한 방법.
  - Component마다 데이터를 보유하고 관리할수 있습니다.
  - react에서 state는 react library에서 제공해주는 useState로 생성하고, setState 함수로 정/변경 할수 있습니다.
  - UI=component(state)
  - 화면이 그려진 다음 가자 먼저 실행되는 함수, useEffect.  
  ![image](https://user-images.githubusercontent.com/84515872/139267918-ba10ad24-30a3-4ef0-8dca-9b0ca8146422.png)

- Props: 상위 컴포넌트에서 하우 컴포넌트로 데이터르 전달하는 방식
  - 예로 들어 <Text>태그엔 nujmberOfLines이란 속성(Props)
  - <Image> 태그엔 resizeMode란 속성이 있다.
  - useEffect: 화면에 component가 그려면 처음 실행해야 하는 함수들을 모아두는 곳
  
  ```jsx
  useEffect(()=>{

	...화면이 그려진 다음 가장 먼저 실행되야 할 코드 작성 공간

  },[])
  ```

## 기타
- StatusBar: [공식문서](https://docs.expo.dev/versions/latest/sdk/status-bar/)
- navigate: [공식문서](https://reactnavigation.org/)
- stack navigation:
  ![image](https://user-images.githubusercontent.com/84515872/139271199-bda71700-f2f3-433b-a706-389b724d0d6c.png)
- 페이지 내용 공유하기
  ```jsx
  import { Share } from "react-native";
  ```
- 외부 링크 클릭 이벤트
  ```jsx
  import * as Linking from 'expo-linking';
  ```
  
- [Code Example](https://github.com/jmParkGit/sparta-myhoneytip-jm)

## Reference
- [스파르타코딩클럽] 앱개발 종합반 - 3주차 강의자료
