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

```junos
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