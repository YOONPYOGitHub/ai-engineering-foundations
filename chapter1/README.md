# Chapter 1: Introduction to Building AI Applications with Foundation Models

> **"Scale이 모든 것을 바꿨다"**  
> AI post-2020을 한 단어로 표현하면: **Scale**

**Pages**: 1-48

---

## 📖 챕터 개요

이 챕터는 Foundation Models의 등장과 AI Engineering이라는 새로운 엔지니어링 분야의 탄생을 다룹니다. 1950년대 Language Models부터 시작해 2022년 ChatGPT까지의 여정, 그리고 이로 인해 가능해진 수많은 애플리케이션들을 살펴봅니다.

**핵심 질문:**
- Foundation Models은 어떻게 탄생했는가?
- Self-supervision이 왜 혁명적인가?
- AI Engineering은 무엇이고 왜 지금 폭발적으로 성장하는가?
- Foundation Models로 무엇을 만들 수 있는가?

---

## 📚 소주제

### [1.1 The Rise of AI Engineering](./1.1-rise-of-ai-engineering.md)

**Language Models → LLMs → Foundation Models → AI Engineering**

**주요 내용:**

**1. Language Models의 역사**
- 1950s: 첫 Language Model 개념 (Claude Shannon)
- 통계적 언어 모델링
- N-gram 모델의 한계
- Neural Language Models (Word2Vec, RNN, LSTM)

**2. Self-Supervision의 혁명**

핵심 개념:
```
기존 Supervised Learning:
Input + Human Label → Model
문제: 레이블링 비용, 확장 불가능

Self-Supervision:
데이터 자체가 레이블 제공
"I love street food." 
→ 6개의 학습 샘플 (다음 단어 예측)
→ 레이블링 비용 제로
→ 인터넷의 모든 텍스트 활용 가능
```

왜 혁명적인가:
- **무한한 데이터**: 레이블된 데이터 수백만 개 vs 인터넷 텍스트 수조 토큰
- **비용 제로**: $1/레이블 × 1M = $1M vs $0 × ∞ = $0
- **범용 학습**: 감성 분석 데이터는 감성 분석만, 인터넷 텍스트는 모든 것
- **Transfer Learning**: Pre-training (범용) → Finetuning (전문)

**3. Transformer의 등장 (2017)**
- "Attention Is All You Need"
- Attention mechanism
- 병렬 처리 가능
- 긴 문맥 처리

**4. Scaling Laws**
```
GPT-1 (2018):   117M parameters
GPT-2 (2019):   1.5B (13배)
GPT-3 (2020):   175B (117배)
GPT-4 (2023):   1.7T 추정 (10,000배)

발견: 더 큰 모델 + 더 많은 데이터 + 더 많은 계산 
     = 더 나은 성능 (예측 가능하게)
```

**5. Emergent Abilities (창발적 능력)**

정의: 모델이 특정 크기를 넘으면 갑자기 나타나는 새로운 능력

예시:
- **Few-Shot Learning**: 예시 몇 개만 보고 새로운 태스크 수행
- **Chain-of-Thought**: 추론 과정을 단계별로 표현
- **Instruction Following**: 지시사항을 이해하고 따름

Phase Transitions:
```
모델 크기: 0 → 1B → 10B → 100B → 1T
성능:     ──────────────────┐
                          │ ← 급격한 점프!
                          │
          ────────────────
```

**6. Multimodal로의 확장**
```
Language Models (2020):
Input:  텍스트
Output: 텍스트

Foundation Models (2021~):
Input:  텍스트 + 이미지 + 오디오 + 비디오
Output: 텍스트 + 이미지 + 오디오 + 비디오
```

주요 모델:
- **CLIP** (OpenAI, 2021): 4억 (이미지, 텍스트) 쌍, Zero-shot classification
- **DALL-E**: 텍스트 → 이미지
- **Whisper**: 오디오 → 텍스트 (다국어)
- **Sora** (2024): 텍스트 → 60초 고품질 비디오

**7. Foundation Models의 정의**

Stanford HAI (2021):
> "대규모 데이터로 학습되어 다양한 downstream 태스크에 적응될 수 있는 모델"

