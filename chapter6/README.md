# Chapter 6: RAG and Agents

## 개요

이 장에서는 Foundation Model의 두 가지 핵심 Context Construction 패턴인 **RAG(Retrieval-Augmented Generation)**과 **Agents**를 다룹니다. 두 패턴 모두 모델의 Context 한계를 극복하고 외부 정보를 활용해 더 정확하고 유용한 응답을 생성할 수 있게 합니다.

## 학습 목표

이 장을 학습한 후 다음을 이해할 수 있습니다:

1. **RAG 시스템 설계** - 검색과 생성을 결합한 아키텍처 이해
2. **검색 알고리즘** - Term-based와 Embedding-based 검색 비교
3. **Agent 패턴** - 환경, 도구, 계획의 구조적 이해
4. **Planning과 Reflection** - Agent의 자율적 의사결정 메커니즘
5. **Memory 시스템** - 정보 관리와 활용 전략

## 핵심 개념

### RAG (Retrieval-Augmented Generation)
- Context 한계 극복을 위한 외부 정보 검색 및 활용
- Two-step process: Retrieve → Generate
- 효율적 정보 활용으로 응답 품질 향상 및 비용 절감

### Agents
- 환경(Environment)과 도구(Tools)로 정의
- AI를 Planner로 활용한 자율적 작업 수행
- Multi-step 작업을 위한 계획과 실행

### Memory
- Internal Knowledge, Short-term Memory, Long-term Memory
- 세션 내/간 정보 관리
- 효율적 메모리 관리 전략

## 문서 구조

| 파일 | 내용 |
|------|------|
| [6.1-rag.md](./6.1-rag.md) | RAG 아키텍처, 검색 알고리즘, 최적화 기법 |
| [6.2-agents.md](./6.2-agents.md) | Agent 개요, 도구, 계획, 실패 모드 및 평가 |
| [6.3-memory.md](./6.3-memory.md) | Memory 메커니즘과 관리 전략 |

## RAG vs Agents 비교

| 측면 | RAG | Agents |
|------|-----|--------|
| **주요 목적** | 외부 지식 검색 및 활용 | 자율적 작업 수행 |
| **복잡도** | 상대적으로 단순 | 높은 복잡도 |
| **도구 사용** | Retriever만 사용 | 다양한 도구 조합 |
| **적용 분야** | Q&A, 문서 분석 | 업무 자동화, 의사결정 |
| **실패 위험** | 검색 품질 의존 | 계획/실행 실패 가능 |

## 주요 용어

- **RAG (Retrieval-Augmented Generation)**: 검색과 생성을 결합한 패턴
- **Vector Database**: 임베딩 벡터 저장 및 유사도 검색 시스템
- **ANN (Approximate Nearest Neighbor)**: 근사 최근접 이웃 알고리즘
- **Agent**: 환경과 상호작용하며 작업을 수행하는 자율 시스템
- **Tool/Function Calling**: Agent가 외부 도구를 호출하는 기능
- **Planning**: 작업을 단계별로 분해하고 계획하는 과정
- **Reflection**: 결과를 평가하고 개선하는 자기 점검 과정
- **ReAct**: Reasoning과 Acting을 교차 실행하는 프레임워크

## 실무 적용 가이드

### RAG 도입 시 고려사항
1. 데이터 특성에 맞는 검색 알고리즘 선택
2. Chunking 전략 최적화
3. Reranking으로 검색 정확도 향상
4. Query Rewriting으로 검색 품질 개선

### Agent 도입 시 고려사항
1. 명확한 도구 정의와 문서화
2. 단계별 검증 및 에러 처리
3. 비용과 지연시간 모니터링
4. 보안 및 권한 관리

## 참고 문헌

- Lewis et al. (2020) - RAG 원 논문
- Yao et al. (2022) - ReAct 프레임워크
- Shinn et al. (2023) - Reflexion
- Lu et al. (2023) - Chameleon
- Berkeley Function Calling Leaderboard
