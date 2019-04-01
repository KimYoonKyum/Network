## HTTP(HyperText Transfer Protocol)
  * 웹상에서 클라이언트에서 서버까지 일련의 흐름을 결정하는 프로토콜(80번 포트 사용)
  * Application 계층에 속하는 프로토콜로 TCP/IP 위에서 동작한다.
  * Connectionless, Stateless 프로토콜이다.
    - Connectionless(비연결형)
      + 클라이언트가 서버에 요청을하고 서버가 클라이언트에게 응답을 보내면 연결은 끊어진다.
    - Stateless
      + 리퀘스트, 리스폰스 교환시에 상태를 관리안함. 즉, 이전에 보냈던 리스폰스나 리퀘스트에 대한 정보가 없다.
  * URI(Uniform Resource Identifier)를 사용하여 인터넷 상의 리소스를 지정한다.
    - URI는 리소스를 식별하기 위해 문자열 전반을 나타내고 URL은 리소스의 장소를 나타낸다. 즉, URL은 URI의 서브셋이다.
    - https://www.newalpha7.com 이라는 주소는 URL 이면서 URI이라고 할 수 있다. newalpha7.com 서버를 가리키기 때문,  
      https://www.newalpha7.com/new.md도 URI 이면서 URL 이라고 할 수 있다. newalpha7.com 서버의 new.md의 위치를  
      가리키기 때문이다. 그렇지만, https://www.newalpha7.com/ID=123 은 URI 이지만 URL 이라고 할 수 없다. 내가 원하는  
      위치에 도달하기 위해 ID=123 이라는 식별자(Identifier)를 썼기 때문이다.  
      즉, URL(Uniform Resource Locator)는 어떤 파일의 구체적인 위치이고, URI는 요청하는 주소가 파일이라고 하기보다는  
      구분자로 보는 것이다.
      
## HTTP Method(HTTP 1.1에서 지원하는 것만)
  * GET : 리소스 획득(URL에 해당하는 리소스 요구)
  * POST : 서버가 처리할 수 있는 자료를 전송하기 위해 사용.
  * PUT : 파일을 URL에 해당하는 곳에 저장하도록 요구.
  * HEAD : GET과 같은 기능이지만, 메세지 바디를 돌려주지 않는다.meta-information(유효성, 갱신시간 등)만 받는다.
  * DELETE : 해당 URL의 파일을 삭제.
  * TRACE : web 서버에 접속하여 자신에게 통신을 되돌려 받는 루프백 발생. 프록시 등을 중계하여 오리진 서버에 접속할 때 동작 확인하기위해 사용.
  * CONNECT : 프록시에 터널 접속 확립 요구, TCP 통신을 터널링 시키기 위해 사용.

## HTTP Message
  * HTTP에서 교환하는 정보는 HTTP Message라고 불리는데 Request Message와 Response Message로 나뉜다.
  * HTTP Message는 복수 행(CR+LF로 개행)의 데이터로 구성된 텍스트 문자열이다.
  * HTTP Message 구성
    - Message Header : 서버와 클라이언트가 꼭 처리해야하는 리퀘스트와 리스폰스 내용과 속성.
    - CR + LF : CR(Carrige return, 16진수 0x0d)와 LF(Line Feed: 16진수 0x0a)
    - Message Body : 꼭 전송되어야 하는 데이터 그 자체.
## HTTP 상태 코드
  * 클라이언트가 서버를 향해 리퀘스트를 보낼 때 서버에서 그 결과가 어떻게 처리되었는지 알려주는 것이 상태 코드.
  * 200 : 리퀘스트가 정상적으로 처리되었음.
  * 3XX : 리다이렉트, 리퀘스트가 정상적으로 처리를 종료하기 위해 브라우저 측에서 특별한 처리를 수행해야함을 알림.
  * 400 : bad request, 리퀘스트 구문이 잘 못되었음.
  * 401 : 인증이 필요함을 알림.
  * 403 : 리소스의 액세스가 거부됨.
  * 404 : 리퀘스트에 대한 리소스가 없음.
  * 500 : 서버에서 리퀘스트를 처리하는 동안에 에러가 발생했음.
  * 503 : 서버가 과부하 상태이거나 점검중이기 때문에 리퀘스트 처리 할 수 없음을 알림.