핵심 특징:
- **Scale**: 수십억~수조 parameters
- **Generality**: 범용 능력, 다양한 도메인
- **Adaptability**: Prompt engineering, RAG, Finetuning

**8. AI Engineering의 탄생**

3가지 요인:
1. **General-purpose AI 능력**: 더 많은 애플리케이션 가능
2. **낮은 진입 장벽**: API 호출로 누구나 사용
3. **증가한 투자**: Goldman Sachs 추정 $200B (2025년 글로벌)

통계:
- ChatGPT: 2개월 만에 1억 사용자
- GitHub Copilot: 2년 만에 $100M ARR
- S&P 500의 33% 기업이 AI 언급 (2023 Q2)
- AI 언급 기업: 주가 평균 4.6% vs 2.4%

---

### [1.2 Foundation Model Use Cases](./1.2-foundation-model-use-cases.md)

**8가지 주요 use case와 실제 애플리케이션**

**1. Coding (가장 인기있는 use case)**

통계:
- 개발자의 92%가 AI 코딩 도구 사용 경험
- 생산성 55% 증가 보고
- GitHub Copilot: 2년 만에 $100M ARR

McKinsey 연구 결과:
- 문서화: 2배 생산성
- 코드 생성/리팩토링: 25-50% 향상
- 복잡한 태스크: 최소한의 개선
- Frontend > Backend (AI가 더 잘함)

주요 도구:
- **GitHub Copilot**: OpenAI Codex 기반, IDE 통합
- **Cursor**: VS Code fork + GPT-4, Codebase-wide 이해
- **ChatGPT/Claude**: 코드 리뷰, 디버깅, 알고리즘 설명

특화 도구:
- 데이터 추출: AgentGPT
- English → Code: DB-GPT, SQL Chat, PandasAI
- 디자인 → 코드: screenshot-to-code
- 언어 변환: GPT-Migrate
- 문서화: Autodoc
- 테스트: PentestGPT

개발자 역할 변화:
```
이전: 코드 작성자
현재: 코드 설계자 + 검토자

AI가 초안 생성 → 개발자가 검토/수정
```

**2. Image and Video Production**

성공 사례:
- **Midjourney**: 1.5년 만에 $200M ARR
- Apple App Store Graphics & Design Top 10: 50%가 AI 앱

주요 모델:
- **DALL-E 3**: GPT-4 통합, 프롬프트 자동 개선
- **Midjourney**: 예술적 품질, Discord 기반
- **Stable Diffusion**: 오픈소스, 로컬 실행, 커스터마이징
- **Runway Gen-2**: 텍스트/이미지 → 4초 비디오
- **Sora**: 텍스트 → 60초 고품질 비디오

사용 사례:
- 프로필 사진 생성 (LinkedIn, TikTok)
- 광고/마케팅 소재
- 프리비주얼라이제이션
- 계절별 광고 변형 (가을→낙엽, 겨울→눈)

창작 민주화:
```
이전:
아이디어 → 디자이너 고용 → 수일~수주 → 비용 $수천~수만

현재:
아이디어 → AI 프롬프트 → 수초~수분 → 비용 $0~$수십
```

**3. Writing**

MIT 연구 (Noy and Zhang, 2023):
- 453명 전문가 대상 실험
- ChatGPT 사용 시:
  - 작성 시간 40% 감소
  - 품질 18% 향상
  - 능력 격차 감소 (덜 능숙한 사람에게 더 도움)
- 실험 후 실제 업무 사용: 2배 증가

사용 사례:
- **소비자**: 이메일 개선, 에세이, 인터랙티브 책
- **기업**: 성과 리포트, 영업 이메일, 광고 카피, 제품 설명
- **SEO**: 너무 잘해서 content farm 문제 발생

도구:
- **Grammarly**: 유창함, 일관성, 명확성 개선
- **Notion/Gmail/Google Docs**: 작문 도우미 통합
- **Jasper, Copy.ai**: 마케팅 콘텐츠 생성

부작용:
- 저품질 AI 생성 콘텐츠 범람
- 한 웹사이트가 하루 1,200개 기사 생성
- NewsGuard: 400개 광고가 AI 생성 사이트에 노출

**4. Education**

