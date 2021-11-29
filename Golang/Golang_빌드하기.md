# Golang 빌드하기

## 1. source code
```Go
package main

import "fmt"

func main() {
	fmt.Println("hello world");
}
```

## 2. 관련 명령어
- go fmt
  - 소스 코드 형식을 Go 표준 포멧형식으로 정렬
- go run
  - 소스코드를 바로 컴파일한 다음 바로 실행 (그러나, 컴파일된 실행 파일은 저장되지 않음)
 - go build
  - 바이너리파일로 컴파일

## 3. 예제
- go run 이용
```shell
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main  cat helloworld.go
package main

import "fmt"

func main() {
	fmt.Println("hello world");
}
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main  go run helloworld.go
hello world
```
- 바이너리 빌드 후 실행
```shell
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main  cat helloworld.go
package main

import "fmt"

func main() {
	fmt.Println("hello world");
}
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main  go fmt helloworld.go
helloworld.go
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main ±  go build helloworld.go
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main ±  ls
helloworld    helloworld.go
 parkjaemin@bagjaemin-ui-MacBookAir  ~/workspace/coding/Programming_with_Google_Go/Getting_Started_with_Go/week1   main ±  ./helloworld
hello world
```
