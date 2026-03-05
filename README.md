# Job Recommendation System
이력서와 채용 공고 데이터를 활용하여 개인 맞춤형 채용 공고를 추천하는 추천 시스템을 개발한 프로젝트입니다.

지원자의 이력서 정보와 채용 공고 특징을 학습하여 지원 가능성이 높은 채용 공고를 추천하는 모델을 구축했습니다.
![EDA](images/파일명.png)

🏆 576팀 중 121등 / Recall@5 = 0.17029

Problem

채용 플랫폼에서는 구직자가 수많은 채용 공고 중에서 자신에게 맞는 공고를 찾기 어렵습니다.

따라서 다음 문제를 해결하고자 했습니다.

이력서와 채용 공고 데이터를 활용하여 지원 가능성이 높은 공고를 추천할 수 있을까?

Data
Dataset	Description
recruitment.info	채용 공고 정보
resume.info	이력서 정보
resume_edu	학력 정보

총 17개의 텍스트 컬럼

지원 히스토리 기반 User–Item Interaction 데이터

Feature Engineering
Text Embedding

텍스트 컬럼은 Doc2Vec Embedding을 사용했습니다.

적용 컬럼

희망 직무

경력 직무

직무 키워드

모집 직무

Tech Stack

Python
Pandas
Scikit-learn
Gensim
TensorFlow / Keras

