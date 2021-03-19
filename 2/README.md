# [2] [대출 상점 총 매출 예측](https://dacon.io/competitions/official/136/overview/)

## 1_직접구현 ... 해결 못 함
### 시도
- date와 time 합쳐서 datetime 자료형으로 변환 -> 시계열 데이터 다루기

### 공부
- pandas resample()


### 의문
1. 시계열 데이터의 학습법? 예측값? 무엇이 나오나. 제대로 잡히지 않은 개념
2. store 별로 모델을 따로? -> 그렇지는 않을거같은데... 그렇다면 store 별로 다른 수입을 어떻게 예측하나? 원핫 인코딩도 차원이 너무 많아질것
3. Target 값을 무엇으로 해야되나?
  - 다음 100일 매출 총합?
  - 일 별 다음날 매출?


## 2_2nd HELLOCRYPTO 코드 공부

### 공부
1.  원하지 않는 데이터 삭제하는 법 -> 사용하려하면 생각나지 않을 때 많았다.
```python
df = df[df.store_id != s]
```
2. pandas.DataFrame 메소드
   - [asfreq()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.asfreq.html?highlight=asfreq#pandas.DataFrame.asfreq)
   - [rolling()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.rolling.html?highlight=rolling#pandas.DataFrame.rolling)
   - last()

3. feature engineering 이용


### 후기
- pandas 시계열 데이터를 다루는 법에 너무 익숙하지 않다. 공부하자.
- feature engineering 또 생각하지 못 했다... 

## 3_Facebook prophet을 활용하여 예측모델 만들기

### 공부
1. `Prophet` : 다른 시계열 모델에 비해 간단하게 모델을 만들 수 있다.