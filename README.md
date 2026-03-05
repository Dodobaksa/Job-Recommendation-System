# Job Recommendation System
이력서 기반 맞춤형 채용 공고 추천 시스템
<p align="center">
  <img src="images/대국민.png" width="400">
</p>
---

# 1. 개요 (Overview)

### Objective
이력서 정보, 채용 공고, 지원 히스토리 데이터를 활용하여  
**구직자에게 적합한 채용 공고를 추천하는 AI 기반 추천 시스템 개발**

### Project Info

| 항목 | 내용 |
|---|---|
| Competition | 제1회 국민대학교 AI 빅데이터 분석 경진대회 |
| Duration | 2023.10.16 ~ 2023.11.13 (약 4주) |
| Participants | 576 teams |
| Result | **121등 / Recall@5 : 0.17029** |

### Role
- EDA 및 데이터 분석
- 텍스트 feature embedding
- 추천 모델 개발 및 실험

---

# 2. 배경 (Background)

채용 플랫폼에서는 수많은 채용 공고와 구직자 정보가 존재하지만  
구직자가 **자신에게 적합한 공고를 찾기 어렵고**,  
기업 또한 **적합한 인재를 찾는 데 많은 비용이 발생**합니다.

본 프로젝트는

- 이력서 데이터
- 채용 공고 데이터
- 지원 이력 데이터

를 활용하여 **개인 맞춤형 채용 공고 추천 시스템**을 구축하는 것을 목표로 합니다.

---

# 3. 데이터셋 설명 (Dataset)

### Data Source
HR 플랫폼 **Scout**에서 제공한 채용 데이터

### Data Components

| Dataset | Description |
|---|---|
| resume.info | 구직자 이력서 정보 |
| recruitment.info | 채용 공고 정보 |
| apply_history | 지원 기록 데이터 |

### Data Size

| 데이터 | 규모 |
|---|---|
| 지원 데이터 | 57,946 records |
| resume features | 12 columns |
| recruitment features | 5 columns |

### Feature Engineering

- **Doc2Vec Embedding**
  - job keywords
  - resume job preference
  - career job code

- **TF-IDF + KMeans**
  - 자격증 텍스트 clustering

- **Fourier Transform**
  - resume 등록일 / 수정일

- **Scaling**
  - MinMax Scaling

---

# 4. 방법 요약 (Method)

추천 성능을 개선하기 위해 다양한 추천 모델을 실험했습니다.

### Models

- Auto Encoder
- Wide & Deep
- Deep SVDD
- Layer Ensemble

### Model Pipeline
Resume Data
↓
Recruitment Data
↓
Text Embedding (Doc2Vec)
↓
Feature Scaling
↓
Recommendation Model
↓
User-Job Matching


### Key Technique

**1️⃣ Auto Encoder 기반 추천**

User-Item Matrix를 학습하여  
사용자가 지원할 가능성이 높은 채용 공고를 예측

**2️⃣ Masked MSE Loss**

조회하지 않은 아이템까지 추천되는 문제를 해결하기 위해  
Masked MSE Loss 적용

**3️⃣ Layer Ensemble**

User latent vector + Item latent vector를 결합하여  
추천 성능 향상

---

# 5. 결과 요약 (Results)

### Competition Result

| Metric | Score |
|---|---|
| Recall@5 | **0.17029** |
| Rank | **121 / 576 teams** |

### Key Findings

- 이력서 업데이트가 빠를수록 지원 빈도가 높음
- 경력이 적은 지원자가 더 많은 공고에 지원
- 약 **33%의 지원자가 동일 지역 회사에 지원**


---

# 6. Notion Documentation

프로젝트 전체 분석 과정 및 EDA 결과는 아래 노션에서 확인할 수 있습니다.

👉 **[Notion Link]((https://www.notion.so/1-AI-d21eb5127e7c4a34ace111ff04984fae))**




