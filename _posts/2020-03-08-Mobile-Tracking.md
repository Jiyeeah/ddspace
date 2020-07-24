---
layout: post
permalink: /Mobile-Tracking/
title: '모바일 사용자 트래킹 방식'
date: 2020-03-07 11:30:00 +09:00
feature: '/img/posts/4th/thumbnail.jpg'
background: '/img/posts/4th/header.jpg'
content_id:'/mobile/Mobile-Tracking/'
categories:
  - Mobile
tags:
  - 마테크
  - MarketingTechnology
  - 퍼포먼스마케팅
  - 그로스해킹
  - 모바일환경
  - MAT
description: 모바일 사용자 트래킹을 위한 대표적인 3가지 방식, 모바일 기기 광고ID(ADID/IDFA), Referral, Finger Print 활용 방식에 대해 자세히 알아보자.

---

가장 대표적인 모바일 사용자 트래킹 방식은 뭘까? 

지난 포스팅을 통해 (웹과 다른 모바일 환경 <https://ddspace.kr/before-MAT/>) 모바일은 고유 식별자로 ADID/IDFA를 사용한다고 간단히 언급한 바 있다. 이 밖에도 모바일 환경에서 사용자를 트래킹 하는 방식은 더 있다. 가장 대표적으로 세가지 방법이 있는데, 그 세가지가 **모바일 기기 광고ID, Install Referrer, Finger Print 활용 방식**이다. 그럼 각각의 방법에 대해서 구체적으로 살펴보자. 

---

### 1. 모바일 기기 광고ID 활용 방식

![애플로고 이미지](/img/posts/4th/apple.jpg) 

**모바일 기기 광고ID란 문자와 숫자 조합의 랜덤 값으로, 모든 기기(스마트폰/태블릿 등)에 부여된다.** 가장 대표적으로 아래 두가지가 많이 알려져 있다. 

- IDFA(Identifier for Advertisers)란, iOS 기기용 광고 식별자를 말한다.
- AAID(Android’s Advertising Identifier)란, Android 기기용 Google 광고 ID로 ADID라고도 불린다. 

대개 앱 설치 과정에서 모바일 기기 광고ID 값을 통해 서버와 통신하는 중요한 역할을 담당하며, 모바일 광고 환경에서도 모바일 기기 광고ID를 기준으로 사람을 식별한다. 정확히는 기기를 식별한다. 

예를들면 특정 기기가 내 광고를 봤는지, 특정 기기가 내 앱을 설치했는지, 앱 설치 이후에는 얼마나 상호작용을 하고 있는지 모바일 기기 광고ID를 활용해 알 수 있다. 하지만 디지털 환경 내 모든 트래킹이 그렇듯 100퍼센트의 정확도를 가질 수 없다. 유저가 원할 경우 ID변경이 가능하며, 모바일 기기 광고ID 정보 제공을 거부할 수 있기 때문이다. 

*참고링크*<br>
<https://support.google.com/authorizedbuyers/answer/3221407?hl=ko>
<https://www.adjust.com/glossary/device-id/>
<https://www.adjust.com/glossary/idfa/>

<br>

### 2. Install Referrer 활용 방식

![앱 이미지](/img/posts/4th/app.jpg) 

**Install Referrer란 Google Play 스토어의 Install Referrer를 말하며, 아래 정보를 얻을 수 있다. 당연히 안드로이드에서만 활용 가능하다.** 

- 설치된 패키지의 리퍼러 URL 
- 리퍼러 클릭이 발생한 시간(초)의 타임 스탬프
- 설치가 시작된 시간(초)의 타임스탬프

셋 다 중요하지만, 마케터에겐 설치된 패키지의 리퍼러 URL을 가져온다는 것이 가장 중요할 것이다. 채널 어트리뷰션을 측정하는 데 필요한 정보들이 담겨있기 때문이다.(해당 정보들은 Play Store developer 콘솔에서 설정 가능하다.) 

Google Play Store에 한정해서는 100퍼센트의 정확성을 가진다는 장점이 있지만, iOS 및 그밖의 앱스토어에서는 활용 불가하다는 치명적인 단점을 가지고 있다. 다이나믹 링크를 통해 동일한 정보를 넘기는 식으로 단점을 보완할 수 있다. (우리 회사 엔지니어분들께서는 다이나믹 링크를 활용하는 방법을 더욱 선호하는 편이시라고)

*참고링크*<br>
<https://developer.android.com/google/play/installreferrer>
<https://www.adjust.com/glossary/install-referrer/>

<br>

### 3. Finger Print 활용 방식

![핑거프린트 이미지](/img/posts/4th/fingerprint.jpg) 

**핑거프린트란 모바일 환경에서 사용자를 식별하는 방법 중 하나로, 디바이스에서 공식적으로 제공하는 정보들에 기반해 사용자를 식별한다.** 예를들면 디바이스 정보, 위치, OS 버전, 플랫폼, IP주소 등의 정보가 사용된다. 

해당 정보들을 조합해 동일 사용자의 가능성을 유추하는 방식으로, 당연히 정확성에서 문제가 될 수 있다. 그래서 대개 사용자 식별 방식에서 최하의 우선순위를 갖는다. 모바일 기기 광고ID, Install Referrer로 확인이 안되는 사용자에 한해 핑거프린트 방식을 적용해 사용자를 찾아내는 것이다. 실제로 대다수의 MAT에서는 우선순위와 적용하는 트래킹 방법의 차이만 있을 뿐, 이런 식으로 사용자를 유추한다. 

*참고링크*<br>
<https://www.appsflyer.com/resources/fingerprinting-for-mobile-attribution/>
<https://www.adjust.com/glossary/fingerprinting/>

---

지금까지 모바일 사용자 트래킹을 위한 대표적인 3가지 방식, 모바일 기기 광고ID(ADID/IDFA), Referral, Finger Print 활용 방식에 대해 알아보았다. MAT에서 사용자를 추적할 때 가장 많이 언급되는 세가지 방법이다. 이제 MAT 도입 혹은 MAT 공부할 때, 세가지 방법이 언급된다면 큼직한 개념적 이해는 갖고 접근할 수 있지 않을까.

<br>


개인적으로 공부한 내용을 담은 글입니다. 사실과 다른 내용/문의사항이 있다면 댓글을 남겨주시거나 jiyea0017@gmail.com으로 말씀해주세요. 읽어주셔서 감사합니다.