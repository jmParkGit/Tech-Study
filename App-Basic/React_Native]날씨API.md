# 날씨 API
## 1.API사용
- [날씨관련 API 공식문서 링크](https://openweathermap.org/api)
- [데이터 받아오기 예제 링크](https://openweathermap.org/current)
- axios설치
```shell
yarn add axios
```
- code 예제
``` jsx
import * as Location from "expo-location";
import axios from "axios"

const getLocation = async () => {
    //수많은 로직중에 에러가 발생하면
    //해당 에러를 포착하여 로직을 멈추고,에러를 해결하기 위한 catch 영역 로직이 실행
    try {
      //자바스크립트 함수의 실행순서를 고정하기 위해 쓰는 async,await
      await Location.requestPermissionsAsync();
      const locationData= await Location.getCurrentPositionAsync();
      const latitude = locationData['coords']['latitude']
      const longitude = locationData['coords']['longitude']
      const API_KEY = "cfc258c75e1da2149c33daffd07a911d";
      const result = await axios.get(
        `http://api.openweathermap.org/data/2.5/weather?lat=${latitude}&lon=${longitude}&appid=${API_KEY}&units=metric`
      );

      const temp = result.data.main.temp; 
      const condition = result.data.weather[0].main
      
      console.log(temp)
      console.log(condition)

      //오랜만에 복습해보는 객체 리터럴 방식으로 딕셔너리 구성하기!!
      setWeather({
        temp,condition
      })

    } catch (error) {
      //혹시나 위치를 못가져올 경우를 대비해서, 안내를 준비합니다
      Alert.alert("위치를 찾을 수가 없습니다.", "앱을 껏다 켜볼까요?");
    }
  }
  
 //...
  <Text style={styles.weather}>오늘의 날씨: {weather.temp + '°C   ' + weather.condition} </Text>
 
