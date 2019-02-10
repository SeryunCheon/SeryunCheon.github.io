---
layout: post
title:  "🌿🗺️ Sprig MVC기반 게시판 With Naver, Daum, GoolgleMap APIs"
date:   2019-01-25
excerpt: "스프링MVC 게시판 w/ Google, Naver, Daum map APIs"
project: true
tag:
- Sprigframwork
- 스프링프레임워크
- NaverMap
- DaumMap
- GoogleMap
- mvc
feature: https://user-images.githubusercontent.com/30023840/51996132-8184d900-24f7-11e9-8142-6f38d3bccece.jpg
comments: false
---


## 🌿The Basic Board 회원관리 게시판
🌿🗺️ Sprigframwork기반 게시판 With Naver, Daum, GoolgleMap APIs
- 프로젝트설명: [https://seryuncheon.github.io//SprigframworkNDGBoard/](https://seryuncheon.github.io//SprigframworkNDGBoard/)
- Repository: [https://github.com/SeryunCheon/SprigframworkWithNaver_Daum_GoolgleMap_APIs](https://github.com/SeryunCheon/SprigframworkWithNaver_Daum_GoolgleMap_APIs)

![spring1](https://user-images.githubusercontent.com/30023840/52528869-03f96e00-2d2c-11e9-9af3-9fcf386de6cc.jpg)
-- 회원관리가 가능한 스프링mvc 기반의 게시판입니다. 기본적인 게시글의 CRUD가 가능하고, Member는 Student의 정보를 수정하거나 삭제 가능합니다.


![spring2](https://user-images.githubusercontent.com/30023840/52528868-0360d780-2d2c-11e9-9bac-94a04deb5325.jpg)
--MultipartResolver를 사용하여 이미지의 기본적인 업로드가 가능합니다.
--동영상 삽입 기능을 적용했습니다.

![12345678](https://user-images.githubusercontent.com/30023840/52528891-5b97d980-2d2c-11e9-8359-233bef568f7a.JPG)
-- MVC Interceptor를 적용하여 로그인하지 않은 회원은 접근이 불가하게 처리해두었습니다.

![11](https://user-images.githubusercontent.com/30023840/51996460-1f78a380-24f8-11e9-9228-f6928599b3bc.jpg)
-- 본격적인 메인 프로젝트를 하기전에 만들었던 작은 프로젝트였습니다. 수업시간에 배운 API쓰는법을 활용하여, 구글맵,다음맵,네이버맵으로 현위치를 나타낼수있게 만들어 보았습니다.

- Stack:
  - APIs: Naver Map, Daum Map, Google Map
  - backend: Spring,Eclipse,maven, Mysql, mybatis, apache Tomcat
  - frontend:jQuery,AJAX,JSon