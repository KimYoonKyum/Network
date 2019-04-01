## TCP/IP
  * 인터넷에 연결된 컴퓨터들이 데이터를 주고 받을 수 있도록 하는 표준 프로토콜
  * 구조
    - Application(osi 7의 application,presentation,session 계층 3개를 합쳐놓은 것에 해당)
      + telnet, ftp, http
    - Transport
      + tcp,udp
    - Network
      + ip
    - DataLink
  
## TCP(Transmission Control Protocol)
  * OSI 7 Layer 중에서 Transport Layer에서 사용하는 프로토콜로, 신뢰성있는 바이트 스트림 서비스를 제공한다.  
    (바이트 스트림 : 용량이 큰 데이터를 보내기 쉽게 TCP세그먼트라고 불리는 단위 패킹으로 작게 분해하여 관리하는 것)
  * TCP는 대용량의 데이터를 보내기 쉽게 작게 분해하여 상대방에게 보내고 정확하게 도착했는지 확인하는 역할.
  * 상대방에게 데이터를 확실하게 보내기 위해 3-way handshacking 방법 사용.
  * 연결해제시에는 4-way handshacking 사용.
  * point to point와 full-duplex 방식 사용. 
    - point to point : 각 연결이 정확히 2개의 양끝 점을 가지고 있는 것
    - full-duplex : 전송이 양방향 동시에 일어날 수 있는 것
  * 혼잡제어, 흐름제어, 에러감지 지원
    - 혼잡제어 : 데이터를 송신하는 곳과 수신하는 곳의 데이터 처리 속도를 조절하여 수신자의 버퍼오버플로우를 막는 것.
    - 흐름제어 : 네트워크 내의 패킷수가 오버플로우 나지 않게 방지하는 것.
    - 에러감지 : checksum 활용하여 에러 확인.
  * 일정 시간 ACK 값이 수신을 하지 못한 경우, 재전송 요청(Timeout-based Retransmission)
  
  * 참고
    - SYN : Synchronize Sequence Number
    - ACK : Acknowledgement
    - 3-way handshacking
      + 가장 처음, 송신측에서 'SYN' 플래그로 상대에게 접속하고 동시에 패킷을 보냄.
      + 그다음, 수신측에서 'SYN/ACK' 플래그로 송신측에게 접속하고 패킷받은 사실 보냄.
      + 마지막으로 송신측이 'ACK' 플래그 보내 패킷교환 완료 전함.
      + 이 과정에서 어디선가 통신이 도중 끊어지면 TCP는 같은 순서로 패킷 다시 전송함.
  
