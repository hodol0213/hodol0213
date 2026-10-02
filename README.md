# 안호용(An Hoyong) - Backend, Data Engineer

### 데이터의 흐름을 이해하고, 서비스로 연결하는 개발자

**Data Engineering · Backend Development · Applied AI**

데이터 정제부터 모델 학습, 서버 연동, 실시간 전달까지 직접 연결해 왔습니다.<br>
데이터가 정확하게 처리되고 안정적으로 전달되는 시스템을 만들고 싶습니다.

<p>
  <a href="https://github.com/hodol0213"><img src="https://img.shields.io/badge/GitHub-hodol0213-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub hodol0213"></a>
  <a href="mailto:hodol0213@naver.com"><img src="https://img.shields.io/badge/Email-hodol0213%40naver.com-03C75A?style=flat-square&logo=naver&logoColor=white" alt="Email"></a>
  <a href="https://clever-honey-b91.notion.site/bbe720a6f6cb82ec918d01d5fa3608eb"><img src="https://img.shields.io/badge/Portfolio-Notion-000000?style=flat-square&logo=notion&logoColor=white" alt="Notion Portfolio"></a>
</p>

---

## About Me

안녕하세요. **데이터 처리와 AI 서비스 연동을 경험한 개발자 안호용**입니다.

- **실시간 서비스** — 수어톡 팀장으로 FastAPI 기반 백엔드와 AI 모델 연동을 담당했습니다.
- **데이터 품질** — 한국어 텍스트 약 300만 건을 정제하고, 리뷰 감성 분석 모델 개발에 참여했습니다.
- **탐지 파이프라인** — 네트워크 패킷을 수집·가공해 Random Forest 추론으로 연결하는 NIDS를 구현했습니다.
- **협업 방식** — 문제와 판단 근거를 기록하고, 진행 상황을 공유하며 맡은 일을 끝까지 해결합니다.

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black" alt="C">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git">
</p>

| 분야 | 기술 및 활용 경험 |
| :--- | :--- |
| Backend | FastAPI 비동기 API, Socket.IO 기반 채팅, SSE 알림, 서버·모델 연동 |
| Database | PostgreSQL 영구 데이터 저장, Redis 프레임·임시 데이터 처리 |
| Data Processing | Python 텍스트 정제·정규화, 학습 데이터 구성, 패킷·플로우 특징 추출 |
| Machine Learning | PyTorch, scikit-learn, Random Forest, BERT·ELECTRA 사전학습 및 파인튜닝 |
| AI Integration | MediaPipe, LSTM 추론 연동, Gemini API를 활용한 문장 후처리 |
| Systems | Linux, Git, Wireshark, tcpreplay, C 기반 마이크로컨트롤러 제어 |

**학습·프로젝트에서 접한 기술:** Docker, Nginx, Apache Kafka, Apache Airflow, Apache Spark, Hadoop, MySQL

## Featured Projects

### 01. SignTalk · 수어톡

**수어·한글 양방향 번역 채팅 서비스**  
`2026.01 – 2026.03` · 4인 팀 · **팀장 / 백엔드 및 서버·모델 연동**

농인과 청인이 수어와 한글로 대화할 수 있도록, AI 번역 기능을 실시간 채팅 서비스에 연결했습니다.

- **비동기 서버 구현:** FastAPI 기반으로 요청을 처리하고 채팅 서버와 번역 모델의 데이터 흐름을 연결했습니다.
- **저장 구조 분리:** 수어 프레임·좌표 등 임시 데이터는 Redis로, 회원 정보와 채팅 기록은 PostgreSQL로 관리하도록 구성했습니다.
- **번역 결과 전달:** 수어 인식 결과인 글로스를 Gemini API로 자연스러운 한국어 문장으로 변환하는 흐름을 연동했습니다.
- **재난 알림 개선:** 재난 알림 전달에 SSE를 적용해 서버에서 클라이언트로 이벤트를 보내도록 구성했습니다.
- **예외 처리:** 미등록 단어와 조회 실패 등 번역·검색 연동 과정에서 발생하는 예외 상황을 고려했습니다.

