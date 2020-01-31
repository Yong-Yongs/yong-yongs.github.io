---
title: "Juniper – vlan 설정"
categories:
  - Juniper
tags:
  - Juniper
  - vlan
---

## Intro

안녕하세요 오늘도 Juniper User가 한분이라도 늘길 바라는 마음으로 시작하겠습니다 ㅎ

오늘은 Juniper 장비로 VLAN 설정하는 방법을 알아보겠습니다.

명령어를 먼저 볼까요???

우선 형식은 다음과 같습니다
<br/><br/>

```
set vlans [vlan_name] vlan-id [vlan_ id]
```

<br/>

```[vlan_name]```는 설정하고자 하는 vlan
```[vlan_id]```는 설장하고자 하는 vlan-id  

<br/>

```
set vlans v100 vlan-id 100
set vlans v200 vlan-id 200
```
<br/>

간단하네요!!

그럼 장비에서 설정한 다음 Config를 확인해 보겠습니다.

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/1.png)

<br/>

보시는 것처럼 v100, v200이 설정 되었습니다.

그런데 vlan에 default vlan이 있네요???

Juniper 스위치의 경우  default vlan이 기본적으로 설정 되어 있습니다. ^^

이번에는 Vlan이 어찌 할당되어 있는지 확인해 보겠습니다.

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/2.png)

<br/>

설정한 vlan들이 보이네요

하지만 아직 Interface에 할당을 안해서 Interface 부분에는 공백으로 되어 있습니다.

그럼 Interface에 할당해 보겠습니다.

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/3.png)

<br/>


보시는것처럼 Interface 부분에 할당된 Interface가 보입니다.

여기서 *로 체크된 Interface는 현재 Up 상태를 뜻합니다.

*체크가 안된 xe-0/0/10는 현재 vlan이 할당은 되어 있지만 Down이라고 보시면 됩니다.

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/4.png)

<br/>

보이시죠??? ^^

가상머신이라 그런지 장비가 부팅되면 모든 Interface는 Up이라고 떠서

제가 일부러 xe-0/0/10은 disable 했습니다.

이해되셨지요?? ^^

그럼 이번에는 vlan을 할당하는 명령어를 해보겠습니다.

아시겠지만 vlan을 할당할때 Interface는 두가지 모드가 있습니다.

Untag 인 Access 모드

Tag 인 Trunk 모드

우선 Access 먼저!!

Access의 명령어는 다음과 같습니다.

<br/>

```
set inerfaces [Interface] unit 0 family ethernet-switching interface-mode [Interface mode]

set inerfaces [Interface] unit 0 family ethernet-switching vlan members [vlan-id]
```
<br/>

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/5.png)

<br/>


이번에는 Trunk 설정입니다.

<br/>

```
set inerfaces [Interface] unit 0 family ethernet-switching interface-mode [Interface mode]

set inerfaces [Interface] unit 0 family ethernet-switching vlan members [vlan-id]
```
<br/>

크게 어렵지 않으실거라 생각이 듭니다.

참고로 vlan을 할당할때 vlan-id는 vlan-id를 사용해도 되고 vlan_name을 사용해도 됩니다.

ㅇ_ㅇ??

무슨말이냐면 아래 설정처럼 두가지의 설정 모드 같은뜻을 의미합니다.

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/6.png)

<br/>

실제로 vlan-id만 사용하시는 분들도 있고 vlan_name만 사용하시는 분들도 있습니다.

이번에는 마지막으로  Routed VLAN Interface라 불리는 RVI에서 알아보겠습니다.

RVI 말 그대로 라우팅 된 인터페이스입니다.

Cisco에는 SVI라고 합니다.

설정 한번 볼까요???

<br/>

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/7.png)

<br/>

빨간색으로 표기한 부분이 추가되는 부분입니다.

나머지는 앞서 설명드린 vlan 할당에 대한 내용입니다.

간단히 설명하자면

<br/>

```
“나는 irb(vlan과 같음) 100(vlan_id)을 L3 인터페이스로 사용할꺼야~

irb unit(vlan_id) 100의 IP는 12.12.12.1/24 로 쓸꺼야~”
```

<br/>

대충 이런 뜻을 이해하시면 됩니다.

간단한 vlan에 대한 설명은 요기까지 하겠습니다.

열공하세요~^^