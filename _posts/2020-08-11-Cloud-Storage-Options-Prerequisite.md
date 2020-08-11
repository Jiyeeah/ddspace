---
layout: post
permalink: /CloudStorageOptionsPrerequisite/
title: 'structured data, unstructured data, data transaction, transactional data'
date: 2020-08-11 11:30:00 +09:00
feature: '/img/posts/12th/thumbnail.jpg'
background: '/img/posts/12th/header.jpg'
categories:
  - Cloud
tags:
  - 구글클라우드플랫폼
  - GCP
  - 마케팅데이터
  - AD-Tech
  - Data
  - Cloud
description: Cloud Storage 옵션을 들어가기 전, 선수과목 structured/unstructured data, data transaction과 transactional data
content_id: "012"

---

두서 없이 Google Cloud Platform 공부를 시작한 탓에, 두서 없이 Google Cloud Storage 옵션들에 대해 알아보려고 한다.  **GCP Cloud Storage는 옵션에 따라 structured/unstructed data를 지원하고, transactional database 환경 형태인지 여부가 다르다**. 

GCP Cloud Storage는 옵션이 어떤 데이터 형태를 지원하는지 세부 설명을 하기 전, 일종의 선수과목처럼 데이터 구조 관련 4가지 정의부터 먼저 알아보겠다.

---

### Prerequisite 1. structured data vs unstructed data

**Structrued data**

Structured data는 우리가 일하면서 가장 많이 만나볼 수 있는 종류의 데이터로, relational database나 스프레드시트에서 만나게 되는 데이터들을 말한다. 이렇게 말로만 표현하면 당연히 이해가 안될테니.. 예시 이미지를 넣는다. 

![Structured data 이미지](/img/posts/12th/SampleACSdatatable.jpg)

*이미지 출처: https://commons.wikimedia.org/wiki/File:Sample_ACS_data_table.png*



열마다 데이터 속성이 정해지고, 하나의 행마다 각 데이터 속성 값에 맞는 실제 데이터가 차곡차곡 채워진다. 흔히 SQL을 사용할 때, 이런 structured data를 활용한다. 



**Unstructrued data**

Unstructed data는 structured data를 제외한 모든 데이터를 말한다. structured data는 사전에 정의된 내부 데이터 구조와 데이터 모델/스키마를 가지고 있지만, Unstructed data는 그렇지 않다. 이러한 특성 탓에 세상에는 structured data보다 Unstructed data가 더 많고, 앞으로 더 많아질 것이다. 

Structured data보다 사용에 불편함이 많고, 정리되지 않은 data인 Unstructured data를 굳이 알아야하는 이유가 뭘까? 위에도 말했듯 Unstructed data는 앞으로 더 많아질 것이다. 그리고 많은 Unstructed data를 이용해서 사람들은 머신러닝, 고도화된 분석을 진행하고, 인사이트를 찾아낸다. 그래서 이 데이터들이 중요하다. (GCP에서 NoSQL로 표현되는 데이터들이 이런 데이터를 말한다고 보면 된다.)

대개 사람이 만들어내는 종류의 Unstructed data로는 아래의 것들이 있다.
- 텍스트 파일
- 이메일 데이터
- SNS 데이터
- 웹사이트 데이터
- 모바일 데이터
- 커뮤니케이션 데이터 (각종 챗앱, 통화기록, 협업툴 등)
- 미디어 파일 (이미지, 오디오, 비디오 파일 등)
- 비즈니스 어플리케이션 데이터

사람뿐만 아니라 기계들도 Unstructed data를 만들어낸다.
- 위성 데이터(날씨 데이터, 지형, 군사 움직임 등)
- 과학 데이터(석유/가스/공간 탐사, 지진 이미지, 대기 데이터 등)
- 디지털 보안용 데이터(보안 감시 사진, 비디오 등)
- 센서 데이터(트래픽, 날씨, 해양학 센서 등)



