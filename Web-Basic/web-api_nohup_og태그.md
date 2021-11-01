# web-api, nohup, og태그

## web-API 예제
- API 정보
```
만들 API 정보는 아래와 같습니다.
 
A. 요청 정보
- 요청 URL= /api/like , 요청 방식 = POST
- 요청 데이터 : 영화인 이름(name_give)

B. 서버가 제공할 기능 :  영화인 이름(요청 데이터)과 일치하는 영화인 정보의 좋아요 수를 한 개 증가시켜 데이터베이스에 업데이트하고(Update), 성공했다고 응답 메세지를 보냄 

C. 응답 데이터  : (JSON 형식) 'msg'='좋아요 완료!'
```
- server
```python
@app.route('/api/like', methods=['POST'])
def like_star():
    name_receive = request.form['name_give'];
    target_star = db.mystar.find_one({'name': name_receive});
    current_like = target_star['like'];

    new_like=current_like+1;

    db.mystar.update_one({'name': name_receive}, {'$set': {'like': new_like}})

    return jsonify({'msg': '좋아요 완료!'})
```
- client
```javascript
function likeStar(name) {
                $.ajax({
                    type: 'POST',
                    url: '/api/like',
                    data: {name_give:name},
                    success: function (response) {
                        alert(response['msg']);
                        window.location.reload();
                    }
                });
            }
```

## nohup 설정하기
- 원격 접속을 종료하더라도 서버가 계속 돌아가게하기
```shell
nohup python app.py &
```
-서버 종료하기 (강제종료하는 방법)
```shell
# 아래 명령어로 미리 pid 값(프로세스 번호)을 본다
ps -ef | grep 'app.py'

# 아래 명령어로 특정 프로세스를 죽인다
kill -9 [pid값]
```

## og태그
- OG tag는 SNS나 메신저에 링크르 공유할때나오는 미리보기 화면
- HTML의 `<head>~</head>`사이에 아래 내용을 넣으면 됨
- 예제
```
<meta property="og:title" content="원페이지쇼핑몰" />
<meta property="og:description" content="연필를 팔아요!!" />
<meta property="og:image" content="{{ url_for('static', filename='ogimage.png') }}" />
```
- 페이스북 og태그 초기화 하기
```
https://developers.facebook.com/tools/debug/
```
-카카오톡 og태그 초기호 하기
```
https://developers.kakao.com/tool/clear/og
```
