브라우저란
사용자가 웹사이트를 볼 수 있게 해주는 프로그램
ex) google, chrome, safari, microsoft edge

브라우저가 하는 일
1. 사용자가 URL 입력
2. 서버에 요청(Request) 보냄
3. 서버로부터 응답(Response)을 받음
4. 브라우저가 화면에 출력

예시

* 사용자가 google.com 접속
* 브라우저가 서버에 요청
* 서버가 HTML/CSS/JS 데이터를 응답
* 브라우저가 화면으로 보여줌

서버란
데이터를 처리하고 요청을 처리하는 컴퓨터

프론트엔드 서버
사용자에게 보이는 화면 담당

예시) 버튼,로그인 화면, 메뉴 화면

백엔드 서버
실제 데이터 처리 담당

예시) 로그인 검사, 데이터베이스 저장, 회원가입 처리

예시 흐름
1. 사용자가 로그인 버튼 클릭
2. 프론트엔드가 아이디/비밀번호를 백엔드 서버로 전달
3. 백엔드가 검사
4. 성공/실패 결과 응답
5. 프론트가 결과 화면 표시

req와 res
req(request)
클라이언트가 서버에게 보내는 요청 정보

req 객체 안 : 
URL
헤더(Header)
body
쿠키
요청 방식(GET/POST)
등이 들어있음

res(response)
서버가 클라이언트에게 보내는 응답 정보

HTTP란?
HTTP(Hyper Text Transfer Protocol)

웹에서 데이터를 주고받기 위한 통신 규칙(프로트콜)
-브라우저와 서버가 서로 대화하는 방법

특징
-요청 / 응답 구조
-TCP/ IP 기반
-웹 통신의 기본 규칙

HTTP 요청과 응답
HTTP 구조
HTTP
-request(요청)
-response (응답)
1.HTTP Request(요청)
구조
1.Start Line
2.Headers
3.Body

1 Start Line
	1.HTTP Method
	2.Request Target
	3.HTTP Version
1-1 HTTP Method 종류
- get (데이터 조회)
 특징
*서버 데이터 가져오기
*body 거의 사용 나함

- post (데이터 제출)
 특징
*서버 상태 변화 가능
*회원가입/로그인 등에 사용

- put (전체 수정)
 특징
*서버의 기존 데이터를 요청 데이터로 교체

-patch (부분 수정)
 특징
*데이터 일부만 수정

-delete (데이터 삭제)

-HEAD (헤더 정보만 요청)
 특징
body 없음

사용 이유) 파일 크기 확인, 서버 상태 확인, 수정 시간 확인

-OPTIONS (서버가 지원하는 통신 방식 확인)

-TRACE (요청이 서버까지 어떻게 전달됐는지 테스트)
ex) loop-back 테스트

과정
1.클라이언트가 TRACE요청
2.중간 서버들을 지나감
3.목적 서버 도착
4.서버가 받은 요청 그대로 다시 반환
5.비교 확인

-connect
클라이언트와 서버 사이 터널 연결

1-2 Request Target
요청을 보낼 주소

1-3 HTTP Version
HTTP 버전 표시
이유 : 버전에 따라 기능이나 구조가 달라질수가 있기 때문에

Headers
역할 : 추가 정보 영역
종류
-general headers
-request headers
-entity headers

주요 Header

- Host (접속하려는 서버 주소)

- User-Agent(브라우저 정보)

- Referer (직전에 방문한 페이지 주소)

- Accept (클라이언트가 받을 수 있는 데이터 종류)
ex) 이미지, 오디오, 어플리케이션

- If-Modified-Since (특정 시간 이후 수정됐는지 확인)
만약 수정이 안됨
304 Not Modified가 뜸
수정되면
새 body 전송

- Authorization(인증 토큰 전달)
로그인 인증 등에 사용

- Origin (요청이 시작된 주소)
다르면 CORS 문제 발생가능

- Cookie (쿠키 정보 저장)
key-value 형태로 저장이 됨

Body
역할 : 실제 데이터 영역
ex) 로그인 정보, 회원가입 정보, 폼 데이터

POST 요청에서 자주 사용


2.HTTP Response(응답)
구조
1. Status Line
2. Headers
3. Body

2-1 states Line
구성
1. HTTP Version
2. Status Code
3. Status Text

2-2 Headers
request의 headers와 동일함 
차이점은 서로 사용하는 용어가 다름

2-3 Body
response의 body와 일반적으로 동일함
특징
-모든 response가 body가 있지는 않음
-데이터를 전송할 필요가 없을경우에는 body가 비어있음

URL 구조
ex) https://google.com:443/search?q=test#section1
1. Protocol (Scheome) -> 통신 방식
ex) http, https


2. Host ->  도메인 주소
ex) google.com
*도메인이란 : IP 주소를 사람이 읽기 쉽게 만든 이름

3. Port -> 프로그램 구분 번호
ex) :443
IP = 건물 주소
Port = 방 번호

4. Path -> 사이트 내부 경로
ex) /search

5. Query String -> 추가 데이터 전달
ex) ?q=test
q -> key
test -> value

6.Fragment -> 페이지 내부 위치
ex) #section1

Origin(출처)
구성 : Protocol, Host, Port
ex) https://google.com:443

Header / Body
Header
추가 설명 데이터
ex) 브라우저 정보, 인증 정보, 쿠키, 데이터 타입

Body
실제 데이터

GET / POST
GET
데이터 조회
특징 : URL에 데이터 포함 가능, 조회용, 서버 상태 변화 적으머ㅓ

POST
데이터 전송
특징 : body 사용, 서버 상태 변경 가능