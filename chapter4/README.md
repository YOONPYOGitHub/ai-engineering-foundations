# Chapter 4: Evaluate AI Systems

## 📚 개요

이 챕터는 AI 시스템을 평가하는 방법론에 대해 다룹니다. 평가 기준 정의부터 모델 선택, 그리고 실제 평가 파이프라인 설계까지 전체 프로세스를 학습합니다.

> **핵심 메시지**: "신뢰할 수 있는 평가 파이프라인이 없는 것은 AI 도입의 가장 큰 장애물 중 하나입니다."

---

## 📖 목차

| 섹션 | 제목 | 핵심 내용 |
|------|------|----------|
| [4.1](4.1-evaluation-criteria.md) | Evaluation Criteria | Domain-Specific, Generation, Safety, Instruction-Following, Cost/Latency |
| [4.2](4.2-model-selection.md) | Model Selection | Build vs Buy, Public Benchmarks, Data Contamination |
| [4.3](4.3-evaluation-pipeline.md) | Design Your Evaluation Pipeline | 3단계 접근법, 평가 데이터, 파이프라인 평가 |

---

## 🎯 학습 목표

이 챕터를 완료하면 다음을 할 수 있습니다:

1. **평가 기준 정의**: 애플리케이션에 적합한 평가 기준을 설정할 수 있다
2. **모델 선택**: Build vs Buy 결정을 위한 7가지 축을 이해하고 적용할 수 있다
3. **벤치마크 해석**: Public Benchmark의 한계와 Data Contamination 문제를 이해한다
4. **파이프라인 설계**: 3단계 평가 파이프라인을 설계하고 구현할 수 있다

---

## 💡 핵심 인사이트

### Evaluation-Driven Development
```
평가 없이 개발 → 문제 발견 어려움 → 개선 방향 불명확
     ↓
평가 기반 개발 → 빠른 피드백 루프 → 체계적 개선
```

### Build vs Buy 의사결정 7축
| 축 | Build (Open Source) | Buy (API) |
|----|---------------------|-----------|
| Data Privacy | ✅ 완전 통제 | ⚠️ 외부 노출 |
| Data Lineage | ✅ 추적 가능 | ❌ 불투명 |
| Performance | 🔄 노력 필요 | ✅ 즉시 사용 |
| Functionality | ✅ 커스터마이징 | ⚠️ 제한적 |
| Control | ✅ 완전 통제 | ⚠️ 종속성 |
| Cost | 🔄 초기 비용 높음 | ✅ 시작 비용 낮음 |
| Speed to Market | ⚠️ 느림 | ✅ 빠름 |

### 평가 샘플 수 가이드라인 (95% 신뢰도)
| 감지할 차이 | 필요 샘플 수 |
|-------------|-------------|
| 30% | ~10 |
| 10% | ~100 |
| 3% | ~1,000 |
| 1% | ~10,000 |

---

## 🔗 연관 챕터

- **Chapter 3**: Evaluation Methodology - 평가 방법론의 기초
- **Chapter 5**: Prompt Engineering - 다음 단계: 모델 적응
- **Chapter 6**: RAG & Agentic Systems - Retrieval 및 Agent 시스템 평가
- **Chapter 8**: Dataset Engineering - 평가 데이터 생성

---

## ❓ 토론 질문

1. **Trade-off 분석**: 당신의 조직에서 Build vs Buy 결정 시 가장 중요한 축은 무엇인가요?

2. **벤치마크의 한계**: Public Benchmark 점수가 높은 모델이 실제 애플리케이션에서 기대에 못 미치는 경우를 경험한 적이 있나요?

3. **Data Contamination**: 벤치마크 데이터가 학습 데이터에 포함되는 문제를 어떻게 해결할 수 있을까요?

4. **비용 최적화**: 평가 파이프라인의 비용과 신뢰도 사이에서 어떻게 균형을 잡을 수 있을까요?

---

## 📚 참고 자료

- Eleuther AI's lm-evaluation-harness
- OpenAI Evals Framework
- HELM (Holistic Evaluation of Language Models)
- Chatbot Arena & LMSYS Leaderboard
- TruthfulQA, IFEval, MMLU 벤치마크
