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