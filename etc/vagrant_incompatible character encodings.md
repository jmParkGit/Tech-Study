# Encoding::CompatibilityError: incompatible character encodings: UTF-8 and CP-949
- 윈도우에서 ```vargant up```시 위 에러가 나면, 경로에 한글이 있어서일 경우가 많음
## 해결방법 1
- 영어로 된 사용자 계정을 만들고 그곳에서 ```vargant up```
## 해결방법 2
- 기존 (C:\USER\사용자명\...)아래에 있던 .vagrant.d 폴더를 영어로만 된 경로로 이동.
- 윈도우에서 환경변수 ```VAGRANT_HOME``` 생성   
![image](https://user-images.githubusercontent.com/84515872/150996658-3b326bab-4e57-4d36-b362-9798297cf817.png)

