---
layout: post
permalink: /aboutfloodlight/
title: 'Google Marketing Platform의 전환 트래킹 시스템, Floodlight'
date: 2020-05-02 11:30:00 +09:00
feature: '/img/posts/8th/thumbnail.jpg'
background: '/img/posts/8th/header.jpg'
content_id:'/gmp/aboutfloodlight/'
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
description: 구글 마케팅 플랫폼의 전환 트래킹 시스템이자 픽셀, Floodlight를 알아봅니다.
---
### Floodlight란? 

![doubleclick 로고 이미지](/img/posts/8th/thumbnail.jpg)

**Google Marketing Platform(GMP)의 전환 트래킹 시스템**이다. Google의 전환 트래킹 시스템에는 가장 크게 세 가지가 있다. Google analytics의 전환 트래킹 시스템, Google Ads의 전환 트래킹 시스템 그리고 GMP의 전환 트래킹 시스템인 Floodlight. 전환 시스템들은 각기 다른 룰을 가지고 있기 때문에, GMP의 모든 Products을 연결할 수 있지만 전환 데이터를 하나의 보고서 내에서 원하는 대로 이어 붙여보기에는 어려움이 많다. (이는 다른 포스팅에서 또 다뤄볼 계획입니다. 미래의 나가 어떻게든 해결하겠죠..)

![floodlight 이미지](/img/posts/8th/floodlight.jpg)

**Floodlight를 통해 GMP 내의 Campaign Manager, Display & Video 360, Search Ads 360의 전환을 기록할 수 있고 하나의 Floodlight 셋업을 세 개 플랫폼 모두에서 공유할 수 있다.** Floodlight의 셋업 자체는 세 개 플랫폼 모두에서 가능하나, 세부 조정은 Campaign Manager에서만 가능하다. 하나의 Floodlight 태그를 세 개 플랫폼에서 공유할 수 있다는 것은 퍼널 내 전환 중복 카운팅을 피할 수 있다는 의미이다. 마케팅 채널 기여 분석과 밀접하게 관련이 있는 부분인데, 쉽게 말해 디스플레이 클릭 1회, 검색광고 클릭 1회 후 전환이 일어났을 때 마지막 클릭 기여모델을 사용한다면 검색광고에만 기여를 부여하는 식으로 작동한다.  

어쨌든 Floodlight도 하나의 전환 시스템이기 때문에, 페이스북 픽셀/구글 애널리틱스 등을 사용하며 전환 시스템에 익숙한 분들이라면 어렵지 않게 받아들일 수 있다. **Floodlight 역시 여타 다른 픽셀과 마찬가지로, 내 광고 중 하나에 노출되거나 클릭한 뒤 내 사이트에 방문한 유저의 행동을 트래킹한다.** **기록된 유저들의 데이터를 바탕으로 오디언스(리타게팅 그룹)을 셋업할 수 있고, 다른 광고캠페인(예를들면 리타게팅 캠페인)에서 해당 그룹을 그대로 사용하거나 유사그룹으로 불려서 사용할 수 있다.**



### Floodlight 태그가 유저를 인식하고, 전환을 트래킹하는 방법

![identifications 이미지](/img/posts/8th/identifications.jpg)

**Floodlight는 userID로 cookieID와 mobileID를 활용**한다. 광고 노출, 클릭, 전환이 일어날 경우 cookieID나 mobileID같은 userID를 cookie에 기록한다. Floodlight는 쿠키 기록을 통해 유저를 인식하고 전환을 트래킹하기 때문에, 사람이 아닌 브라우저 혹은 디바이스에 기반해 데이터가 저장된다. 즉, **userID는 사람 한 명을 대표하는 것이 아니라 브라우저/디바이스를 대표**하는 것이다.

Floodlight는 전환을 카운트 시스템을 이해하기 위해서는 activity, tag, lookback window 개념을 알아둬야 한다.

