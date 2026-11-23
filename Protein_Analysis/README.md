# Protein Analysis

학사 졸업연구 · 효모 단백질의 분비 성능과 N말단 무질서 영역(IDR)의 연관성 분석
한국생명공학연구원(KRIBB) 제공 데이터 · TFP 변이체 24종 × Biopolymer Synthase 6종

AlphaFold2 예측 구조의 pLDDT를 IDR 추정에 활용해 TFP · POI 구간별로 정량화하고
분비 점수와의 관계를 분석.

### 결과

- Spearman 상관 : TFP_IDRs_Ratio 0.2182 · POI_IDRs_Ratio -0.3100 · GRAVY 0.2137
- 두 IDR 특성을 PCA로 압축해 0.3705로 개선
- RandomForest 회귀 : R² 0.644 · RMSE 27.029

### ColabFold_auto.ipynb

서열을 하나씩 처리하던 ColabFold를 일괄 처리 방식으로 개조.
데이터프레임으로 범위를 지정해 입력하고 rank01~03 PDB를 Drive 저장과 동시에 JSON으로 관리.
서열 1,500개를 약 일주일간 하루 1~3회 조작으로 처리.

분석 코드는 포함하지 않았습니다.
