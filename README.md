# Genome breed classfication AI Challenge
### 유전체 정보 품종 분류 AI 개발

# Overview
![Image](https://github.com/user-attachments/assets/46c6c01c-4d4b-41b8-9337-ba4a33d60f64)
![Image](https://github.com/user-attachments/assets/8262802a-6b39-4d73-801e-43d9cad8ffac)

<br/>

## Data Pre-processing
* 'father','mother','gender' 변수는 동일한 값만이 존재하여 모델링에 안좋은 영향을 줄 것으로 판단하여 제거
* numeric scaling(standardscaler)
## Feature Engineering
* SNP 정보(name, chrom, cm, pos)를 활용하여 새로운 feature 생성
1. name(SNP 명) & chrom(염색체 정보)
2. chrom(염색체 정보)
3. SNP Total combination
4. cm(Genetic distance)
5. SNP G,C,A mathematical feature
* catboost encoder를 적용하여 catboost의 모델내부 인코딩 방식을 활용해보고자 함
## Over-sampling
* BorderlineSMOTE
## Model
* VotingClassifier
1. BaggingClassifier
2. DecisionTreeClassifier
3. RidgeClassifier
4. XGBClassifier
5. LGBMClassifier
6. GradientBoostingClassifier
7. SVC
8. RidgeClassifierCV
9. RandomForestClassifier
## Training
* XGBClassifier와 RandomForestClassifier의 가중치를 2로 하여 학습
* KFOLD 교차검증 학습을 진행하지 않고 Total data 학습
## Inference
* 총 175개의 평가데이터 추론
## Score(Macro-F1)
* Public(1.0) 2nd
* Private(0.99362) 1st
