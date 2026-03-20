# MAP3K5(ASK1) IC50 Prediction

SMILES 기반으로 화합물의 **MAP3K5(ASK1) 저해 활성(IC50)** 을 예측하는 머신러닝 프로젝트입니다.  
ChEMBL과 PubChem 데이터를 활용하여 분자 특성을 추출하고 회귀 모델을 통해 pIC50 값을 예측합니다.

---

## Overview

- **Task**: IC50 → pIC50 변환 후 회귀 예측  
- **Target**: MAP3K5 (ASK1)  
- **Data**: ChEMBL + PubChem  
- **Best Model**: RandomForestRegressor  

---

## Method

1. **Preprocessing**
   - IC50 데이터 필터링
   - pIC50 변환
   - 중복/결측 제거

2. **Feature Engineering**
   - Morgan Fingerprint
   - RDKit Descriptor (MolWt, LogP, TPSA 등)

3. **Modeling**
   - RandomForest / XGBoost / LightGBM 비교
   - 최종: **RandomForest 선택**

---

## Results

- RMSE: 0.3986  
- R²: 0.9855  
- DACON Score: 0.61311  
- Rank: 12 / 938  (08.16.25 기준)

---

## Files

- `ChEMBL.ipynb` → 데이터 전처리  
- `CAS.ipynb` → 추가 데이터 분석  
- `model*.ipynb` → 모델 실험 및 튜닝  
