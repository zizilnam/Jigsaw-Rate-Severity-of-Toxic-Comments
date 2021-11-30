# Jigsaw-Rate-Severity-of-Toxic-Comments

--- 

## 문제 정의

 Goal : Predict Ranks Severity of  Comments
 
- Target: Ranks of relative toxicity between comments

 Data : Toxic Comments (text data ) 가 모인 정형 데이터
 
 Solution : Ranking -> Scoring -> Regression  
- Rank를 매기는 것이 대회의 목표.
- Rank를 매기기 위해서 Score를 측정 해야함.
- Score를 측정하기 위해서 문제를 Regression으로 정의.


### Evaluation Metric

Evaluation (Official)

Score is not constrained to any numeric range (e.g., you can predict [0, 1] or [-999, 999]).

There is no tie breaking; tied comment scores will always be evaluated as 0. You could consider using something like scipy.stats.rankdata to force unique value.

1) Loss Function Issue – Margin Ranking Loss or MSE Loss?

2) Other Methods (Discussing)
- Target Column: Degree of Toxic (Classes)
- Loss function: nn.BCEWithLogitsLoss()


## 데이터 정의

## 문제 정의
![image](https://user-images.githubusercontent.com/69458840/144067475-43ac80ff-bfc9-4d0a-b7ed-7930ce49a227.png)

![image](https://user-images.githubusercontent.com/69458840/144067517-60994206-5325-4510-9e66-9ce7ac9f1850.png)

![image](https://user-images.githubusercontent.com/69458840/144067545-4bfa1a35-e77d-4eee-b9e3-b606982f056b.png)

![image](https://user-images.githubusercontent.com/69458840/144067567-22b7ca33-23bc-4508-be18-af82645db6da.png)


작성중...
