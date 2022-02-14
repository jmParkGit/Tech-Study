# [Spring]Gradle로 빌드 후 서비스 시작하기
- 아래 설명에서 사용한 IDE는 IntelliJ IDEA

## 배포 파이 빌드하기
- Gradle 탭에서 빌드하기.  
![image](https://user-images.githubusercontent.com/84515872/151196172-dbef28fc-bb54-4305-a7b4-e54ae1821dfa.png)
- .jar 파일 확인하기.  
![image](https://user-images.githubusercontent.com/84515872/151196341-321d26f0-eab7-4c0b-863b-99c242234840.png)

## 서비스 실행하기
- 명령어
```Shell
java -jar {JAR파일명.jar}
```
- nohup 사용시
```Shell
nohup java -jar {JAR파일명.jar} &
```
