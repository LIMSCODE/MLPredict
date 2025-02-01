# MLPredict
Apart Price Prediction &amp; CNN Skin Cancer Prediction

## Stack
```
Python
Pandas, numpy
TensorFlow, keras
Matplotlib
랜덤포레스트, XGBoost
k-fold, cross_validate
Maxpool2D, Conv2D, imageDataGenerator, Sequential
```

## 머신러닝: 아파트 가격예측  
랜덤포레스트, XGBoost 알고리즘으로 아파트 매매가격 예측모델 제작 및 비교 
데이터셋: Kaggle의 우리나라 아파트 거래 데이터(지역,날짜,거래금액) (434만 8,785개) 
기술스택: Python, Pandas, TensorFlow, Matplotlib / 랜덤포레스트, XGBoost, k-fold, cross_validate 
모델링: 
-train_test_split, kFold모듈 적용하여 학습진행, 평가척도로 RMSE와 R2사용 (Y_test,pred 비교)
-cross_validate모듈로 훈련데이터가 잘 학습되었는지, 걸린시간 확인 
-테스트데이터(X_test,Y_test)를 모델에적용시켜 학습잘되었는지 평가함(pred=forest.predict(X_test)) 
-랜덤포레스트(RMSE:10593, R2:0.95)와 XGBoost(RMSE:9558, R2:0.96) 학습결과 시각화, XGBoost가 더 정확함 
 
## 머신러닝: 피부암 초기진단  
이미지데이터 전처리 및 이미지학습 인공지능모델(CNN) 제작
기술스택: Python, numpy, Pandas, TensorFlow, imageDataGenerator, keras, Sequential, Maxpool2D, Conv2D, Matplotlib
데이터수집 및 전처리 : Kaggle 피부암이미지 데이터세트 다운로드 / 병명(dx), 진단방법(dx_type)출력 
모델링: 
-Convolution, Pooling과정 반복하여 최종도출된 2차원데이터를 1차원으로 변형 
-model.add(Dense(7,activation:softmax):7가지피부질환 다항분류 
-훈련시 학습률개선과 조기종료 적용 
-피부암 테스트데이터로 병명예측, 실제병명 및 정확도 출력 / 혼동행렬표현  