활용 방법:
- 교재 요약
- 개인화된 강의 계획
- 포맷 맞춤 (청각 학습자 → 읽어주기)
- 시각화 맞춤 (동물 선호 학생 → 동물 중심 예시)
- 수식 → 코드 변환

언어 학습:
- AI와 롤플레이 연습
- Duolingo: Lesson personalization에 가장 효과적
- 실시간 피드백, 무한한 인내심

혁명적 변화:
```
이전: 일괄 교육 (모든 학생에게 동일)
현재: 개인화 교육 (각 학생에게 맞춤)

광고는 개인화되는데 교육은 왜 아닌가?
→ AI가 이제 가능하게 함
```

현실:
- ChatGPT 다운 → Discord 서버에 학생들 불평
- 뉴욕/LA 교육청: ChatGPT 금지 → 몇 달 후 해제

**5. Conversational Bots**

ChatGPT 현상:
- 2개월 만에 1억 사용자
- (비교: Instagram 2.5년, TikTok 9개월)
- 2024년: 주간 활성 사용자 1억+

왜 성공했나:
- 자연스러운 대화
- 광범위한 지식
- 쉬운 사용 (채팅만)
- 무료 접근
- 다양한 활용

주요 모델:
- **ChatGPT**: 범용성, GPT-4, 플러그인
- **Claude**: 긴 컨텍스트 (200K 토큰), 안전성
- **Gemini**: Google 서비스 통합, 실시간 정보
- **Microsoft Copilot**: Windows/Office 통합

기업 활용:
- **고객 서비스**: 24/7, 즉시 응답, 다국어, 확장 가능
- **내부 지식**: "휴가 신청 어떻게?" → 즉시 답변
- **영업/마케팅**: 리드 검증, 제품 추천

새로운 인터페이스:
```
GUI (기존):
버튼 클릭, 메뉴 탐색, 학습 필요

CUI (미래):
자연어로 요청, AI가 실행, 학습 불필요

예: "다음 주 금요일 서울→제주 아침 비행기 예약"
→ AI가 모든 단계 처리
```

**6. Information Aggregation**

문제:
```
정보 과부하:
- 하루 생성 데이터: 2.5 exabytes
- 논문: 매일 수천 편
- 뉴스: 24/7
→ "뭘 읽어야 하지?"
```

해결: **Perplexity AI**
```
질문: "2024년 AI 산업 트렌드는?"

→ 여러 소스 검색
→ 통합 답변 + 출처 명시
→ 시간 절약 85-90%
```

연구 보조:
- **Elicit**: 논문 검색, 요약, 비교표
- **Semantic Scholar**: AI 기반 논문 검색
- **Consensus**: 과학적 컨센서스 ("커피가 건강에 좋은가?")

뉴스 통합:
- 같은 사건, 100개 언론사, 100가지 관점
- AI가 여러 소스 분석 → 균형잡힌 요약
- 편향성 분석, 팩트 체크

개인화 큐레이션:
- **Feedly + AI**: 중요도 판단, 관심사 학습
- 사용자 행동 관찰 → 맞춤 추천

**7. Data Organization**

문제:
```
개인:
- 이메일 수천 통
- 파일 수백~수천 개
- 사진 수만 장

결과: "그 파일 어디 있더라?" → 30분 소비
```

해결: AI 기반 정리

**Notion AI**:
- 자동 요약: 긴 회의 노트 → 핵심 3-5개
- 액션 아이템 추출: 회의록 → To-do 리스트
- 자동 태그/분류
- 자연어 검색: "지난 달 마케팅 미팅 예산 논의"

**Microsoft 365 Copilot**:
- Outlook: 이메일 요약, 회의 준비, 답장 초안
- Word: 문서 작성, 편집 제안
- Excel: 데이터 분석, 차트 생성
- Teams: 회의 요약, 액션 아이템

**이메일 관리**:
```
문제:
- 평균 직장인: 하루 121통 수신
- 28% 읽지 않음

해결:
- SaneBox: AI가 중요도 판단, 자동 분류
- Superhuman: AI triage, Split Inbox
```

임팩트:
- 정보 찾기: 하루 1-2시간 → 15-30분
- 주당 5-10시간 절약
- "어디 있더라?" 스트레스 감소