**핵심 경험:** 모델의 입력·출력 형식을 서버와 맞추고, 데이터의 저장 목적과 통신 방향에 따라 처리 구조를 설계했습니다.

`Python` `FastAPI` `PostgreSQL` `Redis` `Socket.IO` `SSE` `Gemini API`

[프로젝트 상세 보기 ↗](https://www.notion.so/2026-01-2026-03-1ed720a6f6cb820a8d1401f610d8fa96)

<details>
<summary><b>서비스의 AI 처리 흐름</b></summary>

- **수어 → 한글:** MediaPipe 랜드마크 추출 → LSTM 글로스 분류 → Gemini 문장 후처리 → 채팅 전달
- **한글 → 수어:** KoBART 글로스 변환 → PostgreSQL 영상 매핑 및 fastText 유사도 검색 → 수어 영상 재생
- 수어 인식 실험에서는 포즈·양손 좌표를 **96차원 특징 벡터, 8프레임 시퀀스**로 구성했습니다.

위 내용은 팀 프로젝트 전체의 처리 흐름이며, 제 담당 범위는 백엔드와 서버·모델 연동입니다.

</details>

---

### 02. ReBERT & ReELECTRA

**온라인 리뷰 특화 한국어 감성 분석 모델**  
`2025.10 – 2025.11` · 4인 팀 · **데이터 정제 / 모델 학습·평가 참여**

다양한 출처의 한국어 텍스트를 정제하고, 사전학습과 도메인 적응 학습을 거쳐 리뷰의 긍정·부정을 분류했습니다.

- **약 300만 건의 텍스트 정제:** 출처별 데이터 형식을 통일하고, 비표준 문자 제거·반복 표현 정규화·짧은 문장 제거 등의 규칙을 적용했습니다.
- **단계별 학습:** 일반 한국어 사전학습 → 리뷰 도메인 적응 사전학습(DAPT) → 감성 분류 파인튜닝을 수행했습니다.
- **경량 모델 실험:** 제한된 학습 자원에 맞춰 ReBERT를 small 규모로 구성하고, BERT·ELECTRA 계열 모델의 분류 결과를 비교했습니다.

| 팀 프로젝트 평가 결과 | Accuracy | F1 Score |
| :--- | ---: | ---: |
| ReBERT | **89.53%** | **91.53%** |
| ReELECTRA | 88.98% | 90.90% |

*프로젝트 최종 보고서와 발표자료의 성능 평가표 기준입니다.*

**핵심 경험:** 데이터 품질과 학습 조건을 함께 관리하고, 모델 규모와 평가 결과를 구분해 해석했습니다.

`Python` `PyTorch` `BERT` `ELECTRA` `WordPiece` `soynlp` `DAPT`

[프로젝트 상세 보기 ↗](https://www.notion.so/BERT-ELECTRA-pre-training-2025-10-2024-11-ebd720a6f6cb820d88f201d63d7367d2)

---

### 03. Random Forest NIDS

**머신러닝 기반 네트워크 침입탐지 시스템**  
`2025.03 – 2025.09` · 졸업 프로젝트 · **데이터 전처리 / 모델 비교 / 탐지 파이프라인 구현**

네트워크 패킷을 수집하고 연결 단위로 특징을 추출해, 정상·공격 여부를 판단하는 탐지 시스템을 구현했습니다.

- **모델 비교:** NSL-KDD 데이터셋으로 분류 모델을 비교하고 Random Forest를 선택했습니다.
- **판단 임계값 조정:** 공격 미탐을 줄이기 위해 임계값을 `0.015`로 설정하고 정밀도·재현율의 변화를 비교했습니다.
- **패킷 처리:** 5-tuple 기반 패킷 그룹화와 시간 윈도우를 활용해 추론에 필요한 특징을 구성했습니다.
- **동작 검증:** Linux 환경에서 tcpreplay로 Teardrop·Slammer·Nmap Scan 트래픽을 재생하며 탐지 흐름을 확인했습니다.

| NSL-KDD 평가 지표 | 결과 |
| :--- | ---: |
| Accuracy | 약 **94%** |
| Attack Recall | 약 **98%** |
| F1 Score | 약 **95%** |
| ROC-AUC | **0.962** |

*졸업논문의 데이터셋 평가 결과입니다. 실시간 트래픽 재생 검증과는 구분하며, 실제 운영 환경의 탐지 성능을 의미하지 않습니다.*

**핵심 경험:** 공격 미탐과 오탐의 균형을 고려하고, 학습 데이터 평가와 실시간 입력 처리의 차이를 확인했습니다.

`Python` `scikit-learn` `Random Forest` `Scapy` `Linux` `Wireshark` `tcpreplay`

[프로젝트 상세 보기 ↗](https://www.notion.so/Random-Forest-NIDS-2025-06-2025-09-681720a6f6cb828682f901eb3abd9984)

## More Projects

<details>
<summary><b>ATmega128 · XOR 기반 대칭키 암호화 실습 시스템</b> — 2025.04 – 2025.06</summary>

C 언어로 XOR 암호화·복호화와 하드웨어 입출력 제어를 구현한 마이크로프로세서 프로젝트입니다.

- 스위치 외부 인터럽트로 암호화·복호화 모드를 전환했습니다.
- UART 시리얼 통신으로 PC와 데이터를 송수신했습니다.
- LED·FND로 처리 결과를 표시하고, 부저로 완료 상태를 알렸습니다.
- 비트 연산과 레지스터 설정을 통해 소프트웨어 로직을 하드웨어 동작으로 연결했습니다.

`C` `ATmega128` `UART` `Interrupt` `Bitwise Operations`

[프로젝트 상세 보기 ↗](https://www.notion.so/ATmega128-XOR-2025-04-2025-06-637720a6f6cb83f892678100d92663d0)

</details>

<details>
<summary><b>Arduino · 라인 트레이서</b> — 2020.09 – 2020.12</summary>

적외선 센서로 검은 선을 감지하고, 모터 제어로 주행 방향을 보정하는 자동차를 제작했습니다.

- 센서 입력에 따라 좌우 DC 모터의 회전 방향과 속도를 제어했습니다.
- 교환학생 팀원과 번역 도구를 활용해 소통하며 기체 설계와 주행 로직을 통합했습니다.

`Arduino` `C/C++` `IR Sensor` `Motor Control`

</details>

## Education & Certifications

**숭실대학교 전자정보공학부 전자공학전공**  
**멀티캠퍼스 데이터 엔지니어 과정**

| 자격 및 어학 | 취득 연도 |
| :--- | :---: |
| 정보처리기사 | 2026 |
| SQLD | 2026 |
| ADsP | 2026 |
| TOEIC Speaking IH | 2025 |

## How I Work

- **데이터 흐름부터 확인합니다.** 수집·처리·저장·전달 중 문제가 발생한 구간을 좁혀 원인을 찾습니다.
- **판단 근거를 남깁니다.** 기술 선택의 이유와 실험 조건을 기록해 팀이 같은 기준으로 논의할 수 있게 합니다.
- **결과의 범위를 명확히 합니다.** 모델 평가 수치, 기능 검증 결과, 실제 운영 성능을 구분합니다.

---

<div align="center">

<b>Contact</b><br>
<a href="mailto:hodol0213@naver.com">hodol0213@naver.com</a> · <a href="https://github.com/hodol0213">GitHub</a> · <a href="https://clever-honey-b91.notion.site/bbe720a6f6cb82ec918d01d5fa3608eb">Portfolio</a>

</div>
