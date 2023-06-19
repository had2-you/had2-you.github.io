---
title: 'Summary'
layout: post
categories:
  - ComputerNetwork
tags:
  - cs
comments: true
---

e-mail, ftp(하나의 서버에 여러 파일을 올려놓은 후 사용자들이 원할 때 꺼내쓰는 형태)는 요즘은 Web안에 흡수되어 있음

remote login? 원격 → 잘 안씀

p2p file sharing ↔ prime server

OTT(over the top), Searching Engine : ex) google

**분산시스템**

- 어떤 일을 하나에서 전부 처리하지 않고 분산하여 처리

sysytem? 어떠한 동일한 목적을 이루기위해 여러 개의 구성요소들이 서로 협력하여 해당 일을 효율적으로 처리하는 것

s/w system?

![텍스트, 폰트, 스크린샷, 라인이(가) 표시된 사진

자동 생성된 설명](/assets/img/Aspose.Words.c8ae7185-f69b-46ba-9c22-6be8e7c8b98b.001.png)

![도표, 스케치, 화이트, 폰트이(가) 표시된 사진

자동 생성된 설명](/assets/img/Aspose.Words.c8ae7185-f69b-46ba-9c22-6be8e7c8b98b.002.png)

P 부분을 client, A와 D를 Server로 나누지만, A와 D를 한번 더 나눌 수도 있음

클라이언트 파트는 사용자에게 보여지는 것 뿐만 아니라 처리하는 부분으로 한 번 더 나눌 수 있음(서버의 부담을 줄여줌)

- 사용자 입장에서 컴퓨터 내부에서는 나누어져 있지만 사용자가 의식하면 안됨

DNS? 떨어져 있는 컴퓨터의 ip를 찾아가기 위해 도메인주소와 ip주소를 매칭시켜주는 역할 → www.google.com이라는 주소를 사용자는 검색했지만 컴퓨터 입장에서는 ip주소를 찾아가야하기 때문

찾아가기 위해서는 내 컴퓨터의 ip가 필요, 가정에서의 경우 하나의 고정된 ip를 사용하지만 학교와 같은 경우 필요할 때마다 할당을 해주어야함. → DHCP

어플리케이션 프로그램을 개발하는 입장에서는 라우터와 같은 네트워크 코어 디바이스를 신경쓸 필요가 없음 → 어플리케이션 부분은 운영체제가 담당

어떻게 어플리케이션 개발?

SGML? HTML 이전 언어

분산시스템을 구조화시키는 두가지

1. c/s(client & server) : 클라이언트는 요청, 서버는 응답, cs는 역할이 고정적 서버는 항상 대기를 하고 있어야 함(고정아이피를 가지고 있어야함) 데이터도 많고 집중되기 때문에 데이터 센터에서 운영(최근들어 데이터센터를 운영하는 것이 중요) → 운영비 등 비용 소요 → 각각의 회사가 데이터 센터를 운영하는 것 보다는 서버를 운영하고 도와주는 클라우드 컴퓨터를 이용 클라이언트는 요청만 하기 때문에 고정아이피를 사용할 필요가 없음(동적 아이피)
2. p2p : 좀 더 발달된 형태

⭐️ 클라우드 컴퓨팅 ? 많은 컴퓨터가 뭉쳐져 있는 형태 (크게 3가지 종류 나눔)

1. IaaS : 네이버나 구글과 같이 기본적인 메모리 할당해주는 것
2. PaaS : 내 컴퓨터에서 개발하기 위해 프로그램 설치 등 환경을 클라우드가 제공
3. SaaS : 만들어진 것을 이용만 하는 것

P2P architecture

만약 1만명이 이용할 수 있는 서버가 갑자기 10만명이 이용해야한다면 하드웨어 교체 등 비용이 들어가게 됨 → p2p는 확장성이 좋음(내가 클라이언트도 될 수 있고 서버가 될 수도 있기 때문)

프로세스? 하드에 있던 어떤 프로그램이 cpu에 올라가서 실행되어지는 상태

쓰레드? 프로세스와 같은 개념이지만 경량화 되어 있음

한 컴퓨터 안에도 클라이언트와 서버가 공존할 수 있음

