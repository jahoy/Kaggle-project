# Classify Invasive Species 캐글 프로젝트
외래종이 들어왔는지 모니터링하기위해서 image로 부터 외래종인지 예측하는 작업

[Dataset](https://www.kaggle.com/c/invasive-species-monitoring)

1. Classfiy Invasive Species: `InceptionResNetV2` 모델을 활용하였으며, `sequential`방식으로 층을 쌓음  `dropout`, `earlystopping`옵션 등을 주어 overfitting을 방지하였음.  - 상위 4% 성적 

