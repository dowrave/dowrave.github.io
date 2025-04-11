+++
date = '2025-04-11T14:00:05+09:00'
draft = false
title = '한글 단일 글자 필기체 이미지 분류'
summary = 'Project02'
+++
# 한글 단일 글자 필기체 이미지 분류
## 개요
네이버 사전 등에 있는 **손글씨 이미지를 문자열로 바꿔주는 기능**을 참고하여 진행한 프로젝트입니다.

## 주요 내용
![모델 실험](/images/Project2Usage.png)
- **한글 1글자**를 그려넣은 **이미지를 인식해서 컴퓨터 문자로 바꾸는 필기 인식기** 기능
- 이미지는 **2350개**의 글자 중에서 분류
- 구글 코랩에서 텐서플로우를 사용하여 모델 학습을 진행
- 처음에는 로컬에서만 작동
- AWS 블로그를 사용한 후에는 모델을 백엔드`Django`에 넣고, 프론트엔드`ReactPainter`의 이미지를 전달하는 방식으로 웹에서 추론 기능 구현

## Skills / Used Resources
- **프레임워크** : `Tensorflow`
- **이미지 작성** : (로컬) `OpenCV` / (웹) `ReactPainter`
- **모델 학습** : `Google Colab`
- **데이터셋** : `phd08`
- **모델** : `GoogLeNet` 간소화 모델(하단 링크 참조)
  - [모델 논문 1](https://scienceon.kisti.re.kr/commons/util/originalView.do?cn=JAKO201823955287871&oCn=JAKO201823955287871&dbt=JAKO&journal=NJOU00292001)
  - [모델 논문 2](https://scienceon.kisti.re.kr/commons/util/originalView.do?cn=JAKO201630762630914&oCn=JAKO201630762630914&dbt=JAKO&journal=NJOU00431883)


## 결과
- 모델 학습 과정에서 검증 정확도는 98.47%이었으나 **실제 손글씨 이미지에 대한 정확도는 다소 많이 떨어졌습니다.**
1) phd08 데이터셋은 9가지 **폰트에 대한 데이터셋**.
2) 구글 코랩의 메모리 이슈로 각 글자에 대해 1가지 폰트, 50개의 데이터만 사용이 가능했습니다.
   - 그래서 학습시킨 폰트와 비슷한 모양으로 넣을 때에는 성능이 올라가는 체감이 있었습니다.
3) 손글씨 데이터셋이 없어서 손글씨에 대한 측정수단이 부재했기 때문에, 직접 이미지를 만들어서 테스트하는 방법밖에 없었습니다.


## **링크**
- [프로젝트 레포지토리, 전체적인 구현 내용](https://github.com/dowrave/Project01_HandWriting)
- [h5 모델(구글 드라이브)](https://drive.google.com/file/d/1O5THjolq-CbqDwkYsBykZmE-a5TIHuWI/view)
- 데이터셋
  - [phd08 데이터셋](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART001293992)
  - [최초 사용하려 했던 데이터셋](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=81)
  - [PE92](https://github.com/callee2006/HangulDB)

## 참고
### 블로그 시절 작성한 프로젝트 개요
![프로젝트2개요](/images/Project2-ImageClassification.png)