### Prerequisite 2. data transaction and transactional database

**Data transaction**

Data transaction은 데이터베이스 내에서 일관된 형태로 수행되는 모든 논리적 계산을 말하는데, 가장 흔한 예로 은행 업무가 이야기되곤 한다. 하나의 은행 계좌에서 다른 하나로 돈을 보낸다고 가정해 봤을 때, 완벽하게 수행된 거래는 다음과 같다. 한 계좌에서 송금 신청된 금액이 해당 계좌에서 추출되고, 다른 계좌에 동일한 금액으로 입금되어야 완벽하게 수행된 거래라 할 수 있다. Data transaction 역시, 데이터베이스 내에서 이런 식의 일관된 형태로 수행되는 모든 논리적 계산을 말한다. 

대개 데이터베이스 환경 내에서의 data transaction은 두 개의 목표를 갖고 있다. 
1. 어떤 환경에서든 일관된 데이터를 유지하기 위함이다. 예기치 못하게 시스템 상의 문제로 데이터에 영향이 생기거나, 운영 상의 이유로 데이터베이스의 데이터 상태가 좋지 못할 때를 고려해 본다면 이유를 납득할 수 있다.

2. 데이터베이스와 통신하는 프로그램들 간에 격리된 환경을 만들기 위함이다. 통신이 뒤엉켜 데이터 정보에 에러가 생기는 것을 방지하기 위함이라 생각해 본다면 이 역시 이해되는 부분이다.

   

**Transactional database**
Transactional database란 data transaction을 지원하는 DBMS(Database Management System)을 말하는데, 여기서의 DBMS는 ACID propertie 역시 함께 제공한다. 

다시, ACID properties란 무엇이냐하면 data transaction의 속성 묶음을 말하는데, 여기서의 속성은 에러/시스템 고장 등의 문제 발생에도 데이터 유효성을 보장하는 녀석들이다. 이러한 속성 덕분에, transaction에서 발생한 모든 쓰기 작업(데이터를 새로 쓰는 작업 등)은 데이터에 영향을 아예 미치지 않는다. (거래 성공 후, 해당 쓰기 작업이 데이터에 영향을 미치게 하거나 transaction에 포함된 쓰기는 아예 지워지거나) 뿐만 아니라 transaction 자체도 특정 isolation level을 만족시켜야만 transaction이 가능하다. 

data transaction이 database에 영향을 미칠 수 있으니, ACID propertie를 함께 제공하는 것이다. 

---

당연하지만 클라우드를 이용해 만들어지는 모든 어플리케이션은 그 목적이 다르고, 목적에 따라 각기 다른 Google Cloud Storage 옵션을 선택해 사용한다. 어플리케이션에 따라 콘텐츠 스트리밍, 동영상 스트리밍, 혹은 광고 데이터 저장 등 GCP를 활용해 만들 수 있는 어플리케이션 종류 만큼이나 데이터 저장 목적이 다양하게 나타난다. 

오늘 공부한 선수과목 내용을 바탕으로, GCP에서 지원하는 Cloud Storage 옵션에 따른 다양한 지원 방식을 다음포스팅에서 비교해볼 계획이다!  <br>

개인적으로 공부한 내용을 담은 글입니다. 사실과 다른 내용/문의사항이 있다면 댓글을 남겨주시거나 jiyea0017@gmail.com으로 말씀해주세요. 읽어주셔서 감사합니다.

<br>

**참고링크**<br>

<https://learn.g2.com/structured-vs-unstructured-data#:~:text=Structured%20data%20is%20highly%2Dorganized,collect%2C%20process%2C%20and%20analyze.>

<https://www.datamation.com/big-data/structured-vs-unstructured-data.html#:~:text=Structured%20data%20vs.,video%2C%20and%20social%20media%20postings.>

<https://en.wikipedia.org/wiki/Database_transaction>