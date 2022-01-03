# [LH]구내식당 식수 인원 예측 AI 경진대회
![image](https://user-images.githubusercontent.com/77089771/147949668-b881395b-e27a-45a2-a229-2979c4b98cc5.png)
## Evaluation
* MAE
## 접근방법
* data leakage 이슈로 외부 데이터는 음식재료 데이터만 사용(날씨데이터 x)
* 메뉴이름 BPE tokenizer로 token화 시킨 후 feature 생성 시도
* 메뉴를 대분류로 분류 후 원핫인코딩 형태로 인코딩
* 메뉴 대분류 기준 점심 저녁 유사도
* 메뉴에서 사이드와 김치의 순서가 일정 시기부터 바뀜 -> 순서 통일
* 휴일 기준 앞뒷날 feature
* 시계열적 feature(lag 변수)
* 점심 식수인원 수와 저녁 식수인원 수를 각각 regression하는 방법 사용
* sklearn의 SelectPercentile를 통한 feature selection
* CatBoost, NGBoost, LightGBM 세 모델 앙상블
## REVIEW
* public과 private의 LB점수 차이가 심했다.
* BPE tokenizer에 대해 더욱 깊은 이해도가 생겼다.
* NGBoost라는 새로운 모델을 알게 되었다.
* feature selection에 대해 좀 더 깊은 고민을 하게 되었다.
* 시계열을 다루는 것에 대한 공부가 많이 부족함을 알게 되었다.
* 처음 2차에 오른 대회였다. 최종등수가 2차에서 오류없이 통과한 사람들의 등수로 매겨졌다면 등수가 더 높아졌을텐데 좀 아쉽다.
## LB
* (public) 59.26646 : 32th / 480
* (private) 110.73658 : 13th / 480
## Reference
* https://wansook0316.github.io/cv/projects/2019/03/01/%EC%84%9C%EC%9A%B8%EC%8B%9C%EC%B2%AD-%EC%8B%9D%EC%88%98%EC%9D%B8%EC%9B%90-%EC%98%88%EC%B8%A1-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8.html
* https://scienceon.kisti.re.kr/srch/selectPORSrchArticle.do?cn=DIKO0015077964&dbt=DIKO
