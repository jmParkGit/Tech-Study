# React Native,JSX 문법 소개

1. React Native란
- React Native는 페이스북에서 만든 오픈소스 모바일 어플리케이셔 프레임워크
- Javascript로 개발 가능
- 하나의 언어로 IOS와 안드로이드 모바일 앱 동시개발 가능
- [Link](https://reactnative.dev/)

2. Expo 란
- React Native로 개발을 할때 Expo를 이용해서 쉽게 앱을 테스트용으로 실행시켜볼수 있다.
- [Link](https://expo.dev)
- 아래 1)번,2)번 install에 필요한 명령어는 Expo reference에 존재

```
1)Node와 NPM
- Node.js로 자바스크립트 개발환경 구축
- NPM으로 필요한 자바스크립트 앱 개발도구를 가져옴

2)Yarn
- Yarn은 npm보다 가볍게 자바스크립트 패키지 관리하게 하는 패키지 매니저 툴
```

- local pc에 Expo계정 설정하기

```console
expo login --username "Expo 사이트 가입당시 입력한 name"
```

- Expo 프로젝트 기본 폴더구조
//사진
```
1)assets
- 앱의 이미지 및 아이콘 파일을 담는 폴더
2)node_modules
- 각종 라이브러리가 저장됨
3)App.js
- main함수라고 생각하면됨
4)app.json
- 앱 이름, 버전 등의 앱 기본정보를 설정하는 파일
```


- Expo실행 명령어
```console
1)Expo 명령어 설치
2)로컬에 Expo계정 세팅
3)expo init 명령어로 기본 앱 생성
4)expo start로 Expo앱 실행
5)휴대폰의 Expo 클라이언트 앱으로 Expo앱 실행
```

- jSX문법에서 tag의 스타일을 주는 방식은 html의 css를 연상시킴.

-[style_official_document](https://reactnative.dev/docs/style#docsNav)

-[예제코드](https://github.com/jmParkGit/sparta-myhoneytip-jm/blob/main/pages/AboutPage.js)


