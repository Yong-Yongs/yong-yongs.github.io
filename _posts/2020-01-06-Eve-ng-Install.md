---
title: "LAB with Eve-ng - Install"
categories:
  - Eve-ng
tags:
  - Eve-ng
  - Lab
---

# Intro

개인적으로 공부한 내용을 정리하고자 시작하게 되었고 제가 Juniper 라는 Vendor 제품을 만지는데

Juniper User가 한분이라도 늘길 바라는 마음으로 블로깅을 시작하려고 합니다.^^

혹시나 찾아주셨는데 제가 작성한 내용이 이상하다??? 라고 생각하시면 가르침 부탁드립니다.

우선 Network Emulator인 Eve-NG설치 방법을 소개 하려고 합니다.

제가 Eve를 사용하는 이유는 아래와 같습니다.

> * Web UI 방식의 Lab 환경 제공
> * Major Vendor의 NFV 지원
> * GNS3와 마찬가지로 실시간 Packet Capture 지원 등

개인적으로는 공부하기에 정말 좋은 녀석인거 같습니다.

 
이제 설치 해볼까요???

Eve 홈페이지에 설치 동영상이 있지만 참고 하실분들은 참고 하시면 됩니다.

(제가 처음에 설치할땐 이런것도 없었는데 ㅠ_ㅠ)


[![Eve-ng](http://img.youtube.com/vi/nia7BEQEOHk/0.jpg)](https://youtu.be/nia7BEQEOHk?t=0s) 

우선 www.eve-ng.com 으로 접속하여 Community version을 Download를 하시면 됩니다.

예전에는 version 구분이 없었는데 얼마전에 Professional version이 생겼습니다.

느끼셨겠지만 Community version은 무료 Pro version은 유료입니다!!

Community  버전으로도 충분히 공부할수 있으니 걱정 안하셔도 됩니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/1.png)

x86서버에 바로 설치도 가능하지만 OVA로 설치하는것이 편하기때문에 OVA로 다운 받습니다.

다운로드가 완료되면 VMware Workstation으로 ova를 설치합니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/2.png)

다운 받은 OVA file을 실행하시면 아래와 같이 import화면이 나옵니다.

Import 후 가디리시고 VM 전원을 켜시면 됩니다.

켜시기전에 VT-X부분에 체크가 되었는지 확인을 해야합니다.

혹시 체크가 안되어 있으면 가상머신이 동작을 안합니다.

Network 부분도 NAT로 변경하고 VM을 켜겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/3.png)

Root password 입력 하는 부분입니다.

나중에 window client package 설치 후 구동을 편하게 하시려면 그냥 넘어가시면 됩니다

(Default password : eve)

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/4.png)

호스트 네임도 그대로 하겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/5.png)

DNS도 넘어 가겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/6.png)

고정 IP를 사용하셔도 되지만 저는 DHCP로 설정하겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/7.png)

NTP도 그냥 넘어 가겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/8.png)

Proxy 또한 그냥 넘어가겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/9.png)

여기까지 다 완료가 되었으면 이제 설치가 완료 된겁니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/10.png)

이쁘네요 🙂

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/11.png)

설치가 완료되면 위에 보이는 IP로 접속하시면 해볼까요???

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/12.png)

접속하면 화면처럼 로그인 창이 나옵니다.

기본 계정과 비번은 admin // eve입니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/13.png)

실행은 했는데 아무것도 없네요???

우선 Lab을 만들어 보겠습니다.


![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/14.png)

폴더 이름을 정하고 Add folder를 클릭하시면 폴더가 생성이 됩니다.

여러명이 Eve를 공유하면서 사용한다고 했을때 폴더를 사용자명으로 구분하셔도 됩니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/15.png)

폴더에 들어온다음 Lab을 만들어 보겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/16.png)

Lab 명을 정해주시고 Save 클릭

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/17.png)

Lab이 만들어 지면 위 화면과 같이 화면이 나옵니다.

저희는 저기서 Add an object를 선택하겠습니다.

좌측 메뉴에서 선택을 해도 되고 아래 화면 같이 마우스 우클릭 후 Node를  선택 하겠습니다.

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/18.png)

![Eve-ng Community](/files/2020-01-06-Eve-ng-Install/19.png)

오~ 먼가 많은 Vendor의 NFV가 있네요

아쉽지만 실행 할 Image가 등록이 되어있지 않아서 모든 Image가 비 활성화 상태입니다.

활성화가 되면 파란색으로 표시가 됩니다.

여기까지가 기본적인 Eve 설치 과정입니다. ^^