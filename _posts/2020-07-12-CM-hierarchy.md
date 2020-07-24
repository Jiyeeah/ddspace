---
layout: post
permalink: /CMhierarchy/
title: 'Campaign Manager의 시작, Trafficking! 1. CM 하이어라키부터 알아볼까요?'
date: 2020-07-12 11:30:00 +09:00
feature: '/img/posts/11th/thumbnail.jpg'
background: '/img/posts/11th/header.jpg'
categories:
  - GMP
tags:
  - 마테크
  - MarketingTechnology
  - 퍼포먼스마케팅
  - 그로스해킹
  - AD-Tech
  - 애드테크
  - GMP
description: 구글 마케팅 플랫폼의 중심에 있는 Campaign Manager 첫걸음, Trafficking! Trafficking을 시작하며 반드시 알고 있어야할 CM 하이어라키 구조부터 알아보겠습니다.
content_id: "011"
---

![cm 로고 이미지](/img/posts/11th/thumbnail.jpg)

정말, 정말 오랜만에 다시 Campaign Manager로 돌아와 좀 더 깊숙이 들어가볼 계획이다.
잠깐 복습해보자면 Campaign Manager는 광고주 쪽에 위치한 Ad server이며, 웹 기반의 advertisers, agencies 관리 시스템이다. 웹/모바일 게재면에 상관 없이 온라인 광고 전반을 한 곳에서 관리하는데 좋은 플랫폼이다.

**아직 Campaign Manager에 대해 잘 모르신다면 이전 포스팅을 참고해주세요!*  <https://ddspace.kr/aboutCM/>

오늘은 **Campaign Manager의 시작, 캠페인 세팅이라 할 수 있는 Trafficking에 대해서 알아보겠다.** Trafficking을 하기 위해서는 CM의 하이어라키 구조를 먼저 이해해야만 세밀한 세팅이 가능하기 때문에, 이번 포스팅에서는 **CM의 하이어라키 구조와 각 구조별 세팅 가능한 값들에 대해 먼저 알아보고, 다음 포스팅에서 실제 Trafficking에 대해 더 알아보는 시간을 가질 예정**이다.

---

### Trafficking을 위한 CM 하이어라키

![cm 하이어라키 이미지](/img/posts/11th/hierarchy.jpg)

각 하이어라키 위치마다 적용할 수 있는 설정이 다르기 때문에, 실제 캠페인 세팅이라 할 수 있는 Trafficking을 하기 전에 CM 하이어라키에 대해 이해하는 것은 중요하다.

- **Advertiser**
CM에서 각각의 Advertiser는 각기 다른 캠페인 그룹과 그에 따르는 creative 자산 및 다른 세팅을 가진다. 대개 Creative 라이브러리 역할, 이벤트 태깅, floodlight 설정, 오디언스 세팅 등이 이루어진다.

- **Campaign**
CM에서 Campaign은 Advertiser 하위 그룹으로, 어떤 조건으로 그룹지을지는 전적으로 운영담당자의 결정에 달려있다. 대개 랜딩페이지, 이벤트 태깅, 오디언스 세그먼트 등을 세팅할 수 있으며 각 세팅에 따라 그룹을 달리 운영하거나, 리타게팅/신규/예측 등 캠페인 목표에 따라 그룹화되어 진행되기도 한다.

- **Site**
대개 실제 웹사이트, 모바일 앱 혹은 실제 구매되고 판매되는 광고 네트워크 자체를 의미한다. 광고 네트워크일 경우 대개 publisher 사이트로 구분되어 그룹지어진다. New York Times, The Economist 등 실제 사이트 명칭을 그대로 나타내는 경우가 대부분이다.

- **Placement(Package / Roadblock)**
  Placement란, 웹사이트 내에서 광고가 보여지는 곳, 즉 광고 구좌를 의미한다. 각 Plaecement는 저마다의 placement tag를 가지고 있고, placement 세팅 시 각 placement를 나타내는 tag 세팅을 반드시 해줘야 한다. Placement 마다 사용자 위치, 브라우저, 방문 시간대 등에 따라 광고 타게팅을 진행할 수 있다.

  Placement는 Package와 Roadblock 두 가지 형태로 그룹지을 수 있다. package는 하나의 placement 그룹이 모두 한 사이트 혹은 앱 내에 위치하고 있을 경우를 말한다.

  Roadblock은 하나의 placement 그룹이 모두 하나의 동일 페이지 내에 위치할 경우를 말한다.

- **Ad**
  Ad type 선택을 통해 display 광고, 클릭 유도 광고, 노출 광고를 세팅할 수 있다. 크게 Standard ads와 Tracking ads로 type을 선택할 수 있다.

  Standard Ads는 사이트 상의 display creative 광고를 말하며, display, in-stream, HTML 5 banners, rich media, in-stream video redirect, display redirect creatives가 있다.

  Tracking Ads와 click tracker 광고는 눈에 보여지는 형태의 광고가 아닌, CM 외 플랫폼을 통해 진행되는 광고의 클릭수와 노출을 트래킹하기 위해 활용되는 기술적인 광고 형태다.

- **Creative**
  Creative란 ad 콘텐츠 형태로 제공되기 위해 광고주가 업로드하는 파일 자산을 말한다. 대개 image file, Studio에 저장된 rich media assets, HTML 5 file 등이 있다.

  대부분의 일반적인 creative는 하나의 image file 형태로 업로드가 진행되지만 HTML 5 creative의 경우, 필요 이미지파일과 코드 등을 담은 zip 파일 형태로 업로드가 진행된다.

---

모든 광고 플랫폼이 그렇듯 CM도 CM만의 하이어라키를 갖고 있고, 광고 서버이자 GMP의 중심 역할을 하고 있어서 그런지 CM은 다른 광고 플랫폼보다도 더 복잡한 하이어라키 구조를 갖고 있는 것처럼 느껴졌다. 상대적으로 하이어라키가 복잡하지 않은 광고 매체들의 광고를 돌려와서 그럴 수 있지만 ㅎ_ㅎ. 각 하이어라키 내의 설정값은 겹치는 듯 하면서도 자세히 살펴보면 기능적인 제한/상속을 통해 충돌없이 진행할 수 있다. 이런 자세한 사항은 다음 포스팅에 실제 trafficking 세팅을 공부해보며 좀 더 살펴볼 예정이다.  <br>

개인적으로 공부한 내용을 담은 글입니다. 사실과 다른 내용/문의사항이 있다면 댓글을 남겨주시거나 jiyea0017@gmail.com으로 말씀해주세요. 읽어주셔서 감사합니다.

<br>

**참고링크**<br>

<https://support.google.com/dcm/answer/2829356?hl=en>

<https://support.google.com/dcm/answer/2829072?hl=en>

<https://support.google.com/dcm/answer/2829205?hl=en>

<https://support.google.com/dcm/answer/2837647?hl=en>

<https://support.google.com/dcm/answer/2826476?hl=en>
