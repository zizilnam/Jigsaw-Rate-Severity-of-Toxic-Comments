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

#### MSE(Mean Squared Error)

MRL보다 학습이 덜 될수는 있지만, x1, x2의 차이가 적은 경우에도 순위를 분류할 수 있다.

우리 모델의 목표는 문장들의 toxic한 정도를 비교해 순위를 예측하는 것이므로 MSE를 사용할 예정이다.


## 데이터 정의

### Train data

Train dataset 부재 (Validation_data 존재)

[Important Point] 지난 Kaggle Jigsaw Competition에서의 train data를 가공하여, 모델 학습시킬 예정.

지난 JigsawCompetition의 Task와 다르기 때문에 이번 대회의 Task에 맞게 가공이 필요.

가공 내용: 지난 JigsawCompetition의 데이터의 comment와 toxic_score를 가져와서 합치는 작업

경우에 따라, Validation data도 모델 학습에 사용할 수도 있음.

Past Jigsaw Competitions in Kaggle 
- Toxic Comment Classification Challenge (2017)
- Jigsaw Uninteded Bias in Toxicity Classification (2019)
- Jigsaw Multilingual Toxic Comment Classification (2020)

### Validation Data
#### [Features]
- Worker : 주석을 작성한 전문가의 Id (총 753명)
- less_toxic : 상대적으로 무해한 코멘트
- more_toxic : 상대적으로 유해한 코멘트

#### [특 징]
- 1) Pair Sentences 1세트당 3회 평가받음.  (3명의 다른 Worker가 평가)
- 2) Worker 1명당 평가한 Pair Sentences 수가 다름. ( 예: 8, 68, ...)


![image](https://user-images.githubusercontent.com/69458840/144070042-b7404cc7-8984-4983-b857-24094a901e10.png)


작성중...