1. **Activity**

   **Floodlight 전환 시스템에서 전환으로 정의되는 행동을 Activity라고 표현**한다. 예를들면 구매 완료, 특정 페이지 방문을 전환으로 본다면 각각 Activity라 말할 수 있다. 하나의 Activity별로 태그가 부여되며, 이 태그가 활용되어 전환을 기록한다.

   광고 클릭 이후 얼마나 많은 사람이 프로모션 페이지에 방문하는지 보기 위해서는 다음의 과정을 진행하면 된다. 원하는 전환에 부합하는 한 개의 Activity를 생성하고, 프로모션 페이지에 해당하는 Activity 태그를 설치한다. 유저가 내 광고를 클릭하고 해당 페이지에 방문하면(내가 정의한 전환 행동) 설치된 Activity 태그에 의해서 하나의 전환이 기록되는 것이다.  

   **Floodlight Activity에는 Action과 Transaction 두 가지 타입**이 있다. 아래 두 가지 타입을 모두 활용한다면 하나의 페이지/앱 내에서 방문과 구매 데이터 모두 한번에 트래킹할 수 있다.

   - **Action**

     광고를 보거나 클릭한 뒤 일어난 웹사이트 방문을 카운트한다. Campaign Manager에서의 Counter Activities가 Action Activity를 일컫는 말이다. CM의 Counter Activities 내에서는 세가지 전환 타입으로 나눠 카운팅할 수 있는데, Standard/Unique/Per session이 있다. Standard는 모든 전환, Unique는 24시간 마다 unique 유저의 첫번째 전환, Per session은 세션 당, 유저 당 하나의 전환을 카운트한다.

   - **Transaction**

     광고를 보거나 클릭한 뒤 일어난 구매된 상품 수 혹은 구매 횟수를 카운트한다. Campaign Manager에서의 Sales Activities가 Transaction Activity를 일컫는 말이다. CM의 Sales Activities 내에서는 Trasaction/Item sold 두가지 전환 타입으로 나눠 카운팅할 수 있다. Trasaction은 모든 전환, Item sold는 상품별 각각의 전환을 카운트하며, 판매된 상품의 전체 개수와 그에 상응하는 수입을 보여준다.

2. **Tag**

   **하나의 Activity를 트래킹하기 위해 활용되는 추적코드**를 말한다. 아래 태그(추적코드)는 Thank you 페이지에 세팅되는 Floodlight 태그이다. 페이지가 로드됐을 때, 아래 태그가 userID를 GMP Products(CM, DV360, SA360)에 보내 전환을 기록한다.

   ```
   <iframe height="0" width="0" src="//0.fls.doubleclick.net/activityi;src=0;type=fake_tag;cat=fake_tag;u=4771963;qty=1;cost=129.97;ord=4771963;~oref=http%3A//mysite.com/checkout?" style="display: none; visibility: hidden;"></iframe>
   ```

3. **Lookback Window**

   **Floodlight는 셋업 당시 내가 정한 기간 내에 광고를 클릭한 고객의 전환만을 기록하는데, 이를 룩백윈도우라 한다.** 예를들어 셋업 당시, 내가 룩백윈도우 기간을 10일로 설정해두면 한 유저가 내 광고를 클릭한 뒤 15일 이후 내 웹사이트에 방문해도 해당 방문은 전환으로 기록되지 않는다. 룩백윈도우 기간인 10일에 포함되지 않기 때문이다.

   Floodlight의 룩백윈도우는 '시간'이 아닌 '일' 단위 기간으로 적용된다. 이게 무슨 말이냐면 룩백윈도우 기간을 1day로 설정해두고 2일 자정이 넘어 전환이 발생했다고 가정했을 때, 내가 리포트를 오늘(3일) 오전 7시에 보면 내 전환 리포트에 해당 전환은 포함되지 않는다. 일 단위로 봤을 때 해당 전환은 3일자에 해당되는 전환에 포함되기 때문이다.

---

CM과 DV360을 공부하다, 급 Floodlight에 꽂혀 Floodlight에 대해 먼저 간단히 알아봤다. 다음 포스팅에서는 지난 포스팅에서 예정했던대로 CM의 하이어라키와 DV360의 하이어라키에 대해 알아보고, 차이점에 대해 좀 더 알아볼 예정이다. (혹은 Floodlight 태그 설치 방법에 대해 좀 더 알아볼 수도 있습니다 ? ㅎㅅㅎ)

<br>

개인적으로 공부한 내용을 담은 글입니다. 사실과 다른 내용/문의사항이 있다면 댓글을 남겨주시거나 jiyea0017@gmail.com으로 말씀해주세요. 읽어주셔서 감사합니다.

<br>

**참고링크**<br>

<https://support.google.com/dcm/answer/2823388?hl=en&ref_topic=6094292>

<https://support.google.com/dcm/answer/2903014?hl=en&ref_topic=6094292>

<https://support.google.com/dcm/answer/2823400?hl=en&ref_topic=6094292>

<https://support.google.com/dcm/answer/2823351?hl=en&ref_topic=6094292>

<https://support.google.com/searchads/answer/7298761?hl=en&ref_topic=6054260>

<https://support.google.com/searchads/answer/2903014?hl=en&ref_topic=6054260>

<https://support.google.com/searchads/answer/7305597?hl=en&ref_topic=6054260>

<https://support.google.com/searchads/answer/2478311?hl=en&ref_topic=6054260>
