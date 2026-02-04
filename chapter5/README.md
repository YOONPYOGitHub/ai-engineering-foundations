# Chapter 5: Prompt Engineering

## 📚 개요

이 챕터는 모델이 원하는 결과를 생성하도록 지시를 작성하는 **프롬프트 엔지니어링**의 기술을 다룹니다. 가장 쉽고 일반적인 모델 적응 기법이며, 파인튜닝 전에 먼저 시도해야 합니다.

> **핵심 메시지**: "프롬프트 엔지니어링은 인간-AI 커뮤니케이션입니다. 누구나 소통할 수 있지만, 모두가 효과적으로 소통하는 것은 아닙니다."

---

## 📖 목차

| 섹션 | 제목 | 핵심 내용 |
|------|------|----------|
| [5.1](5.1-introduction-to-prompting.md) | Introduction to Prompting | In-Context Learning, System/User Prompt, Context Length |
| [5.2](5.2-prompt-engineering-best-practices.md) | Prompt Engineering Best Practices | 명확한 지시, 충분한 컨텍스트, 태스크 분해, CoT |
| [5.3](5.3-defensive-prompt-engineering.md) | Defensive Prompt Engineering | Jailbreaking, Prompt Injection, 방어 전략 |

---

## 🎯 학습 목표

이 챕터를 완료하면 다음을 할 수 있습니다:

1. **프롬프트 구조 이해**: System/User Prompt, Chat Template의 역할을 이해한다
2. **효과적인 프롬프트 작성**: Best Practice를 적용하여 명확하고 효과적인 프롬프트를 작성한다
3. **In-Context Learning 활용**: Zero-shot, Few-shot 학습을 적절히 적용한다
4. **보안 위협 대응**: Prompt Attack의 유형을 이해하고 방어 전략을 구현한다

---

## 💡 핵심 인사이트

### 프롬프트의 구성요소
```
Prompt
├── Task Description (무엇을 할 것인가)
│   └── 역할, 출력 형식, 제약조건
├── Examples (어떻게 할 것인가)
│   └── Few-shot 예시들
└── Task (구체적 작업)
    └── 질문, 데이터, 컨텍스트
```

### Context Length 발전
| 모델 | 연도 | Context Length |
|------|------|----------------|
| GPT-2 | 2019 | 1K |
| GPT-3 | 2020 | 4K |
| GPT-4 | 2023 | 128K |
| Gemini 1.5 Pro | 2024 | 2M |

> 5년 만에 **2,000배** 증가!

### Prompt Attack 유형
| 공격 유형 | 설명 | 위험도 |
|----------|------|--------|
| **Prompt Extraction** | 시스템 프롬프트 추출 | 중간 |
| **Jailbreaking** | 안전 기능 우회 | 높음 |
| **Prompt Injection** | 악성 지시 삽입 | 높음 |
| **Indirect Injection** | 도구를 통한 간접 공격 | 매우 높음 |
| **Data Extraction** | 학습 데이터 추출 | 높음 |

---

## 🔗 연관 챕터

- **Chapter 2**: Sampling - 모델의 확률적 특성 이해
- **Chapter 4**: Evaluation - 프롬프트 성능 평가
- **Chapter 6**: RAG and Agents - 컨텍스트 구성 기법
- **Chapter 7**: Finetuning - 프롬프트 이후의 모델 적응

---

## ❓ 토론 질문

1. **자동화 vs 수동**: AI가 프롬프트를 작성하도록 하는 것과 수동으로 작성하는 것, 언제 어떤 접근법을 선택해야 할까요?

2. **보안 트레이드오프**: 과도하게 방어적인 시스템은 사용자 경험을 저해합니다. 보안과 사용성 사이에서 어떻게 균형을 잡을 수 있을까요?

3. **프롬프트의 미래**: 모델이 더 강력해지면 프롬프트 엔지니어링은 사라질까요, 아니면 더 중요해질까요?

4. **Indirect Prompt Injection**: RAG 시스템이나 Agent에서 간접 주입 공격을 어떻게 방어할 수 있을까요?

---

## 📚 참고 자료

- OpenAI Prompt Engineering Guide
- Anthropic's Claude Prompt Library
- "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models" (Wei et al., 2022)
- "The Instruction Hierarchy" (Wallace et al., OpenAI 2024)
- "Not What You've Signed Up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection" (Greshake et al., 2023)
