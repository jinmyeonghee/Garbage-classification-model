# 재활용쓰레기 분류 모델
**프로젝트기간 : 2023.02.02 ~ 2023.02.07**

**사용 언어 : python**

**개발환경 : macOS Ventura 13.1, visual studio code**

**사용모델 : MobileNet, ResNet**

***
### 프로젝트 개요
- 폐기종류별로 이미지를 학습하고, 분리하는 모델 생성. 재활용쓰레기들의 재활용률을 높이고, 환경보존에 도움이 되고자 프로젝트를 진행

### 프로젝트 배경
- 비대면, 원격수업, 재택근무 등 생활형태가 변하면서 택배와 음식배달, 포장 등이 늘어남. 재활용쓰레기들이 분리수거가 제대로 이루어지지않아 그대로 폐기처분되기 때문에 심각한 환경오염을 야기시킨다.

   
## 프로젝트 내용
### 1. 데이터소개와 ImageDataGenerator
<img width="721" alt="스크린샷 2023-08-10 오후 2 50 02" src="https://github.com/jinmyeonghee/Garbage-classification-model/assets/114460314/c067c871-bdcc-4713-ad06-f6eec823e620">


### 2. CNN으로 모델 구축, 전이학습을 이용해 2개 모델 추가 제작
- 사전학습모델 : MobileNet, ResNet 사용
<img width="771" alt="스크린샷 2023-08-10 오후 2 51 33" src="https://github.com/jinmyeonghee/Garbage-classification-model/assets/114460314/6030308b-124a-4211-8375-c07f1dc91e15">


### 프로젝트 평가
- 데이터 이미지의 수가 적어 과적합이 될 수 있기 때문에 학습데이터를 조금씩 변형시켜 양을 늘리는 방식인 ImageDataGenerator로 데이터 증강을 한 후 학습.  
- 사전학습모델을 사용한 이유 : 훈련시간을 절약하고, 신경망의 성능을 향상시키며 많은 데이터를 필요로 하지 않는다는 장점


### 프로젝트 한계 및 개선방안
- 건전지는 종이로 예측하였는데 데이터의 metal이미지에는 캔류로만 이루어져 있어 건전지는 분류하지 못함

  -> 재활용 분류에는 더 세세한 카테고리가 있지만 데이터의 한계로 6개의 클래스로 분류한 것이 아쉬움. 비닐, 스티로폼, 배터리 등 으로 나누어져 있는 데이터로 학습하여 실제로 사용할 수 있는 모델을 만들 수 있음.
- 이미지분류문제이다 보니 GPU의 한계도 있었고, 학습시간도 오래걸려 여러가지 사전학습모델을 사용해보거나 파라미터 조정을 해보지 못한 점이 아쉬움.
