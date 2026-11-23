# Ecobi

예산 기반 개인화 식단 추천 서비스의 AI 추천 파이프라인
산학협력 프로젝트(구글 클라우드 코리아) · Vertex AI 노트북 환경

목적 : 데이터 입출력 및 모델 동작 테스트

- `MILP.ipynb` 예산 · 영양 · 알레르기 제약을 만족하는 식단 후보 생성
- `XGBoost.ipynb` 후보별 선택 확률 예측
- `LightFM.ipynb` 식품 단위 학습 후 식단 선호 점수 산출
- `MMR.ipynb` 최근 섭취 이력 기반 반복 패널티
- `result.ipynb` 전 단계 통합 실행 및 최종 순위

### 참고

1. `LightFM.ipynb`의 학습/평가 분리가 1:9로 뒤집혀 있음
2. `MMR.ipynb`의 구현 내용은 실질적으로 반복 패널티이며, MMR(Maximal Marginal Relevance)과는 차이가 있음
3. Google Cloud DB 접속 모듈 `db_connector.py`가 포함되지 않아 실행 불가
