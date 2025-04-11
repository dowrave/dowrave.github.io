+++
date = '2025-04-10T18:20:23+09:00'
draft = false
title = 'React + Django로 AWS에 웹 사이트 구축'
summary = "Project01"
+++

# React + Django로 AWS에 웹 사이트 구축
## 개요
**2024년 1월부터 5월까지 진행한 프로젝트**이며, **AWS 프리 티어를 이용해 2024년 5월부터 2025년 4월까지 유지된 사이트**입니다.  
~~현재는 유지보수가 어려울 것 같아 사이트를 내린 상태입니다.~~  
도메인은 `htlee-blog.com`을 사용했습니다.

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

### 메인 화면
- 최근 글 5개 표시 : 카테고리 전체, 각 게시판
- 현재 하고 있는 일 / 관심사 
- 깃허브의 잔디밭 : 글 게시 활동에 반응
- 카테고리가 2개이므로 실질적인 메인 페이지는 2개

#### Work 메인화면
![메인페이지1](/images/MainSite1.png) 

![메인페이지2](/images/MainSite2.png)  
- 배경음악 구현
  - SUNO AI로 노래를 만든 다음, 사이트의 배경음으로 넣을 수 있게 구현했습니다.
  - **HLS 적용**
    - MP3 파일을 그대로 넣었을 때, 로딩이 완료되지 않은 상태에서 재생 시간 변경을 시도하면 슬라이더가 맨 처음으로 돌아가는 문제가 있었습니다.
    - 각 곡에 HLS을 적용하고 백엔드 서버에서 해당 데이터를 갖고 있게 하는 식으로 구현하여 위 문제를 해결했습니다.
    - HLS는 사이트의 어떤 페이지에서든 이용할 수 있습니다.

#### Hobby 메인화면
![메인페이지3](/images/MainSite3.png) 

![메인페이지4](/images/MainSite4.png)  
- `현재 관심사`의 편집 버튼은 로그인 중일 때에만 나타납니다.

![메인페이지5](/images/MainSite5.png)

### 페이지
- 게시글은 [티스토리](https://waltwaez.tistory.com/)에 백업해뒀습니다.

#### 게시판
![공부 게시판](/images/StudyPostList.png)

![애니메이션 감상문 게시판](/images/AnimePostList.png)

#### 글쓰기
![글쓰기](/images/WritePost.png)

#### 아카이브
- 전체 아카이브 페이지
![공부 전체 아카이브](/images/StudyEntireArchive.png)

- 취미 2024년 아카이브 페이지
![취미 2024년 아카이브](/images/HobbyAnnualArchive.png)

#### 게시글
- 게시글 스크린샷을 찍어둔 게 없어서.. 만약 복구할 수 있으면 확보해 보겠읍니다.

### 회원가입과 로그인
![회원가입, 로그인](/images/SignIn&SignUp.png)

![회원가입2](/images/SignUp2.png)

## 참고
### 블로그 시절 작성한 프로젝트 개요
![요약](/images/Project1Summary.png)

