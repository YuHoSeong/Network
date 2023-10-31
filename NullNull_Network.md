# 네트워크 기초 이론

## 01 네트워크를 배우려는 사람들을 위해
이상의 실체!
우선 실체에 대한 학습을 하자!
- OSI 7Layer : 이상
- TCP(4Layer)/IP(3Layer) + HTTP(7Layer) 구현 : 실체

## 02 Mac주소, IP주소, Port번호 식별자
MAC : NIC에 대한 식별자. H/W 주소지만 변경이 가능하다 NIC 당 1개 (만약 유선 NIC과 무선 NIC이 있을경우 2개가 된다는 말)
IP : Host에 대한 식별자. NIC 당 N개 바인딩 가능하다
Port번호 : Process 식별자

Host : 인터넷이 연결된 컴퓨터
Network : 자원을 공유하기 위해 단말들이 서로 통신이 가능하도록 연결(LAN)
Internet: 여러 네트워크의 연결

## 03 Host, Switch, Network 이들의 관계
- Host : 네트워크에 연결된 컴퓨터 Network + Computer
    - Network 자체 : Switch
        - Router : 경로 선정
        - F/W (방화벽) : 보안 스위치
        - IPS : 보안 스위치
        - Network 이용주체 : End-point
            - Peer
            - Server
            - Client
- Network
    - Internet = Router와 DNS의 집합체
        
## 04 IPv4 주소 체계
- IPv4 : 32bit
- IPv6 : 128bit
- IPv4기반 IP주소 : 예시 - 192.168.60.14
    - IP주소 = NetworkID + HostID
    - 192.168.60 : NetworkID
    - 14 : HostID
- 서브넷 마스크 : 예시 - 255.255.255.0
    - 네트워크ID의 길이를 나타냄.
- CIDR 표기법 : 192.168.60.14/24
    - /24 : 네트워크ID의 길이

## 05 Port 번호 : Process 식별자!
- Port번호는 16bit 정보
- Process - 소켓 - TCP - IP - Driver - NIC
    - TCP 4Layer에서 어떤 Process로 정보를 보내야하는지 port번호로 식별함

## 06 Switch가 하는 일은 Switching
- Network(고속도로)
- 패킷 단위 데이터가 라우터에 도착하면 스위칭(경로/인터페이스 선택)을 한다.
- **라우팅 테이블**을 기준으로 목적지에 도착

## 07 네트워크 데이터 단위 정리(매우 중요!)
- File Socket - Stream (크기를 알수 없는 데이터)
- TCP - Segment (Stream의 Segmentation - Stream을 일정 길이(MSS: Maximum Segment Size)로 분해)
- IP - Packet (최대 크기(MTU) : 1500 bytes)
- NIC - Frame

## 08 네트워크 인터페이스 선택 원리와 기준
- cmd `route print` : 라우터 정보를 볼 수 있다.
- 어떤 IP 주소는 어떤 네트워크 인터페이스랑 연결되기 마련

## 09 웹 서비스를 만드신 분에 대하여...
1. 문서(TEXT)
2. 문서 + Link : HTML 형식
3. HTML 전달 하기 위한 HTTP 프로토콜
- HTML + HTTP = **Web**
- 모든 문서 S/W 구조
    1. 인터페이스(GUI)
    2. 제어체계(S/W)
    3. Data형식 = 자료구조

## 10 초창기 웹 서비스 구조 (단방향 구조)
- Web 티모시 버너스리
- Web Client(Browser) - Internet - Web Server
    - TCP/IP 연결(상태) + HTTP(Stateless)
    - 연결되었다면 http.request
    - http.response
    - 브라우저를 이루는 핵심 요소
        1. 구문분석기 : HTML을 파싱해 비선형 자료구조인 DOM형태로 만든다.
        2. 렌더링 엔진 : DOM형태의 정보를 활용해 렌더링 한다.

## 11 웹 서비스 3대 요소 (양방향 상호 작용) 
**-> 문맥(상태 -> 전이) -> 기억(기록) Database의 등장**
- 브라우저
    1. 구문 분석기
    2. 렌더링 엔진
    3. 연산(처리) 엔진 : Mocha -> Live -> JavaScript
- 쿠키(**기억(기록)**)
    - key+value
    - 속성
        - 범위
        - 기간
- Web Server(송/수신)
    - HDD 정적 리소스 : HTML + 사진 + CSS + JavaScript
- Web Application Server(처리, 연산)
    - http.request.method == POST
    - Web Server
    - Web Application Server
    - HTML 동적으로 생성(id = tester)
- Database(자료) **기억(기록)**
    - SQL
