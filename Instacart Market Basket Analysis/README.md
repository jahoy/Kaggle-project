# Instacart Market Basket Analysis

[Dataset](https://www.kaggle.com/c/instacart-market-basket-analysis)

Instacart is challenging the Kaggle community to use this anonymized data on customer orders over time to predict which previously purchased products will be in a user’s next order.

--------------------------------------------------------------
1. DataCleaning
2. Feature Engineering
  - `product_time` : 현재까지 그 제품 구매 횟수(현재까지 상품 구매 횟수)
  - `prod_orders` : 제품에 대한 총 주문횟수
  - `prod_reorders` : 제품에 대한 총 재주문 횟수
  - `prod_reorder_probability` : 한번 사는 거에 비해서 두번 이상 사는 것의 비율
  - `prod_reorder_ratio` : 전체주문중에 재주문율
  - `user_orders` : 유저마다 총 주문 횟수
  - `user_period` : 유저의 활동기간 (유저 첫 구매후 이후의 기간)
  - `user_mean_days_since_prior` : 유저가 제품을 구매하러오는 재방문하는 평균 주기(기간)
  - `user_total_products`: 유저별 total 제품 구매수
  - `eq_1`: 유저가 1번 재구매한 제품 수
  - `gt_1`: 유저가 1번이상 주문한 제품의 수
  - `user_reorder_ratio` : 재주문율(유저가 1번이상 주문한 제품의 수에 대한 1번 이상 재구매한 수에 대한 비율)
  - `user_distinct_products` : 유저가 얼마나 제품을 고루 샀는지 (얼마나 유니크한 제품의 갯수를 구매했는 지)
  - `user_average_basket` :유저가 평균적으로 얼마나 장바구니에 제품들을 담았는지
  - `up_orders` : 제품 선호도 지수 (유저당 그 제품을 얼마나 샀는지)
  - `up_first_order`: 1번의 order에서 제품을 여러개 샀을때 제품을 가장 먼저 사는지 ~ 중요해서 가장 먼저 샀을 수 있기에
  - `up_last_order`: 1번의 order에서 제품을 여러개 샀을때 제품을 가장 늦게 샀는지 ~ 중요해서 마지막에 꼭 골랐을 수 있기에
  - `up_average_cart_position`: 각 제품들이 장바구니에 평균적으로 몇번째 순서에 담겼는지
  - `up_order_rate`: 제품당 주문 비율
  - `up_orders_since_last_order`: 마지막 주문후 얼마나 지났는지
  
3. Word2Vec (NLP) : product name -> vectorize
  - product name을 vectorize 시켜서 서로 비슷한 이름끼리의 product끼리 연관성을 줌
4. Modeling - LightGBM model   - 상위 15% 성적 ( TOP 15% in Rank)
  - 많은 데이터량을 처리할 수 있고, 카데고리별로 잘 나눌 수 있는 LightGBM 모델 사용
