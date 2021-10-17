# React Native,JSX 문법 소개

## 1. React Native란
- React Native는 페이스북에서 만든 오픈소스 모바일 어플리케이셔 프레임워크
- Javascript로 개발 가능
- 하나의 언어로 IOS와 안드로이드 모바일 앱 동시개발 가능
- [reactnative 홈페이지](https://reactnative.dev/)   

## 2. Expo 란
- React Native로 개발을 할때 Expo를 이용해서 쉽게 앱을 테스트용으로 실행시켜볼수 있다.
- [expo 홈페이지](https://expo.dev)
- 아래 Node,NPM install에 필요한 명령어는 Expo reference에 존재

- Node와 NPM
  - Node.js로 자바스크립트 개발환경 구축
  - NPM으로 필요한 자바스크립트 앱 개발도구를 가져옴

- Yarn
  - Yarn은 npm보다 가볍게 자바스크립트 패키지 관리하게 하는 패키지 매니저 툴

- local pc에 Expo계정 설정하기

```console
expo login --username "Expo 사이트 가입당시 입력한 name"
```

- Expo 프로젝트 기본 폴더구조   
<img width="186" alt="스크린샷 2021-10-18 오전 3 14 39" src="https://user-images.githubusercontent.com/84515872/137639769-df9fe1f2-504b-4067-a961-c78887b3f2b7.png">.  

  - assets: 앱의 이미지 및 아이콘 파일을 담는 폴더
  - node_modules: 각종 라이브러리가 저장됨
  - App.js: main함수라고 생각하면됨
  - app.json: 앱 이름, 버전 등의 앱 기본정보를 설정하는 파일

- Expo실행 명령어
  - Expo 명령어 설치
  - 로컬에 Expo계정 세팅
  - expo init 명령어로 기본 앱 생성
  - expo start로 Expo앱 실행
  - 휴대폰의 Expo 클라이언트 앱으로 Expo앱 실행

- jSX문법에서 tag의 스타일을 주는 방식은 html의 css를 연상시킴.

-[style_official_document](https://reactnative.dev/docs/style#docsNav)

-예제코드   
![KakaoTalk_20211018_024117768](https://user-images.githubusercontent.com/84515872/137639542-c202ba7b-79da-4c8a-bbc5-6ebbb0934ba2.jpg)   
[예제코드 링크](https://github.com/jmParkGit/sparta-myhoneytip-jm/blob/main/pages/AboutPage.js)