```

- 날씨 API에서 전달해주는 데이터 모습
```jsx
Object {
  "config": Object {
    "adapter": [Function xhrAdapter],
    "data": undefined,
    "headers": Object {
      "Accept": "application/json, text/plain, */*",
    },
    "maxContentLength": -1,
    "method": "get",
    "timeout": 0,
    "transformRequest": Array [
      [Function transformRequest],
    ],
    "transformResponse": Array [
      [Function transformResponse],
    ],
    "url": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "validateStatus": [Function validateStatus],
    "xsrfCookieName": "XSRF-TOKEN",
    "xsrfHeaderName": "X-XSRF-TOKEN",
  },
  "data": Object {
    "base": "stations",
    "clouds": Object {
      "all": 90,
    },
    "cod": 200,
    "coord": Object {
      "lat": 37.42,
      "lon": -122.08,
    },
    "dt": 1595942079,
    "id": 5375480,
    "main": Object {
      "feels_like": 15.72,
      "humidity": 82,
      "pressure": 1013,
      "temp": 15.4,
      "temp_max": 16.11,
      "temp_min": 14.44,
    },
    "name": "Mountain View",
    "sys": Object {
      "country": "US",
      "id": 5122,
      "sunrise": 1595941783,
      "sunset": 1595992779,
      "type": 1,
    },
    "timezone": -25200,
    "visibility": 10000,
    "weather": Array [
      Object {
        "description": "overcast clouds",
        "icon": "04d",
        "id": 804,
        "main": "Clouds",
      },
    ],
    "wind": Object {
      "deg": 312,
      "speed": 0.58,
    },
  },
  "headers": Object {
    "access-control-allow-credentials": "true",
    "access-control-allow-methods": "GET, POST",
    "access-control-allow-origin": "*",
    "cache-control": "public, max-age=0",
    "connection": "keep-alive",
    "content-length": "477",
    "content-type": "application/json; charset=utf-8",
    "date": "Tue, 28 Jul 2020 13:16:24 GMT",
    "server": "openresty",
    "x-cache-key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
  },
  "request": XMLHttpRequest {
    "DONE": 4,
    "HEADERS_RECEIVED": 2,
    "LOADING": 3,
    "OPENED": 1,
    "UNSENT": 0,
    "_aborted": false,
    "_cachedResponse": undefined,
    "_hasError": false,
    "_headers": Object {
      "accept": "application/json, text/plain, */*",
    },
    "_incrementalEvents": false,
    "_lowerCaseResponseHeaders": Object {
      "access-control-allow-credentials": "true",
      "access-control-allow-methods": "GET, POST",
      "access-control-allow-origin": "*",
      "cache-control": "public, max-age=0",
      "connection": "keep-alive",
      "content-length": "477",
      "content-type": "application/json; charset=utf-8",
      "date": "Tue, 28 Jul 2020 13:16:24 GMT",
      "server": "openresty",
      "x-cache-key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
    },
    "_method": "GET",
    "_requestId": null,
    "_response": "{\"coord\":{\"lon\":-122.08,\"lat\":37.42},\"weather\":[{\"id\":804,\"main\":\"Clouds\",\"description\":\"overcast clouds\",\"icon\":\"04d\"}],\"base\":\"stations\",\"main\":{\"temp\":15.4,\"feels_like\":15.72,\"temp_min\":14.44,\"temp_max\":16.11,\"pressure\":1013,\"humidity\":82},\"visibility\":10000,\"wind\":{\"speed\":0.58,\"deg\":312},\"clouds\":{\"all\":90},\"dt\":1595942079,\"sys\":{\"type\":1,\"id\":5122,\"country\":\"US\",\"sunrise\":1595941783,\"sunset\":1595992779},\"timezone\":-25200,\"id\":5375480,\"name\":\"Mountain View\",\"cod\":200}",
    "_responseType": "",
    "_sent": true,
    "_subscriptions": Array [],
    "_timedOut": false,
    "_trackingName": "unknown",
    "_url": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "readyState": 4,
    "responseHeaders": Object {
      "Access-Control-Allow-Credentials": "true",
      "Access-Control-Allow-Methods": "GET, POST",
      "Access-Control-Allow-Origin": "*",
      "Cache-Control": "public, max-age=0",
      "Connection": "keep-alive",
      "Content-Length": "477",
      "Content-Type": "application/json; charset=utf-8",
      "Date": "Tue, 28 Jul 2020 13:16:24 GMT",
      "Server": "openresty",
      "X-Cache-Key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
    },
    "responseURL": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "status": 200,
    "timeout": 0,
    "upload": XMLHttpRequestEventTarget {},
    "withCredentials": true,
  },
  "status": 200,
  "statusText": undefined,
}
Object {
  "config": Object {
    "adapter": [Function xhrAdapter],
    "data": undefined,
    "headers": Object {
      "Accept": "application/json, text/plain, */*",
    },
    "maxContentLength": -1,
    "method": "get",
    "timeout": 0,
    "transformRequest": Array [
      [Function transformRequest],
    ],
    "transformResponse": Array [
      [Function transformResponse],
    ],
    "url": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "validateStatus": [Function validateStatus],
    "xsrfCookieName": "XSRF-TOKEN",
    "xsrfHeaderName": "X-XSRF-TOKEN",
  },
  "data": Object {
    "base": "stations",
    "clouds": Object {
      "all": 90,
    },
    "cod": 200,
    "coord": Object {
      "lat": 37.42,
      "lon": -122.08,
    },
    "dt": 1595942079,
    "id": 5375480,
    "main": Object {
      "feels_like": 15.72,
      "humidity": 82,
      "pressure": 1013,
      "temp": 15.4,
      "temp_max": 16.11,
      "temp_min": 14.44,
    },
    "name": "Mountain View",
    "sys": Object {
      "country": "US",
      "id": 5122,
      "sunrise": 1595941783,
      "sunset": 1595992779,
      "type": 1,
    },
    "timezone": -25200,
    "visibility": 10000,
    "weather": Array [
      Object {
        "description": "overcast clouds",
        "icon": "04d",
        "id": 804,
        "main": "Clouds",
      },
    ],
    "wind": Object {
      "deg": 312,
      "speed": 0.58,
    },
  },
  "headers": Object {
    "access-control-allow-credentials": "true",
    "access-control-allow-methods": "GET, POST",
    "access-control-allow-origin": "*",
    "cache-control": "public, max-age=0",
    "connection": "keep-alive",
    "content-length": "477",
    "content-type": "application/json; charset=utf-8",
    "date": "Tue, 28 Jul 2020 13:16:24 GMT",
    "server": "openresty",
    "x-cache-key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
  },
  "request": XMLHttpRequest {
    "DONE": 4,
    "HEADERS_RECEIVED": 2,
    "LOADING": 3,
    "OPENED": 1,
    "UNSENT": 0,
    "_aborted": false,
    "_cachedResponse": undefined,
    "_hasError": false,
    "_headers": Object {
      "accept": "application/json, text/plain, */*",
    },
    "_incrementalEvents": false,
    "_lowerCaseResponseHeaders": Object {
      "access-control-allow-credentials": "true",
      "access-control-allow-methods": "GET, POST",
      "access-control-allow-origin": "*",
      "cache-control": "public, max-age=0",
      "connection": "keep-alive",
      "content-length": "477",
      "content-type": "application/json; charset=utf-8",
      "date": "Tue, 28 Jul 2020 13:16:24 GMT",
      "server": "openresty",
      "x-cache-key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
    },
    "_method": "GET",
    "_requestId": null,
    "_response": "{\"coord\":{\"lon\":-122.08,\"lat\":37.42},\"weather\":[{\"id\":804,\"main\":\"Clouds\",\"description\":\"overcast clouds\",\"icon\":\"04d\"}],\"base\":\"stations\",\"main\":{\"temp\":15.4,\"feels_like\":15.72,\"temp_min\":14.44,\"temp_max\":16.11,\"pressure\":1013,\"humidity\":82},\"visibility\":10000,\"wind\":{\"speed\":0.58,\"deg\":312},\"clouds\":{\"all\":90},\"dt\":1595942079,\"sys\":{\"type\":1,\"id\":5122,\"country\":\"US\",\"sunrise\":1595941783,\"sunset\":1595992779},\"timezone\":-25200,\"id\":5375480,\"name\":\"Mountain View\",\"cod\":200}",
    "_responseType": "",
    "_sent": true,
    "_subscriptions": Array [],
    "_timedOut": false,
    "_trackingName": "unknown",
    "_url": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "readyState": 4,
    "responseHeaders": Object {
      "Access-Control-Allow-Credentials": "true",
      "Access-Control-Allow-Methods": "GET, POST",
      "Access-Control-Allow-Origin": "*",
      "Cache-Control": "public, max-age=0",
      "Connection": "keep-alive",
      "Content-Length": "477",
      "Content-Type": "application/json; charset=utf-8",
      "Date": "Tue, 28 Jul 2020 13:16:24 GMT",
      "Server": "openresty",
      "X-Cache-Key": "/data/2.5/weather?lat=37.42&lon=-122.08&units=metric",
    },
    "responseURL": "http://api.openweathermap.org/data/2.5/weather?lat=37.4219284&lon=-122.0839242&appid=cfc258c75e1da2149c33daffd07a911d&units=metric",
    "status": 200,
    "timeout": 0,
    "upload": XMLHttpRequestEventTarget {},
    "withCredentials": true,
  },
  "status": 200,
  "statusText": undefined,
}
```