ipc(inter process communication)? 프로세스가 한 컴퓨터 안에 있을 때 서로가 정보를 주고 받는 것, 기능은 운영체제에서 제공

반대로 떨어져 있다면 메세지를 통해서 전송

소켓 ? 만약 한 컴퓨터 안에 있는 서버와 클라이언트가 소통을 할 때 메세지의 부분까지 설계를 하려고 한다면 번거롭기 때문에 이를 돕는 역할, 운영체제가 제공

서버와 클라이언트에 따라 소켓의 함수차이, 구조가 다름

bind : 서버는 고정아이피를 가지기 때문에 바인딩하는 함수 사용

connect : 클라이언트가 서버에게 커넥트 요청을 보내는 것

accept : 수락할 때까지 반복문

send/recv : 데이터 주고받는 것

ip주소 : 32비트, 4자리수 숫자

한 컴퓨터(=주소가 동일하다는 의미) 안에 여러개의 프로세스가 돌아가면 어떻게 주소를 찾나? port number(=process number)를 통해 원하는 곳에 접근 가능

sequence number : 패킷을 하나만 보내는 것이 아니기때문에 패킷에 순서를 부여

Acknowledge number : 보낸 후 반대쪽에서 응답이 있은 후 다시 보낼 때 받았다는 메세지를 보내는 것

checksum : 에러 유무

요청을 받는 쪽인지 보내는 쪽인지가 맨 앞에 기재됨

신택스에는 정보가 어느 자리에 들어가야 하는지 자리까지 정해져 있음

syntax vs semantics

프로토콜 안에는 메세지에 syntax, semantics 가 있음

전자 규칙, 문법 후자는 의미

ex ) a=b → 자체는 규칙(syntax)이 됨

cs 적 관점 : b를 a에 대입

수학적 관점 : a와 b는 같다

→ 두가지의 의미(semantics)를 가짐

SMTP = 이메일 프로토콜

proprietary protocols = 비공개 프로토콜

data integrity : 파일의 경우 신뢰성이 중요 (no loss)/ 오디오, 비디오와 같은 것들은 손실을 어느정도 반영할 수 있음

timing : 음성의 경우 시간이 중요

throughput : 링크가 가진 대역폭 = R , 패킷의 길이 = L 일 때, L/R = 전송률, 고정적이지 않음, 어느정도의 전송률이 보장되어야 하는가 아닌가? 데이터는 괜찮지만 동영상의 경우 중요함

security : 보안성

TCP 특징

1. 신뢰성있는 전송을 보장, 따라서 보내는 쪽이 안심하고 보내고 받을 수 있음
1. flow control vs congestion control : A를 클라이언트, B를 서버라고 할 때 B가 데이터를 받은 후 큐(자신의상태)의 상태를 A쪽으로 보낸다.(A가 많은 양의 정보를 보내려고 할 때 라던지..) → 이렇게 하면 A는 속도를 조절하여 보낸다. → 서버의 문제 congestion 은 통신망 문제
1. 시간, 전송률과 같은 것을 보장하지 못함 (위와 같은 문제에 시간이 들기 때문)
1. 보내기 전에 연결이 확실하게 되었는지 확인(hand-shake)

↔ 반대되는 것이 UDP 특징

기본적으로 인터넷은 보안에 취약하기 때문에 다른 프로토콜(SSL)의 도움을 받아야함

**3장**

Web? 거미줄.. 인터넷과 다른 의미, 문서가 연결된 것 hypertext(link) 링크를 타고타고 연결되어 얽히고 웹문서들. 웹페이지는 여러 개의 문서로 연결되어 있다.

웹페이지는 오브젝트(html file, 사진, 오디오 파일 등을 일컫는다)

각각의 위치를 나타낸 것을 URL(오브젝트 들의 주소)이라고 함

url, urn 차이

