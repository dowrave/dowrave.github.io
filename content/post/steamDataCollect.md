+++
date = '2025-04-11T14:19:59+09:00'
draft = true
title = '스팀 데이터 수집 & 리뷰 이진 분류 모델 학습'
summary = "Project03"
+++
# 스팀 데이터 수집 & 리뷰 이진 분류 모델 학습
## 개요
- **의도)** steam의 데이터를 수집해서 날짜별로 동시 접속자와 리뷰의 추이를 파악, 유저의 이탈이 왜 발생하는지 파악하기
- **실제)** 유저가 글로 남긴 리뷰 데이터가 많지 않음, 워드 클라우드를 사용하는 것도 의도에 부합하지 않고, 리뷰 글 수집도 엄청 오래 걸림
- **결과)** `steamspy`를 이용한 매일 데이터 수집, 클라우드에 띄워 자동화, 리뷰 긍/부정 이진분류 모델 작성(실제 사용 X)

## 주요 내용
- **스팀 데이터 수집** : 하루의 데이터만 API에 띄우는 `steamspy`을 매일 추적해 게임들의 추이 관찰(주로 `CCU(하루 최대 동접자)`을 관찰)
  - **자동화** : 매일 수동 실행 -> 로컬 도커 컨테이너 사용 -> EC2 도커 컨테이너 사용
  - **시각화** : 수집된 CCU 데이터는 RDS에 저장, 블로그에서 시각화(하단 `블로그 시절 프로젝트 개요` 참조)
- **스팀 리뷰 이진 분류 모델 학습** : 리뷰 데이터 수집, 하이퍼파라미터 튜닝, 모델 학습
    - 모델은 학습은 해뒀는데 실제 추론에서 사용하지 못했음

## Skills / Used Resources
- **데이터 수집**
  - 게임 : `steamspypi`
  - 리뷰글 : `Steam API`
- **모델 생성 및 훈련**
  - 환경 : `Google Colab`, `GCS(TPU 사용)`
  - 하이퍼파라미터 튜닝 : `keras-tuner(HyperBand)`
  - 프레임워크 : `Tensorflow`
- **데이터 저장** : `MySQL`, `pandas`
- **시각화** : `Recharts`
- **컨테이너** : `Docker, Linux`


## 링크
- [프로젝트 레포지토리](https://github.com/dowrave/SteamDataAnalysis) : 데이터 수집을 어떻게 했고, 어떻게 저장했는지 기록되어 있습니다.
- [리뷰 이진 분류 모델(구글 드라이브, h5)](https://drive.google.com/file/d/1OBSRzRXwaFDP4pZq04Dy5iU6VdBhXwsJ/view)
- [steamspy](https://steamspy.com/)
- [kr-BERT](https://github.com/snunlp/KR-BERT)

# 참고

## 블로그 시절 프로젝트 개요
![3](/images/Project03.png)