**8. Workflow Automation**

진화:
```
전통적 자동화 (Zapier):
"If this, then that"
- 단순 규칙
- 컨텍스트 이해 X

AI 자동화:
- 컨텍스트 이해
- 스마트한 결정
- 복잡한 워크플로우
```

예시: 고객 지원 자동화
```
이메일 수신
    ↓
AI 내용 분석
    ↓
├─ 간단 → AI 자동 답장
├─ 복잡 → 티켓 + 담당자 배정
└─ 긴급 → 즉시 알림 + 에스컬레이션

결과:
- 응답 시간 80% 감소
- 만족도 증가
- 직원은 복잡한 문제에 집중
```

주요 도구:
- **Zapier + AI**: 자동화 제안, 데이터 변환
- **Make**: 시각적 워크플로우, GPT 통합
- **n8n**: 오픈소스, self-hosted

AI Agent의 등장:
```
전통적 자동화: 미리 정의된 규칙, 순차적
AI Agent: 목표 기반, 동적 의사결정, 자율적

예: "경쟁사 분석 리포트 만들기"
→ AI가 스스로 태스크 분해하고 실행
```

임팩트:
- 생산성 증가: 반복 작업 자동화
- 비용 절감: 월 40시간 × $50 = $2,000 → $250
- 에러 감소: 일관된 품질
- 24/7 운영: 글로벌 대응

---

**산업별 직업 노출도** (Eloundou et al., 2023)

100% 노출 (AI가 작업 시간 50%+ 단축):
- 수학자
- 세무사
- 금융 분석가
- 작가
- 웹 디자이너

0% 노출:
- 요리사
- 석공
- 운동선수

주요 발견:
- 창의적/지식 기반 직업이 더 노출됨
- 물리적 작업은 덜 노출됨
- 노출 ≠ 대체, 업무 방식 변화

---

### 1.3 Planning AI Applications
*(실제 PDF에서 이 부분은 간략하게 다뤄졌으므로, 다음에 더 자세히 다룰 예정)*

**주요 내용:**
- Use Case Evaluation
- Setting Expectations
- Milestone Planning
- Maintenance

---

### 1.4 The AI Engineering Stack

**Three Layers:**
```
Application Layer (사용자 인터페이스)
    ↓
AI/ML Layer (Foundation Models)
    ↓
Infrastructure Layer (GPU, Cloud)
```

**AI Engineering vs ML Engineering**

| 측면 | ML Engineering | AI Engineering |
|------|---------------|---------------|
| **주요 작업** | 모델 개발/학습 | 모델 활용/적응 |
| **워크플로우** | 데이터 수집 → 레이블링 → 학습 → 평가 | 모델 선택 → 프롬프트 → 평가 → 최적화 |
| **데이터** | 레이블된 데이터 수집 | 프롬프트, 컨텍스트 구성 |
| **스킬** | 수학, 통계, 알고리즘, 모델 아키텍처 | 프롬프트 엔지니어링, 평가, API 통합 |
| **시간** | 개월 (데이터 수집+학습) | 일/주 (프로토타입 빠름) |
| **비용** | 학습 비용 (GPU, 인력) | 추론 비용 (API 호출) |
| **관심사** | 모델 아키텍처, Overfitting, 하이퍼파라미터 | 프롬프트 디자인, Hallucination, 비용 최적화 |

**AI Engineering vs Full-Stack Engineering**

공통점:
- 제품 감각
- 빠른 프로토타이핑
- API 통합
- 사용자 경험

차이점:
- AI Engineer는 + AI 모델 통합, 평가, 최적화
- Probabilistic 시스템 다루기
- Hallucination, 일관성 문제 해결

**AI Engineer의 핵심 활동:**
1. **Model Selection**: GPT-4 vs Claude vs Llama?
2. **Prompt Engineering**: 명확한 지시, few-shot, chain-of-thought
3. **Context Construction**: RAG, 데이터베이스, 도구/API
4. **Evaluation**: 정확도, hallucination, 비용, 사용자 만족도
5. **Optimization**: Caching, quantization, prompt optimization

---

## 🎯 핵심 요약

