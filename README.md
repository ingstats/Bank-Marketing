### 📢 **[Bank Marketing 모델링 프로젝트 - 발표 요약]**

---

### ✅ **프로젝트 개요**
- **목표:** 마케팅 응답 (`y`) 예측 모델 개발 (Binary Classification)
- **데이터:** UCI Bank Marketing (전처리 완료 데이터 사용)
- **핵심 평가 지표:** **F2-score 중심 성능 최적화**

---

### 🔍 **전체 모델링 흐름**

1. **전처리 완료 데이터 (`data.csv`) 활용**
2. **ML 기반 모델링 (GridSearch + Undersampling)**
   - LightGBM, XGBoost, GradientBoosting
   - Soft Voting 앙상블
3. **DL 기반 모델링 (PyTorch MLP)**
   - Flexible MLP 구조
   - Focal Loss & EarlyStopping
4. **성능 기준: F2-score 기반 Threshold 튜닝**

---

### 📦 **폴더 구조 (요약)**

```
BANK-MARKETING/
│
├─ ML/         → ML 모델 코드 (LGBM, XGB, GBM 등)
├─ DL/         → 딥러닝 MLP 모델 코드
├─ model/      → 저장된 최종 모델들 (.pkl / .pth)
├─ data.csv    → 전처리된 학습 데이터
├─ ML_final.ipynb / DL_final.ipynb → 최종 실행 코드
├─ environment.yml → 실행 환경 파일
```

---

### ⚙ **사용 기법 요약**

| 항목 | 주요 적용 내용 |
|------|----------------|
| Sampling | RandomUnderSampler |
| 모델 튜닝 | GridSearchCV |
| 평가 기준 | **F2-score + Threshold 최적화** |
| 딥러닝 전략 | Dropout, BatchNorm, FocalLoss |
| 앙상블 전략 | Soft Voting |

---

### 📈 **성능 평가 지표 (Validation 기준)**

- Accuracy / Precision / Recall / F1 / **F2-score**
- ROC AUC
- PR Curve 기반 Threshold Tuning

---

### 💡 **주요 성과**

- **불균형 대응 → FocalLoss + pos_weight 전략**
- **Threshold 튜닝으로 F2-score 최대화**
- **ML+DL 앙상블 → 최종 성능 개선**

---

### 📂 **환경 구성**
```bash
conda env create -f environment.yml
conda activate bank-marketing-env
```

---