url은 프로토콜(http://) 포함 urn은 프로토콜 제외, 페이지, 확장자 등을 포함

url + urn = uri

sgml → html → xml

xml? 태그<>를 통해 글자의 의미를 부여하고자 함

http를 통해 웹이 어떻게 주고 받는가?

브라우저라는 것을 통해 접근하고 주고받을 때에는 http 전부 프로토콜을 사용

http 하단에는 tcp 프로토콜의 도움을 받음

클라이언트와 서버가 3-way handshake를 함

비상태연결(Stateless)? 클라이언트가 서버에게 한 요청(상태)를 서버가 저장하지 않는 것을 의미

포트번호 = 프로세스번호 한 포트번호에 여러 개의 프로세스가 돌아감

포트번호 배정 누가? 프로세스 누가 관리? → OS

비상태연결 : 기본적으로 상태를 저장하지 않지만 저장하는 방법이 있음 → cookie(쿠키)

서버에 들어온 어떤 사람에게 번호를 부여 → 쿠키가 됨

해당 쿠키를 데이터베이스에 저장하고 어떤 아이피를 통해 들어왔는지, 어떤 물건을 구매했는지 등을 저장

서버에서 응답 시 응답메세지에 쿠키번호를 숨겨서 같이 보내줌 하지만 클라이언트는 모름

이후 클라이언트가 페이지를 옮겨 다른 페이지를 볼 때마다 서버에 저장

일주일 후에 들어가도 쿠키가 남아있음

→ CRM 으로 이용..

왜 쿠키 사용? 기본적으로 웹이 비상태이기 때문에 단점을 보완하기 위해

**비지속성(non-persistent)?**

웹페이지의 오브젝트(자원)들이 하나하나 연결과 종료를 반복하며 요청에 대한 응답을 반복 → 시간과 서버자원 낭비

http 1.0 에서 사용

소켓 하나당 오브젝트 한 개 but, 소켓 여러개가 동시에 열릴 수 는 있음

**지속성(persistent)?**

여러 개의 요청, 응답을 서버, 클라이언트간 연결을 유지하면서 처리하는 방식

하나의 소켓으로 전부 연결하며 보내는 것

첫 RTT는 어떠한 동작이 아닌 핸드쉐이크 과정(there’s no receive and send)

다음 RTT에서 동작이 이루어짐 + 막대기가 넓을수록 파일 전송 시간이 더 걸림

∴ 2RTT + 파일 전송 시간 = 응답시간 → 따라서 지속성에서 더 빨리 걸리는 이유는 RTT를 반복하는 시간이 줄어들기 때문

데이터는 있을 수도 없을 수도 상황에 따라 다름

1번째 라인 : GET / POST / HEAD(커맨드) : 메시지의 전체적인 의미 // URL // HTTP 버전

2번째 라인 : 도메인 이름

3 : 브라우저 이름

…

클라이언트 부분에는 보통 바디가 없음

GET : 웹페이지 URL 요청

HEAD : 문서의 내용 없이 타이틀만

POST : 서버에 요청하는 것(예: 네이버 검색시 텍스트 본문을 서버에 요청)

PUT : 파일 단위나 동영상 같은 용량 큰 것을 업로드하기 위한 요청 → 위키피디아, 이러닝 업로드 등

DELETE : 삭제 요청

put / delete 는 위험

301 : 찾고자 하는 주소를 다른 곳에서 보내줌

400 : 이해를 못했을 때(예: 1.0버전만 이해하는 데 1.1로 보냈다던지..)

404 : 서버 주소를 못 찾는 경우

505 : 버전이 안맞는 것

웹캐시와 프록시 서버는 다름

웹캐시? 서버쪽에서 쿠키를 관리하는 것이 아닌 클라이언트에서 검색했던 기록을 저장하는 것

프록시 서버? 캐시메모리와 개념이 비슷 → 메모리와 cpu 사이 왔다갔다 하는 시간이 오래걸려서 자주 사용하는 시스템을 캐시에 저장한 후 캐시에서 꺼내서 쓰게 되면서 전체적인 속도를 향상시키기 위한 장치

오리지널 서버는 외부, 프록시 서버는 내부에 존재 → 프록시 서버에서 먼저 검색함 → 속도향상

Conditional GET : 프록시 서버와 오리지널 서버 사이에서 문서가 변형 되었는지, 해당 문서가 맞는지 알 수 없기 때문에 서로 교류하여 문서를 작성한 날자를 대조한 후, 문제가 없다면 문제가 없다는 메시지를 전송

만약 날짜가 다르면 오리지널 문서를 다시 보내줌