# [2] [대출 상점 총 매출 예측](https://dacon.io/competitions/official/136/overview/)

## 1_직접구현 ... 해결 못 함
### 시도
- date와 time 합쳐서 datetime 자료형으로 변환 -> 시계열 데이터 다루기

### 공부
- pandas resample()


### 의문
1. 시계열 데이터의 학습법? 예측값? 무엇이 나오나. 제대로 잡히지 않은 개념
2. store 별로 모델을 따로? -> 그렇지는 않을거같은데... 그렇다면 store 별로 다른 수입을 어떻게 예측하나? 원핫 인코딩도 차원이 너무 많아질것 (해결: 후기)
3. Target 값을 무엇으로 해야되나? (해결: 2_공부-4)
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
4. (의문 1-4 해결) Target 값은 말 그대로 내가 예측해야되는 값을 잡는 것이다. 100일 후 매출을 예측해야 되기 때문에 이후 100일 값을 Target 값으로 잡고 그에 맞게 적절히 데이터를 처리하면 된다.


### 후기
- pandas 시계열 데이터를 다루는 법에 너무 익숙하지 않다. 공부하자.
- feature engineering 또 생각하지 못 했다... 


## 3주차 미팅
1. 회귀문제에서 Target 값이 정규분포 형태를 띄는 것이 좋다
   - 로그 변환 등 생각
2. 의문 1-2에서 store별로 모델을 따로 훈련 시켜야되나 생각했다. 생각해보니 store별로 하지 않아도 시계열 데이터는 매출의 흐름을 갖고 있었기 때문에 store 마다의 매출 흐름을 보고 예측해줄 것 같다고 생각했다. store_id 마다 각각 훈련하는 것은 기계학습에 맞지 않다. 
3. `import warnings` : 경고가 많이 뜰 때 경고 제거

### 공부해볼 것
- ARIMA 모델