### The Rise of AI Engineering: 3가지 혁명

**1. Self-Supervision**
```
혁명 전: 레이블 → 비용 → 확장 불가능
혁명 후: 무료 데이터 → 무한 확장 → LLMs
```

**2. Scale**
```
GPT-1 (117M) → GPT-4 (1.7T): 14,500배
Emergent Abilities: 임계점 넘으면 새 능력
```

**3. Accessibility**
```
이전: 모델 만들기 (개월, $수백만)
현재: API 사용 (즉시, $수십)
→ AI Engineering 폭발
```

### Foundation Model Use Cases: 공통 패턴

**1. 민주화**
```
전문가만 → 누구나
- 코딩: 프로그래머 → 누구나 (AI 도움)
- 디자인: 디자이너 → 누구나 (AI 생성)
- 작문: 작가 → 누구나 (AI 보조)
```

**2. 역할 변화**
```
실행자 → 검토자/큐레이터
AI가 초안 생성 → 인간이 선택/수정
```

**3. 속도**
```
대부분 작업: 80-90% 시간 단축
- 코딩: 25-100%
- 작문: 40%
- 정보 찾기: 85-90%
```

**4. 접근성**
```
- API 호출만으로 강력한 AI
- 낮은 비용
- 낮은 기술 장벽
→ 작은 팀도 가능
```

### AI Engineering Stack: 핵심 전환

**Build → Integrate**
```
이전: 모델 만들기
현재: 모델 활용하기
```

**Code → Prompt**
```
이전: 코드로 로직 작성
현재: 자연어로 지시
```

**Train → Adapt**
```
이전: 처음부터 학습
현재: 기존 모델 적응
```

**Accuracy → Evaluation**
```
이전: 정확도 측정
현재: 다차원 평가 (정확도, hallucination, 비용, UX)
```

---

## 📊 주요 통계 & 타임라인

**채택 속도 (기록적)**
```
ChatGPT:        2개월 → 1억 사용자
GitHub Copilot: 2년 → $100M ARR
Midjourney:     1.5년 → $200M ARR
```

**투자 규모**
```
2025년 예상:
- 미국: $100B
- 글로벌: $200B
(참고: 미국 전체 공교육 예산 $900B의 1/9)
```

**기업 채택**
```
S&P 500:
- 2022 Q2: 11% AI 언급
- 2023 Q2: 33% AI 언급 (3배)

AI 언급 기업 주가: +4.6% vs +2.4%
```

**GitHub Stars (2024)**
```
AI Engineering 도구들:
- AutoGPT, Stable Diffusion: Bitcoin 초과
- LangChain, Ollama: React/Vue 추격 중
→ 가장 빠르게 성장하는 도구들
```

**Timeline**
```
1950s:  첫 Language Model (Claude Shannon)
2013:   Word2Vec
2017:   Transformer ("Attention Is All You Need")
2018:   BERT, GPT-1 (117M)
2019:   GPT-2 (1.5B)
2020:   GPT-3 (175B), Few-shot learning
2021:   CLIP, "Foundation Models" 용어
2022:   ChatGPT, Stable Diffusion
        → AI Engineering 폭발
2023:   GPT-4, Claude, Gemini
        Sora, 다양한 도구들
2024:   AI Engineer = 가장 빠르게 성장하는 직군
```

---

## 💬 토론 질문

### 기술적 질문

1. **Self-Supervision의 한계**
   - 모든 도메인에 적용 가능한가?
   - 여전히 Supervision이 필요한 영역은?

2. **Scaling Laws**
   - 계속 키우면 계속 좋아질까?
   - 한계는 어디인가? (데이터, 전력, 비용)

3. **Emergent Abilities**
   - 정말 "창발"인가, 측정의 문제인가?
   - 다음에 나타날 능력은?

### 전략적 질문

1. **Build vs Buy**
   - 직접 모델 만들기 vs API 사용
   - 의사결정 기준은? (규모, 예산, 도메인)

2. **Use Case 선택**
   - 우리 조직에 가장 적합한 use case는?
   - 우선순위 기준: ROI, 리스크, 실행 가능성

3. **투자 타이밍**
   - 지금 투자? 기다리기? (모델이 계속 좋아지는데)
   - First-mover advantage vs Wait-and-see

