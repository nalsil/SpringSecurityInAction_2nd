인증을 위한 테스트 방법
=============================
Basic Auth을 헤더에 직접 삽입하여 인증으로 사용하는 방법은 아래와 같습니다.

1. 인증과 관련한 정보(username, password)를 base64로 인코딩 합니다.
```
echo -n user:d1f329f5-f1f8-463f-ad28-c58576529802 | base64
```

2. 다음과 같이 base64로 반환: 
```
dXNlcjpkMWYzMjlmNS1mMWY4LTQ2M2YtYWQyOC1jNTg1NzY1Mjk4MDI=
```

3. Base64인코딩 값을 Authorization호출의 헤더 값으로 사용하여 호출, 
postman에서는 인증 탭이 아닌 헤드의 key/value에서 key에는 "Authorization"을 value에는 "Basic dXNlcjpkMWYzMjlmNS1mMWY4LTQ2M2YtYWQyOC1jNTg1NzY1Mjk4MDI="
을 사용하여 인증처리를 할 수 있습니다.

```
curl -H "Authorization: Basic dXNlcjpkMWYzMjlmNS1mMWY4LTQ2M2YtYWQyOC1jNTg1NzY1Mjk4MDI="  localhost:8080/hello
```

