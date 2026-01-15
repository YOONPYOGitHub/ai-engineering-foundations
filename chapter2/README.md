# Chapter 2: Understanding Foundation Models

> **AI Engineering 책의 Chapter 2 스터디 가이드**  
> 페이지: 49-111 (총 63페이지)

---

## 📚 개요

Foundation Model을 이해하기 위해서는 세 가지 주요 설계 결정을 알아야 합니다:

1. **Training Data**: 모델이 무엇을 학습하는가
2. **Model Architecture & Size**: 모델이 어떻게 구성되고 얼마나 큰가
3. **Post-Training**: 모델이 인간의 선호도에 어떻게 정렬되는가

이 챕터는 또한 종종 간과되지만 매우 중요한 **Sampling** 개념도 다룹니다.

---

## 📖 소주제별 가이드

### [2.1 Training Data (훈련 데이터)](./2.1-training-data.md)
- 데이터 소스와 품질 문제
- 다국어 모델과 언어별 불균형
- 도메인 특화 모델의 필요성
- 핵심: "AI 모델은 학습한 데이터만큼만 좋다"

### [2.2 Modeling (모델링)](./2.2-modeling.md)
- Transformer 아키텍처 상세 분석
- Attention 메커니즘 (Query, Key, Value)
- 모델 크기와 스케일링 법칙
- 대안 아키텍처 (RWKV, Mamba, Jamba)
- 핵심: "Attention Is All You Need"

### [2.3 Post-Training (사후 학습)](./2.3-post-training.md)
- Supervised Finetuning (SFT)
- RLHF (Reinforcement Learning from Human Feedback)
- Reward Model 학습
- DPO와 비교
- 핵심: "모델을 유능하게 만든 후 안전하게 만들기"

### [2.4 Sampling (샘플링)](./2.4-sampling.md)
- Sampling 전략들 (Greedy, Temperature, Top-k, Top-p)
- Test Time Compute
- Constrained Decoding
- AI의 확률적 특성
- 핵심: "가장 과소평가된 개념"

---

## 🎯 학습 목표

이 챕터를 마치면 다음을 할 수 있어야 합니다:

- [ ] Foundation Model의 학습 데이터가 성능에 미치는 영향 설명
- [ ] Transformer 아키텍처와 Attention 메커니즘 이해
- [ ] Chinchilla Scaling Law를 사용한 최적 모델 크기 계산
- [ ] SFT와 RLHF의 차이점과 필요성 설명
- [ ] 다양한 샘플링 전략의 장단점 비교
- [ ] Test Time Compute의 개념과 실용성 평가
- [ ] AI의 확률적 특성이 프로덕션에 미치는 영향 이해

---

## 💡 핵심 인사이트

### Training Data
- 영어가 Common Crawl의 45.88%를 차지하여 다른 언어는 크게 불리
- 버마어는 영어보다 10배 많은 토큰 필요 → 10배 비용/레이턴시
- 7B 고품질 토큰 > 수조 개의 저품질 토큰

### Modeling
- Transformer의 핵심은 Attention: 모든 이전 토큰 참조 가능
- GPT-3 학습 비용: ~$4M (H100 256개, 236일)
- Chinchilla Law: 학습 토큰 수 ≈ 파라미터 수 × 20

### Post-Training
- Pre-training: 전체 컴퓨팅의 98%
- Post-training: 2%지만 사용성에 결정적
- InstructGPT: 13,000 (prompt, response) 쌍 ($130,000)
- RLHF 비교 데이터: $3.50/쌍

### Sampling
- Temperature 0 = 결정적, Temperature > 1 = 창의적
- Top-p (0.9) + Temperature (0.7) 권장 조합
- OpenAI o1: Test Time Compute로 박사급 추론
- AI는 본질적으로 확률적 (완벽한 일관성 불가)

---

## 🗣️ 스터디 토론 주제

### 1. 데이터 편향과 공정성
- Common Crawl의 품질 문제를 어떻게 해결할 수 있을까?
- 저자원 언어를 위한 현실적 해결책은?

### 2. 모델 아키텍처의 미래
- Transformer는 언제까지 지배할까?
- Mamba/SSM이 실제로 대체할 수 있을까?

### 3. 스케일링의 한계
- "더 크면 더 좋다"는 언제까지 유효할까?
- Last Mile Challenge를 극복할 방법은?

### 4. 인간 선호도 정렬
- 보편적 "인간 선호도"를 정의할 수 있을까?
- 안전성 vs 유용성의 최적 균형점은?

### 5. 샘플링과 프로덕션
- Hallucination을 완전히 없앨 수 있을까? 없애야 할까?
- Test Time Compute의 비용 대비 효과는?

### 6. 윤리와 책임
- AI의 확률적 특성을 사용자에게 어떻게 설명해야 할까?
- 학습 데이터의 저작권 문제는 어떻게 해결해야 할까?

---

## 📚 참고 자료

### 필수 논문
- **Transformer**: "Attention Is All You Need" (Vaswani et al., 2017)
- **Scaling Law**: "Training Compute-Optimal Large Language Models" (Chinchilla)
- **RLHF**: "InstructGPT" (OpenAI, 2022)
- **Mamba**: "Linear-Time Sequence Modeling" (Gu & Dao, 2023)

### 실습 도구
- Hugging Face Transformers
- OpenAI API Playground
- Anthropic Claude
- LangChain

### 벤치마크
- MMLU (Massive Multitask Language Understanding)
- HumanEval (코딩)
- TruthfulQA (사실성)
- BBH (Big-Bench Hard)

---

## 📊 주요 수치 요약

| 항목 | 수치 |
|------|------|
| Common Crawl 영어 비율 | 45.88% |
| GPT-3 학습 비용 | ~$4,000,000 |
| GPT-3 학습 FLOPs | 3.14 × 10²³ |
| InstructGPT SFT 데이터 | 13,000 쌍 |
| RLHF 비교 비용 | $3.50/쌍 |
| RLHF 라벨러 일치도 | ~73% |
| Llama 3 학습 토큰 | 15 Trillion |

---

## 🔑 용어 정리

| 용어 | 설명 |
|------|------|
| **Token** | 모델이 처리하는 텍스트의 기본 단위 |
| **Parameter** | 모델이 학습하는 가중치 값 |
| **FLOP** | Floating Point Operation |
| **Attention** | 입력의 다른 부분에 가중치 부여 메커니즘 |
| **Embedding** | 토큰을 수치 벡터로 변환 |
| **Prefill** | 입력 토큰을 병렬 처리하는 단계 |
| **Decode** | 출력 토큰을 순차 생성하는 단계 |
| **Hallucination** | 모델이 사실이 아닌 정보를 생성 |
| **Temperature** | 출력의 무작위성 조절 파라미터 |
| **RLHF** | Reinforcement Learning from Human Feedback |

---

**만든 날짜**: 2026-01-09  
**출처**: AI Engineering 책 Chapter 2 (페이지 49-111)  
**스터디 목적으로 작성됨**