### 윤리적 질문

1. **일자리 영향**
   - AI가 어떤 직업을 대체할까?
   - 새로운 역할/직업은?
   - 재교육 방안은?

2. **데이터 권리**
   - 학습 데이터의 저작권은?
   - AI 생성물의 소유권은?
   - 예술가/작가 보호는?

3. **AI 접근성**
   - 대기업만 Foundation Model 만들면?
   - 기술 격차 해결 방안은?
   - 오픈소스의 역할은?

4. **콘텐츠 품질**
   - AI 생성 콘텐츠 범람 문제
   - 1,200개/일 기사 생성 사이트
   - 인터넷의 미래는?

---

## 📚 실습 아이디어

### 초급: 체험하기

1. **8가지 Use Case 탐색**
   - Coding, Image, Writing, Education, Bots, Info, Data, Workflow
   - 각 카테고리에서 1개씩 직접 사용
   - 장단점, 한계 정리

2. **모델 비교**
   - 같은 질문/태스크를 3개 모델로 테스트
   - ChatGPT vs Claude vs Gemini
   - 차이점 분석 (스타일, 정확도, 속도)

3. **생산성 측정**
   - 자신의 작업 1개 선택
   - AI 사용 전/후 시간 측정
   - 품질 차이 평가

### 중급: 분석하기

1. **Use Case 평가**
   - 우리 팀/조직에 적합한 TOP 3 선정
   - 평가 기준: 실행 가능성, ROI, 리스크, 시간
   - 각각의 구현 계획 스케치

2. **직업 노출도 분석**
   - 자신의 업무 태스크 리스트업
   - 각 태스크의 AI 노출도 추정
   - 앞으로의 역할 변화 예측

3. **Timeline 확장**
   - 2017-2024 AI 발전 타임라인 작성
   - 각 마일스톤의 영향력 분석
   - 2025-2030 예측

### 고급: 전략 수립

1. **AI 도입 로드맵**
   - 조직의 AI 전략 문서화
   - 단계별 계획:
     - 3개월: Quick wins
     - 6개월: Foundational capabilities
     - 1년: Transformative applications
   - 예산, 인력, 리스크 관리

2. **ROI 계산**
   - 특정 use case 선택
   - 비용: API, 인프라, 인건비, 교육
   - 이익: 시간 절약, 품질 향상, 새 기회
   - Break-even 시점 계산

3. **경쟁 분석 & 기회 발견**
   - 업계 AI 활용 사례 조사 (최소 10개)
   - 경쟁사 vs 우리의 Gap 분석
   - 미개척 use case 발견
   - 차별화 전략 수립

---

## 🎓 핵심 교훈

### 이 챕터에서 배운 것

**1. Foundation Models의 탄생**
- Self-supervision이 가능하게 함
- Scale이 모든 것을 바꿈
- Multimodal로 확장

**2. AI Engineering의 등장**
- 강력한 능력 + 낮은 장벽 + 높은 투자
- 가장 빠르게 성장하는 분야
- 역할 변화: Build → Integrate

**3. 가능한 것들**
- 8가지 주요 use case
- 민주화, 속도, 접근성
- 하지만 한계도 있음 (hallucination, 비용, 윤리)

**4. 다음 단계**
- 모델이 어떻게 작동하는지 이해 필요
- 평가 방법론 필요
- 적응 기술들 (Prompt, RAG, Finetuning)

---

## 🔗 다음 챕터로

**이제 다음을 알게 되었습니다:**
- ✅ Foundation Models이 어떻게 탄생했는지
- ✅ 왜 지금 AI Engineering이 폭발적으로 성장하는지
- ✅ 어떤 애플리케이션들이 가능한지
- ✅ AI Engineer의 역할은 무엇인지

**다음 챕터에서는:**
- Foundation Models이 내부적으로 어떻게 작동하는지
- Training Data, Modeling, Post-Training, Sampling
- 왜 Hallucination이 발생하는지
- Probabilistic Nature가 무엇을 의미하는지

**→ [Chapter 2: Understanding Foundation Models](../chapter2/README.md)**

---

[← 메인으로 돌아가기](../README.md)
