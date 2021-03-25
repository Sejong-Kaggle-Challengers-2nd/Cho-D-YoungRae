# [3]  [아파트 경매가격 예측 경진대회](https://dacon.io/competitions/official/17801/overview/description/)

## 1_직접구현 ... 진행중
### Try
1. 일단 가장 필요해보일 것 같은 feature 제외하고 나머지 데이터만 이용해봄
2. feature engineering 가능해보이는 feature
   - `Total_floor`-`Current_floor` : 나누기를 통해 내 층의 비율을 구해볼까 -> 보통 윗 층이 더 비싸지 않나? 처리 후 이 feature 들 drop 할까 남겨둘까
   - `First_auction_date`-`Final_auction_date` : 두 날짜 사이를 빼보기?

### Study
1. [`pandas.set_option`](https://pandas.pydata.org/docs/reference/api/pandas.set_option.html?highlight=set_options)
   - `head()` 출력 시 칼럼이 모두 나오지 않아 모두 출력하기 위해 찾아본 것
2. https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy

### Question

