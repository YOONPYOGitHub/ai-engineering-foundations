# AI Engineering Foundations

> AI 엔지니어링의 기초를 배우는 실습 중심 학습 자료

## 📖 소개

이 레포지토리는 **AI Engineering** 교재를 기반으로 한 학습 자료와 실습 노트북을 포함하고 있습니다. Foundation Models, LLM 애플리케이션 개발, Azure OpenAI API 활용 등의 내용을 다룹니다.

## 📂 프로젝트 구조

```
ai-engineering-foundations/
├── chapter1/               # Chapter 1: Rise of AI Engineering
│   ├── 1.1-rise-of-ai-engineering.md
│   ├── 1.2-foundation-model-use-cases.md
│   ├── 1.3-planning-ai-applications.md
│   ├── 1.4-ai-engineering-stack.md
│   └── README.md
│
├── chapter2/               # Chapter 2: Understanding Foundation Models
│   ├── 2.1-training-data.md
│   ├── 2.2-modeling.md
│   ├── 2.3-post-training.md
│   ├── 2.4-sampling.md
│   └── README.md
│
└── notebooks/              # 실습 노트북
    └── 2.4-sampling/       # Sampling 파라미터 실습
        ├── 2.4-sampling-practice.ipynb
        ├── pyproject.toml
        └── README.md
```

## 🚀 시작하기

### 필요 사항

- Python 3.10 이상
- Azure OpenAI API 계정 (실습용)
- [uv](https://github.com/astral-sh/uv) (Python 패키지 관리)

### 설치

1. 레포지토리 클론
```bash
git clone https://github.com/[your-username]/ai-engineering-foundations.git
cd ai-engineering-foundations
```

2. 가상환경 생성 및 패키지 설치
```bash
# notebooks 디렉토리에서
cd notebooks/2.4-sampling
uv sync
```

3. 환경 변수 설정
```bash
# .env 파일 생성
cp .env.example .env
# .env 파일에 Azure OpenAI 정보 입력
```

## 📚 학습 내용

### Chapter 1: Rise of AI Engineering
- AI 엔지니어링의 부상과 배경
- Foundation Model 활용 사례
- AI 애플리케이션 기획 방법
- AI 엔지니어링 스택

### Chapter 2: Understanding Foundation Models
- **Training Data**: 모델 학습 데이터의 중요성
- **Modeling**: 모델 아키텍처와 크기
- **Post-Training**: RLHF, DPO 등 정렬 기법
- **Sampling**: Temperature, Top-p, Penalty 등 생성 파라미터

## 🧪 실습 노트북

### 2.4 Sampling Practice
Azure OpenAI API를 사용한 샘플링 파라미터 실습:
- Temperature로 창의성 조절
- Top-p (Nucleus Sampling)
- Presence & Frequency Penalty
- Max Tokens, Seed, JSON Mode
- Best-of-N Sampling

**실행 방법:**
```bash
cd notebooks/2.4-sampling
jupyter notebook 2.4-sampling-practice.ipynb
```

## ⚙️ 환경 설정

### Azure OpenAI 설정
`.env` 파일에 다음 정보를 입력하세요:
```env
AZURE_OPENAI_ENDPOINT=your-endpoint
AZURE_OPENAI_API_KEY=your-api-key
AZURE_OPENAI_DEPLOYMENT_NAME=your-deployment-name
AZURE_OPENAI_API_VERSION=2024-02-15-preview
```

### 모델 호환성
일부 Azure OpenAI 모델 배포는 파라미터 조정을 제한할 수 있습니다. Temperature 파라미터를 지원하는 모델 사용을 권장합니다:
- `gpt-4`
- `gpt-4-turbo`
- `gpt-35-turbo`

## 📖 참고 자료

- [AI Engineering 교재](https://www.oreilly.com/library/view/ai-engineering/9781098166298/)
- [Azure OpenAI Documentation](https://learn.microsoft.com/azure/ai-services/openai/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)

## 🤝 기여

이슈나 개선 사항은 언제든 환영합니다!

## 📝 라이선스

이 프로젝트는 학습 목적으로 작성되었습니다.

---

**Note:** 이 레포지토리는 교재 "AI Engineering"의 학습 자료로, 원본 교재의 저작권은 해당 저자 및 출판사에 있습니다.

---

**만든 날짜**: 2026-01-09  
**출처**: AI Engineering 책 Chapter 2 (페이지 49-111)  
**스터디 목적으로 작성됨**
