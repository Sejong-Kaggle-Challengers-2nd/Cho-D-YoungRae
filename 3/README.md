# [3]  [아파트 경매가격 예측 경진대회](https://dacon.io/competitions/official/17801/overview/description/)

## 1_직접구현
### Try
1. 일단 가장 필요해보일 것 같은 feature 제외하고 나머지 데이터만 이용해봄
2. feature engineering 가능해보이는 feature
   - `Total_floor`-`Current_floor` : 나누기를 통해 내 층의 비율을 구해볼까 -> 보통 윗 층이 더 비싸지 않나? 처리 후 이 feature 들 drop 할까 남겨둘까
   - `First_auction_date`-`Final_auction_date` : 두 날짜 사이를 빼보기?
3. Target값을 로그 변환했으므로 적절한 RMSE를 얻기위한 exp 변환 -> 값이 너무 크게 나옴 함수를 잘못짰나 학습이 잘못되었나

### Study
1. [`pandas.set_option`](https://pandas.pydata.org/docs/reference/api/pandas.set_option.html?highlight=set_options)
   - `head()` 출력 시 칼럼이 모두 나오지 않아 모두 출력하기 위해 찾아본 것
2. https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy

### Question
1. 2개의 범주만 있을 때도 원핫인코딩이 더 좋나?
   - 내 생각에는 이럴 때는 굳이 원핫인코딩해서 데이터 차원을 늘리지 않아도 될 것 같은데..


## 2_2등 송근일, 이유한 코드 공개 ... 공부
### Study
1. 상관관계가 너무 높은 feature가 있으면 그로 인해 다른 feature의 영향력이 묻힐 수 있다.
   - 적절한 처리를 해주자
2. 수치의 절대 값이 크면 자연스럽게 Variance가 커진다.
3. pandas
   - [`cut()`](https://pandas.pydata.org/docs/reference/api/pandas.cut.html?highlight=cut#pandas.cut)
   - `pd.to_datetime(errors)`
   - DateFrame에서 문자열 메소드를 쓰기 위해 .str 쓰는 것 처럼 datetime 메소드 쓰기위해 .dt 사용하는 듯
   - [`pd.DataFrame.isin()`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.isin.html?highlight=isin#pandas.DataFrame.isin)
4. NumPy
   - [`where()`](https://numpy.org/doc/stable/reference/generated/numpy.where.html)
5. 
