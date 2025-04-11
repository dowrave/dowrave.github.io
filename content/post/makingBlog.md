+++
date = '2025-04-10T18:20:23+09:00'
draft = false
title = 'React + Django로 AWS에 웹 사이트 구축'
summary = "Project01"
+++

# React + Django로 AWS에 웹 사이트 구축
## 개요

- **구축** : 2024년 1월 ~ 5월 
- **서비스** : 2024년 5월~
- [사이트](https://www.htlee-blog.com/)

## 주요 구현 내용
- **상단 바의 카테고리 전환 버튼** : `Work`(파란색)와 `Hobby`(붉은색)을 전환
- **페이지 구현** : 메인메뉴, 게시판, 게시글, 아카이브, 회원
- **회원가입과 로그인** : 이메일 인증까지만 진행, 실제 가입은 X
- **글쓰기** : Quill / 동영상 첨부, 스포일러 표시 등 일부 기능 커스터마이징
- **로그인 유지** : JWT 토큰, Http Only 쿠키
- **오디오 파일 스트리밍(HLS) 플레이어**

## Skills / Used Resources
- 프론트엔드 : `React + Vite + TS`, `Redux`
- 백엔드 : `Django (REST Framework)`
- 스타일 : `Tailwind CSS`
- DBMS : `MySQL`
- Cloud : `AWS(S3, Cloudfront, EC2, RDS)`


## 세부 내용
- 대부분이 스크린샷입니다. 

## 메인 화면
- 최근 글 5개 표시 : 카테고리 전체, 각 게시판
- 현재 하고 있는 일 / 관심사 
- 깃허브의 잔디밭 : 글 게시 활동에 반응
- 카테고리가 2개이므로 실질적인 메인 페이지는 2개

### Work 메인화면
![메인페이지1](/images/MainSite1.PNG) 

![메인페이지2](/images/MainSite2.PNG)  
- 배경음악 구현
  - SUNO AI로 노래를 만든 다음, 사이트의 배경음으로 넣을 수 있게 구현했습니다.
  - **HLS 적용**
    - MP3 파일을 그대로 넣었을 때, 로딩이 완료되지 않은 상태에서 재생 시간 변경을 시도하면 슬라이더가 맨 처음으로 돌아가는 문제가 있었습니다.
    - 각 곡에 HLS을 적용하고 백엔드 서버에서 해당 데이터를 갖고 있게 하는 식으로 구현하여 위 문제를 해결했습니다.
    - HLS는 사이트의 어떤 페이지에서든 이용할 수 있습니다.

### Hobby 메인화면
![메인페이지3](/images/MainSite3.PNG) 

![메인페이지4](/images/MainSite4.PNG)  
- `현재 관심사`의 편집 버튼은 로그인 중일 때에만 나타납니다.

![메인페이지5](/images/MainSite5.PNG)

## 페이지
- 게시글은 [티스토리](https://waltwaez.tistory.com/)에 백업해뒀습니다.

### 게시판
![공부 게시판](/images/StudyPostList.PNG)

![애니메이션 감상문 게시판](/images/AnimePostList.PNG)

- 각 게시판, 게시글의 왼쪽에는 소분류를 따로 띄웠으며, 소분류 별로 게시글을 보는 것도 가능합니다.

### 게시글
![게시글](/images/postDetail.PNG)
- 화면 우측에는 **헤더의 위치를 스크롤 위치에 대응**하도록 시각화했습니다. 
- 클릭하면 스크롤은 해당 헤더의 위치로 이동합니다.

### 글쓰기
![글쓰기](/images/WritePost.PNG)
- 게시글 작성 기능은 Quill을 이용했습니다.
- **유튜브 링크, 스포일러 방지 문구** 등을 추가했습니다.
- **이미지 첨부** 기능은 AWS의 이미지 저장 버킷에 이미지를 저장하고, 그 주소를 가져와서 첨부하는 방식입니다.
  - Quill에서 제공하는 기본 기능은 글 자체에 이미지를 넣는 것인데, 이미지가 많아지면 화면이 끊기는 현상이 발생했습니다.

### 아카이브
- 전체 아카이브 페이지
![공부 전체 아카이브](/images/StudyEntireArchive.PNG)

- 취미 2024년 아카이브 페이지
![취미 2024년 아카이브](/images/HobbyAnnualArchive.PNG)

### 회원가입과 로그인
![회원가입, 로그인](/images/SignIn&SignUp.PNG)

![회원가입2](/images/SignUp2.PNG)

## 참고
### 블로그 시절 작성한 프로젝트 개요
![요약](/images/Project1Summary.PNG)

