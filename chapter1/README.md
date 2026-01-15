# Chapter 1: Introduction to Building AI Applications with Foundation Models

> **AI Engineering 책의 Chapter 1 스터디 가이드**  
> 페이지: 1-48 (총 48페이지)

> **"Scale이 모든 것을 바꿨다"**  
> AI post-2020을 한 단어로 표현하면: **Scale**

---

## 📚 개요

Foundation Models의 등장과 AI Engineering이라는 새로운 엔지니어링 분야의 탄생을 다룹니다. 1950년대 Language Models부터 시작해 2022년 ChatGPT까지의 여정, 그리고 이로 인해 가능해진 수많은 애플리케이션들을 살펴봅니다.

**핵심 질문:**
- Foundation Models은 어떻게 탄생했는가?
- Self-supervision이 왜 혁명적인가?
- AI Engineering은 무엇이고 왜 지금 폭발적으로 성장하는가?
- Foundation Models로 무엇을 만들 수 있는가?

---

## 📖 소주제별 가이드

### [1.1 The Rise of AI Engineering](./1.1-rise-of-ai-engineering.md)

**Language Models → LLMs → Foundation Models → AI Engineering**

**주요 내용:**## 📖 소주제별 가이드

### [1.1 The Rise of AI Engineering](./1.1-rise-of-ai-engineering.md)
- Language Models의 역사 (1950s~)
- Self-Supervision의 혁명과 중요성
- Transformer 아키텍처의 등장
- Scaling Laws와 Emergent Abilities
- Multimodal로의 확장
- Foundation Models의 정의
- AI Engineering 분야의 탄생
- 핵심: "Self-supervision이 모든 것을 바꿨다"

### [1.2 Foundation Model Use Cases](./1.2-foundation-model-use-cases.md)
- **Coding**: GitHub Copilot, Cursor (생산성 55% 증가)
- **Image/Video Production**: DALL-E, Midjourney, Sora
- **Writing**: Jasper, Copy.ai, Notion AI
- **Education**: Duolingo Max, Khan Academy
- **Conversational Bots**: ChatGPT, Claude, 고객 서비스
- **Information Aggregation**: Perplexity, You.com
- **Data Organization**: 문서 분류, 태깅 자동화
- **Workflow Automation**: Zapier, Make, 업무 프로세스
- 핵심: "개발자가 가장 많이 채택, 92%가 AI 코딩 도구 사용"

### [1.3 Planning AI Applications](./1.3-planning-ai-applications.md)
- Use Case 평가 프레임워크
- 기대치 설정 (Hallucination, 불확실성)
- Milestone 계획 (PoC → MVP → Production)
- 유지보수 전략
- 핵심: "AI는 확률적 → 완벽한 정확도 기대 금물"

### [1.4 The AI Engineering Stack](./1.4-ai-engineering-stack.md)
- **3 Layers**: Model Layer / Application Layer / Tooling & Infra Layer
- AI Engineering vs ML Engineering
- AI Engineering vs Full-Stack Engineering
- 필요한 스킬셋
- 핵심: "API 호출로 시작, 필요시 깊이 들어가기"

---

## 🎯 학습 목표

이 챕터를 마치면 다음을 할 수 있어야 합니다:

- [ ] Language Models에서 Foundation Models까지의 진화 과정 설명
- [ ] Self-supervision이 왜 혁명적인지 이해
- [ ] Scaling Laws와 Emergent Abilities의 개념 파악
- [ ] Foundation Models의 8가지 주요 use case 설명
- [ ] AI 애플리케이션 기획 시 고려사항 이해
- [ ] AI Engineering 스택의 3계층 구조 파악
- [ ] AI Engineering과 ML Engineering의 차이점 설명

---

## 💡 핵심 인사이트

### The Rise of AI Engineering

**Self-Supervision의 혁명:**
- 레이블링 비용: $1M (기존) → $0 (Self-supervision)
- 데이터 규모: 수백만 샘플 → 수조 토큰 (인터넷 전체)
- "I love street food." 한 문장 → 6개의 학습 샘플

**Scaling Laws:**
```
GPT-1:  117M parameters
GPT-2:  1.5B (13배)
GPT-3:  175B (117배)
GPT-4:  1.7T 추정 (10,000배)
```

**Emergent Abilities:**
- Few-Shot Learning: 예시 몇 개로 새 태스크 수행
- Chain-of-Thought: 단계별 추론 가능
- Instruction Following: 지시사항 이해

**AI Engineering 성장:**
- ChatGPT: 2개월 만에 1억 사용자
- GitHub Copilot: 2년 만에 $100M ARR
- Goldman Sachs: 2025년 $200B 글로벌 투자 예상

### Foundation Model Use Cases

**Coding (최고 인기):**
- 개발자 92%가 AI 코딩 도구 사용
- 생산성 55% 증가
- 문서화: 2배 생산성, 코드 생성: 25-50% 향상

**Image/Video Production:**
- DALL-E 3: 4억 이미지 생성/일
- Midjourney: 1,500만 사용자
- Sora: 텍스트 → 60초 고품질 비디오

