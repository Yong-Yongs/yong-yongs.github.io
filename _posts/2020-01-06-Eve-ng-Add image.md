---
title: "LAB with Eve-ng - Add image"
categories:
  - Eve-ng
tags:
  - Eve-ng
  - Lab
---

# Intro

이번에는 Eve에 Image 등록 후 구동까지 해볼까요??

우선 Eve에서 지원하는 Image는 아래와 같습니다.

생각보다 많네요 ^^

또한 Image를 어찌 추가하는지도 친절하게 나와있습니다.

http://www.eve-ng.net/documentation/howto-s

Cisco를 공부하시는 분들은 Dynamips Image를 그대로 사용할수 있을것 같네요.

다른 Vendor Image는 해당 Vendor 홈피에서 가입하고 Trial Version을 구하셔도 되고

아니면 조금만 검색하시면 구하실 수 있으니까 걱정 마세요 ^^

저는 Juniper의 NFV Image로 진행을 하려고 합니다

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/1.png)

와~ 많다~

제가 아는 버전으로 간단히 몇가지 Image만 소개해 보겠습니다.

> * Olive – M Router의 가상화 장비
> * vMX – MX Router의 가상화 장비
> * vQFX – Data Center 스위치인 QFX의 가상화 장비
> * vSRX – 방화벽 장비인 SRX의 가상화 장비
> * Junos Space – 네트워크 관리 플랫폼

이렇게 제품군 마다 NFV가 있네요???

이제 등록해 볼까요?

여기서 중요한게 복사하는 폴더의 이름도 맞춰서 해주셔야 합니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/2.png)

http://www.eve-ng.net/documentation/images-table

이런식으로 해당 폴더명을 지정해줘야 Eve에서 인식을 합니다.

폴더명까지 완료 하셨으면 Image를 넣어 보겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/3.png)

자세한 방법은 아래 링크를 보시면 됩니다.

http://www.eve-ng.net/documentation/howto-s/146-howto-add-juniper-vqfx
 

Juniper vQFX의 경우 RE, PFE라는 두개의 NFV가 한 세트입니다.

> * RE – Routing Engine
> * PFE – Packet Forwarding Engine

VM에 접속해서 봐볼까요???

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/4.png)

보시는것처럼 두개의 폴더 안에 각각 hda.qcow2 라는 파일이 있습니다.

Eve가 Qemu를 지원하니 qcow2 파일명으로 변경해서 사용하면 됩니다.

다시 Web UI로 가볼까요??

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/5.png)

보시는것처럼 vQFX 부분이 파란색으로 활성화 되었습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/6.png)

원하는 장비를 선택 후 생성하는 내용입니다.

기본적으로 설정이 되어 있으니 그냥 진행해도 될것 같네요

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/7.png)

vQFX 2세트를 만들어서 서로 연결하였습니다.

Interface를 모두 연결 했으면 왼쪽에 Start all nodes 를 선택하면

Eve에서 생성한 모든 VM 장비들이 부팅이 됩니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/8.png)

짠~!! 장비도 회색에서 파란색으로 변했네요

이제 장비에 접속해 볼까요???

우선 장비에 접속하기전에 선작업이 필요합니다.

http://www.eve-ng.net/downloads/windows-client-side-pack

해당 링크를 통해 “Windows client side pack” 설치하시면 됩니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/9.png)

설치가 완료 되었네요

설치한 폴더로 이동해서 해당 레지를 등록합니다.

SecureCRT 레지를 등록한 다음 Web에서 장비 클릭시 아래와 같이 콘솔 선택이 가능해 집니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/10.png)

전 SecureCRT 선택

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/11.png)

CRT를 선택하면 CRT로 실습이 가능해집니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/12.png)

간단하게 Interface에 IP 설정해서 Ping를 체크 해보겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/13.png)

잘 되네요 ^^

다른 기능도 알아 볼까요???

Eve에서 Packet Capture의 기능도 있다고 전에 말씀드린적이 있습니다.

우리는 지금 Ping을 하고 있으니 Packet을 한번 살펴보겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/14.png)

위와 같이 interface capture하면 아래와 같이 실시간 캡쳐가 가능합니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/15.png)

Wireshark 레지를 등록하면 위와 같이 Wireshark가 실행이 됩니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Add_Images/16.png)

오늘 Posting은 요기까지 하겠습니다.

공부 열심히 하세요~ ^^

 