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

우선 형식은 다음과 같습니다.

```
set vlans [vlan_name] vlan-id [vlan_ id]
```

```[vlan_name]```는 설정하고자 하는 vlan
```[vlan_id]```는 설장하고자 하는 vlan-id  


```
set vlans v100 vlan-id 100
set vlans v200 vlan-id 200
```
간단하네요!!

그럼 장비에서 설정한 다음 Config를 확인해 보겠습니다.

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/1.png)


보시는 것처럼 v100, v200이 설정 되었습니다.

그런데 vlan에 default vlan이 있네요???

Juniper 스위치의 경우  default vlan이 기본적으로 설정 되어 있습니다. ^^

이번에는 Vlan이 어찌 할당되어 있는지 확인해 보겠습니다.

![Juniper – vlan 설정](/files/2018-08-17-vlan-설정/2.png)
