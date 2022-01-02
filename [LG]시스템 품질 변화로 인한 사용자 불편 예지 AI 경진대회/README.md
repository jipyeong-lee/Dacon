# [LG]시스템 품질 변화로 인한 사용자 불편 예지 AI 경진대회
![image](https://user-images.githubusercontent.com/77089771/147881517-27f0243d-1434-4ae1-8863-2d53da3423bd.png)
## Evaluation
* ROC-AUC
## 접근방법
* ID 별로 groupby를 통한 feature 생성
* unstack을 통한 multi-groupby feature 생성
* sklearn의 SelectFromModel 패키지를 통한 feature selection(threshold : 4.5*mean ~ 5.0*mean 데이터셋마다 상이함)
* Bayesian Optimization
* LightGBM, CatBoost
* OOF(5Fold)
## REVIEW
* 머신러닝을 배우고 처음 참여한 대회이다.
* ROC-AUC에 대한 이해도가 부족했다. 평가지표에 대한 이해도가 반드시 수반되어야 함을 깨달았다.
* 무식하면 용감하다는 것을 몸소 느낀 대회였다. 수많은 경우의 수를 모두 groupby, multi-groupby를 통해 구현했다.
* 시계열적인 요소를 고려하지 못했다. 시계열적인 feature는 다른 사람이 올려준 코드 공유를 참고했다.(untitled.ipynb)
* 하이퍼파라미터를 탐색함에 있어서 Grid search, Random search같은 기본적인 방법을 사용하지 않고 새로 배웠던 Bayesian Optimization을 사용했다.
* 코드가 너무 길다. 일부 반복적인 부분은 함수를 통해 처리했어야 했다. 좀 더 효율적인 코딩이 필요함을 느꼈다.
## LB
* public 0.84416 : 26th / 418
* private 0.84005 : 24th / 418
## Reference
* https://dacon.io/competitions/official/235687/codeshare/2356?page=1&dtype=recent - 시계열 관련 feature
* https://dacon.io/competitions/official/235687/codeshare/2422?page=1&dtype=recent - EDA
