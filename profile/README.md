# ✍️ gAIde (가이드)
> **"AI는 거들 뿐, 글쓰기의 주체는 바로 당신입니다."** <br>
> 획일화된 AI 문체가 아닌, 나만의 논리와 문체를 완성하도록 돕는 글쓰기 가이드 플랫폼

<br>

## 💡 프로젝트 소개 (Project Overview)
**gAIde**는 LLM이 글을 대신 써주는 것이 아니라, 사용자가 직접 쓴 글에 대해 **"논리적 비약 탐지"**, **"근거 보충 요구"** 등의 피드백만을 제공하는 서비스입니다.

생성형 AI의 발전으로 글쓰기가 편리해졌지만, 사람의 고유한 문체가 사라지고 사고력이 저하되는 부작용이 발생하고 있습니다. 우리는 AI를 '대필'이 아닌 '비서'로 정의하여, 사용자가 능동적인 주체로서 사고하고 글을 완성할 수 있도록 돕습니다.

### 🎯 핵심 목표
- **주객전도 방지:** AI에 의존적인 글쓰기에서 벗어나 사용자의 관점과 차별성 회복
- **논리적 사고 훈련:** 단순 교정이 아닌, 문맥적/논리적 피드백을 통해 스스로 글을 다듬도록 유도
- **진정한 AX (AI Experience):** 인간이 AI를 도구로 삼아 더 고차원적인 사고를 하도록 지원

<br>

## 🛠️ 주요 기능 (Key Features)
* **맞춤형 시스템 프롬프트 로드:** 자기소개서, 보고서 등 문서 목적(Category)에 따른 최적화된 가이드 제공
* **실시간 논리 피드백:** LangChain/DSpy 에이전트가 문장의 논리적 허점과 비약을 분석하여 사이드바에 시각화
* **에디터 통합 경험:** 글쓰기(Editor)와 피드백(Review)이 한 화면에서 자연스럽게 이루어지는 UI
* **데이터 무결성 보장:** Spring Security 및 트랜잭션 관리를 통한 안전한 데이터 처리

<br>

## 🏗️ 시스템 아키텍처 (System Architecture)
사용자가 작성한 텍스트는 아래와 같은 흐름으로 처리되어 피드백을 제공합니다.
<img width="1044" height="730" alt="image" src="https://github.com/user-attachments/assets/ee810312-4f02-4414-8e09-1447d8ead1f5" />

1.  **User Input:** React 에디터에서 텍스트 작성 및 카테고리 선택
2.  **Validataion (Spring Boot):** 1차 데이터 유효성 검증 및 로그 저장
3.  **Async Processing (FastAPI):** 데이터를 비동기로 AI 서버에 전송
4.  **AI Analysis (LLM/LangChain/DSpy):** 사실 나열 vs 주장 분석, 논리적 근거 판별
5.  **Feedback Loop:** 생성된 피드백이 Spring Boot를 거쳐 React 사이드바에 렌더링

<br>

## 📚 기술 스택 (Tech Stack)

| 분류 | 기술 (Techniques) | 선정 이유 |
| :-- | :-- | :-- |
| **Frontend** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=black) | 컴포넌트 단위 UI 관리 및 실시간 피드백 렌더링 최적화 |
| **Backend** | ![Spring Boot](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=Spring&logoColor=white) | Spring Security 인증/인가 및 트랜잭션 관리를 통한 데이터 무결성 보장 |
| **AI Server** | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=FastAPI&logoColor=white) | LangChain/DSpy 활용 및 비동기 처리를 통한 LLM 응답 지연 최소화 |
| **Database** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=PostgreSQL&logoColor=white) | 정형 데이터와 비정형 데이터(JSONB)의 동시 처리에 적합 |
| **Infra** | ![CloudType](https://img.shields.io/badge/CloudType-000000?style=flat-square&logo=googlecloud&logoColor=white) | CI/CD 파이프라인 구축 비용 최소화 및 해커톤 기간 내 빠른 배포 |

<br>

## 👥 팀원 소개 (Team 0xCODE)

| 이름 | 학과 | 역할 | 담당 파트 |
| :--: | :-- | :-- | :-- |
| **이재혁** | 컴퓨터공학전공 | ** 팀장 / PM** | 프로젝트 매니징 |
| **황윤수** | 컴퓨터AI학부 | **Backend** | 백엔드 개발 및 서버 아키텍처 설계 |
| **조수현** | 컴퓨터공학전공 | **Backend** | 백엔드 개발 및 API 구현 |
| **손승현** | 컴퓨터공학전공 | **Frontend** | 프론트엔드 개발 및 UI/UX 구현 |
| **최은서** | 컴퓨터AI학부 | **Frontend** | 프론트엔드 개발 |
| **우지웅** | 컴퓨터AI학부 | **AI Dev** | 모델 서버 개발 및 프롬프트 엔지니어링 |

<br>

## 🚀 시작하기 (Getting Started)

### Prerequisites
* Java 17+
* Python 3.10+
* Node.js 18+
