# JWT / Json Web Token
- 인증에 필요한 정보들을 암호화시킨 토큰
- Access Token을 HTTP 헤더에 실어 서버로 보내게 된다.
- 토큰을 만들기 위해 Header, Payload, Verify Signature이 필요하다.

## JWT 인증 과정
1. 사용자가 로그인을 한다.
2. 서버에서 계정정보를 읽어 고유한 사용자의 ID값을 부여하고 기타 정보와 payload에 넣는다.
3. JWT 토큰의 유효시간을 설정한다.
4. SECRET KEY를 이용해 ACCESS TOKEN을 발급한다.
5. 사용자는 ACCESS TOKEN을 받아 저장하고 인증이 필요한 요청마다 TOKEN을 HTTP header에 담아 보낸다.
6. 서버에서 TOKEN의 Verify Signature을 SECRET KEY로 복호화하고 조작 여부, 유효기간을 확인한다.
7. 검증이 완료되면 Payload를 디코딩하여 사용자의 ID에 맞는 데이터를 가져온다.

## ACCESS TOKEN의 단점
- 이미 발급된 JWT에 대해서 돌이킬 수 없다.
- JWT는 한 번 발급되면 유효기간이 완료될 때까지 계속 사용 가능하다.
- 따라서 악의적인 사용자가 유효기간이 지나기 전까지 정보를 악의적으로 사용 가능하다.

### 해결책
- Access Token의 유효기간을 짧게 하고 Refresh Token이라는 새로운 토큰을 발급한다.
- 위 방법을 사용하면 Access Token을 탈취당해도 상대적으로 피해를 줄일 수 있다.

## 기본 JWT 방식의 강화버전 / Access Token & Refresh Token
- JWT 인증 방식의 문제는 만약 제 3자에게 탈취당할 경우 보안에 취약하다는 점이다.
- 유효기간이 짧은 Token의 경우 그만큼 사용자는 로그인을 자주하여 새롭게 Token을 발급해야 하므로 불편하다.
- 유효기간을 늘리면 토큰을 탈취당했을 때 보안에 더 취약해지게 된다.
- 유효기간을 짧게 하면서 좋은 방법이 바로 Refresh Token이다.

### Refresh Token
- Refresh Token Access Token과 같은 형태 JWT
- 처음 로그인을 완료했을 때 Access Token과 동시에 발급된다.
- 긴 유효기간을 가지면서, Access Token이 만료(유효기간이 지남) 되었을 때 새로 발급해주는 열쇠가 된다.
ex)
- Refresh Token의 유효기간이 2주, Access Token의 유효기간이 1시간
- 1시간이 지나 Access Token이 만료되었을 때, Refresh Token의 유효기간 전까지는 Access Token을 새롭게 발급받을 수 있다.

### Access Token & Refresh Token 사용 과정
1. 사용자가 로그인한다.
2. 서버의 회원 DB에서 값을 비교한다.
3. 로그인이 완료되면 Access Token, Refresh Token을 발급한다. 이 때 일반적으로 회원 DB에 Refresh Token을 저장해 둔다.
4. 사용자는 Refresh Token을 안전한 저장소에 저장 한 후, Access Token을 헤더에 실어 요청을 보낸다.
5. Access Token을 검증하여 Token에 맞는 데이터를 보낸다.
6. Access Token의 유효기간이 만료된다.
7. 사용자는 이전과 동일하게 Access Token을 헤더에 실어 요청을 보낸다.
8. 서버는 Access Toen이 만료됨을 확인하고 권한없음을 신호로 보낸다.
9. 사용자는 Access Token을 새로 발급하기 위해 Access Token, Refresh Token을 서버로 보낸다.
10. 서버는 받은 Access Token이 조작되지 않았는지 확인한 후 Refresh Token과 사용자의 DB에 저장되어 있던 Refresh Token을 비교한다.
11. Token이 동일하고 유효기간도 지나지 않았다면 새로운 Access Token을 발급한다.
12. 서버는 새로운 Access Token을 헤더에 실어 다시 API 요청을 진행한다.


