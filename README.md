# Credit Approval MLOps

독일 신용 승인 데이터를 활용해 전체 ML Cycle을 실습하는 프로젝트입니다.
EDA부터 모델 학습, GCP Vertex AI를 통한 모델 등록 및 배포까지 다룹니다.

## 프로젝트 구조

```
├── Credit Approval 데이터를 활용해 ML Cycle 이해하고 모델 등록과 배포.ipynb
├── data/
│   └── german_credit_data.csv
├── img/
└── 데이터명세서.xlsx
```

## 데이터셋

- **출처**: German Credit Risk Data
- **크기**: 1,000개 샘플, 21개 변수
  - 수치형: 6개
  - 범주형: 15개 (타겟 변수 포함)
- **타겟**: `Creditability` (신용 승인 여부, 이진 분류)

## 주요 내용

### 1. EDA
- 데이터 타입 및 기초 통계 분석
- 범주형 변수: 카이제곱 검정으로 타겟과의 연관성 분석
- 수치형 변수: 왜도/첨도 확인, 상관관계 분석
- 정규성 검정 → Box-Cox 변환 → Kruskal-Wallis 비모수 검정

### 2. 데이터 전처리
- Label Encoding, One-Hot Encoding
- StandardScaler / MinMaxScaler
- 통계 검정 기반 피처 선택

### 3. 모델 학습 및 최적화
- RandomForestClassifier 베이스 모델
- RandomizedSearchCV → GridSearchCV 하이퍼파라미터 튜닝
- 평가 지표: ROC-AUC, Precision, Recall, F1

### 4. 모델 해석
- Feature Importance
- SHAP (Shapley Values)

### 5. 모델 등록 및 배포 (Vertex AI)
- joblib으로 모델 직렬화
- Vertex AI Model Registry 등록
- 엔드포인트 생성 및 온라인 예측

## 기술 스택

| 분류 | 라이브러리 |
|------|-----------|
| 데이터 처리 | pandas, numpy |
| 시각화 | matplotlib, seaborn |
| 통계 분석 | scipy |
| 머신러닝 | scikit-learn, imbalanced-learn |
| 모델 해석 | shap |
| 클라우드 배포 | GCP Vertex AI |
