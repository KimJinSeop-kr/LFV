# Protein Analysis

학사 졸업연구 · 효모 단백질의 분비 성능과 N말단 무질서 영역(IDR)의 연관성 분석

> Data-driven decoding of yeast protein secretion rules for mass production of
> useful proteins : N-terminal intrinsic disorder regions

### 데이터

한국생명공학연구원(KRIBB) 제공
TFP 변이체 24종 × Biopolymer Synthase 6종의 아미노산 서열 및 정규화된 분비 점수

### 접근

AlphaFold2로 예측한 3D 구조에서 잔기별 신뢰도 지표인 pLDDT를 IDR 추정에 활용.
pLDDT 50 이하 잔기의 비율을 TFP 구간과 POI 구간으로 나누어 특성화하고,
서열 기반 물리화학 특성(분자량, pI, GRAVY 등)과 함께 분비 점수와의 관계를 분석.

### 결과

Spearman 상관계수

| 특성 | 상관계수 | p-value |
| --- | --- | --- |
| TFP_IDRs_Ratio | 0.2182 | 0.0085 |
| POI_IDRs_Ratio | -0.3100 | 0.0001 |
| GRAVY | 0.2137 | 0.0101 |

- 상반된 방향의 두 IDR 특성을 PCA로 압축해 상관계수 0.3705로 개선
- RandomForest 회귀 : R² 0.644 · RMSE 27.029
- Gini 기반 특성 중요도 : GRAVY 37.5% · TFP_IDRs_Ratio 36.3% · POI_IDRs_Ratio 26.2%

### ColabFold_auto.ipynb

ColabFold 기본 노트북은 서열을 하나씩 입력받아 개별 저장하는 구조.
데이터프레임에 서열을 저장하고 start_index / end_index로 범위를 지정해
일괄 처리하도록 개조하였고, rank01~03 PDB를 Google Drive에 저장하면서
데이터프레임에 통합해 JSON으로 관리하도록 구성.

### 참고

이 폴더에는 구조 예측 자동화 노트북만 포함되어 있으며,
특성 추출 및 통계·회귀 분석 코드는 포함하지 않았습니다.
