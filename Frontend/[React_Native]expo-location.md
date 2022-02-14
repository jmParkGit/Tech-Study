# ]expo-location
## 1. 앱 위치 정보 권한 설정
- [expo-location 공식문서 링크](https://docs.expo.dev/versions/latest/sdk/location/)
```shell
expo install expo-location

````
- code 예제
``` jsx
import * as Location from "expo-location";

const getLocation = async () => {
    //수많은 로직중에 에러가 발생하면
    //해당 에러를 포착하여 로직을 멈추고,에러를 해결하기 위한 catch 영역 로직이 실행
    try {
      //자바스크립트 함수의 실행순서를 고정하기 위해 쓰는 async,await
      await Location.requestPermissionsAsync();
      const locationData= await Location.getCurrentPositionAsync();
      console.log(locationData['coords']['latitude'])
      console.log(locationData['coords']['longitude'])

    } catch (error) {
      //혹시나 위치를 못가져올 경우를 대비해서, 안내를 준비합니다
      Alert.alert("위치를 찾을 수가 없습니다.", "앱을 껏다 켜볼까요?");
    }
  }
```
- 