**Business Impact:**
- 설문조사 자동화: 80시간 → 30분 (99.4% 감소)
- 고객 서비스: 14% 생산성 향상, 25% 문제 해결 증가

### Planning AI Applications

**Use Case 평가 기준:**
1. **명확한 정의**: 입력/출력/성공 기준
2. **평가 가능성**: 품질 측정 방법
3. **실패 시 영향**: 높음 → 신중, 낮음 → 빠른 실험
4. **데이터 가용성**: 평가/개선용 데이터 확보

**비용 고려:**
```
GPT-4 Turbo (8K output):
- 1,000 쿼리/일 × 30일 = 30,000 쿼리
- $150~$180/월
- 연간 $1,800~$2,160

10배 증가 시: $18,000~$21,600
```

### The AI Engineering Stack

**3 Layers:**
1. **Model Layer**: Pre-trained 모델 (GPT-4, Claude, Llama)
2. **Application Layer**: Prompt Eng, RAG, Agents, Finetuning
3. **Tooling & Infrastructure**: LangChain, Pinecone, Vector DB

**AI Engineering vs ML Engineering:**
- ML Eng: 모델 학습 (Pre-training)
- AI Eng: 모델 적용 (Post-deployment)
- ML Eng: GPU, 분산 학습 전문
- AI Eng: API, Prompt, 통합 전문

---

## 🗣️ 스터디 토론 주제

### 1. Self-Supervision의 한계
- Self-supervision으로 학습할 수 없는 것은?
- 인간의 피드백이 여전히 필요한 영역은?

### 2. Emergent Abilities의 예측 가능성
- 다음 "급격한 점프"는 언제 올까?
- 어떤 새로운 능력이 등장할 수 있을까?

### 3. Coding Use Case의 미래
- AI가 개발자를 대체할까, 보조할까?
- 개발자의 역할은 어떻게 변할까?

### 4. Hallucination 문제
- 언제는 허용 가능하고, 언제는 치명적인가?
- 완전히 제거할 수 있을까? 제거해야 할까?

### 5. AI Engineering의 진입 장벽
- "API 호출만으로 충분"은 언제까지 유효할까?
- 깊은 기술 이해가 필요한 시점은?

### 6. 비즈니스 임팩트 측정
- "생산성 55% 증가"를 어떻게 측정했을까?
- 실제 ROI 계산 시 고려사항은?

---

## 📚 참고 자료

### 필수 논문
- **Transformer**: "Attention Is All You Need" (Vaswani et al., 2017)
- **GPT-3**: "Language Models are Few-Shot Learners" (Brown et al., 2020)
- **CLIP**: "Learning Transferable Visual Models From Natural Language Supervision" (Radford et al., 2021)
- **Foundation Models**: Stanford HAI Report (2021)

### 주요 플랫폼 & 도구
- OpenAI API (GPT-4, DALL-E, Whisper)
- Anthropic Claude
- Google Gemini
- GitHub Copilot
- Cursor
- LangChain
- Hugging Face

### 벤치마크 & 리더보드
- LMSYS Chatbot Arena
- HumanEval (코딩)
- MMLU (일반 지식)
- Big-Bench

---

## 📊 주요 수치 요약

| 항목 | 수치 |
|------|------|
| ChatGPT 사용자 도달 | 2개월 → 1억 사용자 |
| GitHub Copilot ARR | 2년 → $100M |
| 개발자 AI 도구 사용률 | 92% |
| AI 코딩 생산성 증가 | 55% |
| GPT-4 예상 파라미터 | 1.7 Trillion |
| GPT-1 대비 증가 | 10,000배 |
| 2025 글로벌 AI 투자 예상 | $200B |
| DALL-E 일일 이미지 생성 | 4억 개 |
| Midjourney 사용자 | 1,500만 |

---

## 🔑 용어 정리

| 용어 | 설명 |
|------|------|
| **Self-Supervision** | 데이터 자체에서 레이블을 생성하는 학습 방법 |
| **Foundation Model** | 대규모 데이터로 학습되어 다양한 태스크에 적응 가능한 모델 |
| **Emergent Ability** | 모델 크기가 특정 임계점을 넘으면 나타나는 새로운 능력 |
| **Scaling Laws** | 모델 크기, 데이터, 계산이 증가할수록 성능이 예측 가능하게 향상 |
| **Few-Shot Learning** | 예시 몇 개만으로 새로운 태스크 수행 |
| **Chain-of-Thought** | 추론 과정을 단계별로 표현하는 능력 |
| **Multimodal** | 텍스트, 이미지, 오디오 등 여러 양식 처리 |
| **Hallucination** | AI가 사실이 아닌 정보를 그럴듯하게 생성 |
| **RAG** | Retrieval-Augmented Generation (검색 증강 생성) |
| **Prompt Engineering** | AI 출력을 개선하기 위한 입력 설계 |

---

**만든 날짜**: 2026-01-15  
**출처**: AI Engineering 책 Chapter 1 (페이지 1-48)  
**스터디 목적으로 작성됨**