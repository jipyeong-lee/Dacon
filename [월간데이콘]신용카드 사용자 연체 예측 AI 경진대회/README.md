# [월간데이콘]신용카드 사용자 연체 예측 AI 경진대회
![image](https://user-images.githubusercontent.com/77089771/147887285-edf19953-3f87-4c16-8b92-76a97336d917.png)
## Evaluation
* Logloss
## 접근방법
*
## REVIEW
* categorical feature를 어떻게 처리하는지가 굉장히 중요한 대회였다.
* categorical feature를 합치는 등 범주형 변수를 처리하는 법에 대해 많은 공부를 하게 되었다.
* 상위권의 솔루션을 보니 모든 categorical feature를 합치는 방법을 사용했었다. 합치는 방법을 알고있었지만 모든 변수를 합칠 생각은 못했던 나를 반성했다.
* CatBoost 단일모델이 상위권에 굉장히 많았는데, CatBoost의 파라미터에 대해 좀 더 깊은 이해를 할 수 있었다.
* categorical한 데이터는 CatBoost의 성능이 굉장히 뛰어나다는 것을 몸소 느꼈다.
## LB
* (public) 0.70813 : 305th / 714
* (private) 0.69224 : 263th / 714
## Reference
* https://dacon.io/competitions/official/235713/codeshare/3119?page=1&dtype=recent - EDA
* https://dacon.io/competitions/official/235713/codeshare/2562?page=4&dtype=recent - AutoLGB
