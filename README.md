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

#### Evaluation (Official)

Score is not constrained to any numeric range (e.g., you can predict [0, 1] or [-999, 999]).

There is no tie breaking; tied comment scores will always be evaluated as 0. You could consider using something like scipy.stats.rankdata to force unique value.

1) Loss Function Issue – Margin Ranking Loss or MSE Loss?

2) Other Methods (Discussing)
- Target Column: Degree of Toxic (Classes)
- Loss function: nn.BCEWithLogitsLoss()

#### MRL(Margin Ranking Loss)

Loss(x1, x2, y) = max(0, -y * (x1 – x2) + margin)

Idea: more_toxic과 less_toxic 간의 차이를 더 벌려서 학습하면 더 좋지 않을까?

한계: x1과 x2의 차이가 적은 경우에 학습이 잘 되지 않는다. 순위를 나누는데 적합하지 않다.

MSE(Mean Squared Error)


MRL보다 학습이 덜 될수는 있지만, x1, x2의 차이가 적은 경우에도 순위를 분류할 수 있다.
우리 모델의 목표는 문장들의 toxic한 정도를 비교해 순위를 예측하는 것이므로 MSE를 사용할 예정이다.
![image](https://user-images.githubusercontent.com/69458840/144067803-935ae262-1544-47a7-8fb4-9d6b1f32f3f5.png)

## 데이터 정의



작성중...
