# 소켓의 본질
- 소켓은 OS 커널에 구현되어 있는 프로토콜 요소에 대한 추상화된 인터페이스
    - 프로토콜에 따라 해당 소켓이라 부름
        - 블루투스 장치일 경우 : 블루투스 소켓
        - IRDA일 경우 : IRDA 소켓
- 장치 File의 일종
- 일반 파일에 대한 개념이 대부분 적용됨

Stream - 직소퍼즐이 연속으로 조립된 형태
Segmentation - Stream을 Segment조각으로 자라는 행위
TCP - L4 - Segment - 직소퍼즐 조각
IP - L3 - Packet - 직소퍼즐 조각의 택배화