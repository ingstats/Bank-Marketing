## 📘 `README.md` 예시 – PyCaret 프로젝트 환경 구성 및 실행 가이드

```markdown
# Bank Marketing - ML Modeling with PyCaret

본 프로젝트는 `PyCaret` 기반의 머신러닝 자동화 분석 파이프라인 구축을 위한 실습 환경입니다.

## 📁 프로젝트 구조
```
bank-marketing/
├── data.csv               # 데이터 파일
├── environment.yml        # Conda 가상환경 구성 파일
└── notebooks/
    └── analysis.ipynb     # 분석용 노트북
```

---

## 📦 가상환경 설치 및 실행 방법

### 1️⃣ Conda 환경 생성

먼저 Conda 가상환경을 아래 명령어로 생성합니다:

```bash
conda env create -f environment.yml
```

> ⚠ **주의:** 환경 생성 도중 아래 오류가 발생할 수 있습니다:

```plaintext
PackagesNotFoundError: The following packages are not available: pycaret=3.0.0
```

이 경우 `pycaret` 패키지가 conda에서 바로 검색되지 않는 경우가 있으며, **pip 설치 방식으로 우회 설치**하거나, **PyCaret 버전을 조정**해야 할 수 있습니다.

### 🔁 해결 방법 (옵션 A 또는 B 중 선택)

#### ✔ 옵션 A. 환경 생성 후 pip로 pycaret 설치
```bash
conda create -n pycaret-env python=3.10
conda activate pycaret-env
pip install pycaret
```

#### ✔ 옵션 B. conda-forge에서 설치 가능한 최신 호환 버전으로 구성 (권장)
```bash
conda install -c conda-forge pycaret
```

---

### 2️⃣ 환경 활성화

```bash
conda activate pycaret-env
```

> ❗ 오류: `EnvironmentNameNotFound: Could not find conda environment: pycaret-env`  
→ 위 오류가 발생할 경우, 환경이 정상적으로 생성되지 않았습니다. 아래 명령어로 환경 확인:

```bash
conda env list
```

→ 환경이 없다면 다시 생성하거나 `environment.yml`에서 환경 이름을 수정하세요.

---

### 3️⃣ Jupyter Lab 실행

```bash
jupyter lab
```

브라우저에서 실행되며 `.ipynb` 파일을 열어 분석을 진행할 수 있습니다.

---

## 🔎 예시 코드 (환경 테스트용)

```python
from pycaret.classification import setup, compare_models
import pandas as pd

df = pd.read_csv("data.csv")
clf_setup = setup(data=df, target='y', session_id=42)
best_model = compare_models()
```

---

## 📌 Troubleshooting

| 문제 | 해결 방법 |
|------|---------------------------|
| pycaret 설치 오류 | `pip install pycaret` 사용 |
| environment.yml 오류 | 파일 이름 확인 (`enviroment.yml` ❌ → `environment.yml` ✅) |
| 환경 생성 오류 | `conda env remove -n pycaret-env`로 기존 환경 삭제 후 재생성 |
| numpy/pandas 충돌 | `numpy==1.24.4`, `pandas==1.5.3` 버전 명시 |

---

## 🔗 참고 링크
- [PyCaret 공식 문서](https://pycaret.gitbook.io/docs/)
- [Anaconda 공식 문서](https://docs.anaconda.com/)
- [Conda-forge 패키지 검색](https://anaconda.org/conda-forge/pycaret)
```

---
