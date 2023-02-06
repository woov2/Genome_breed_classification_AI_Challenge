# Dacon [데이콘 유전체 품종 분 AI 경진대회](https://dacon.io/competitions/official/236035/overview/description)에서 진행된 코드입니다.
## Data Pre-processing
* 'father','mother','gender' 변수는 동일한 값만이 존재하여 모델링에 안좋은 영향을 줄 것으로 판단하여 제거
* numeric scaling(standardscaler)
## Feature Engineering
* SNP 정보(name, chrom, cm, pos)를 활용하여 새로운 feature 생성
** name(SNP 명) & chrom(염색체 정보)
** chrom(염색체 정보)
** SNP Total combination
** cm(Genetic distance)
** SNP G,C,A mathematical feature
* catboost encoder를 적용하여 catboost의 모델내부 인코딩 방식을 활용해보고자 함
## Over-sampling
* BorderlineSMOTE
## Model
* VotingClassifier
** BaggingClassifier,DecisionTreeClassifier,RidgeClassifier,XGBClassifier,LGBMClassifier,GradientBoostingClassifier,SVC,RidgeClassifierCV,RandomForestClassifier
## Training
* XGBClassifier와 RandomForestClassifier의 가중치를 2로 하여 학습
* KFOLD 교차검증 학습을 진행하지 않고 Total data 학습
## Inference
* 총 175개의 평가데이터 추론
## Score(Macro-F1)
* Public(1.0) 2nd
* Private(0.99362) 1st
