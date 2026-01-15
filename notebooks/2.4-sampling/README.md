# 2.4 Sampling 실습

Azure OpenAI를 사용한 Sampling 파라미터 실습 자료입니다.

## 📚 학습 목표

이 실습을 통해 다음을 배울 수 있습니다:

1. **Temperature**: 출력의 무작위성 제어
2. **Top-p (Nucleus Sampling)**: 확률 기반 토큰 선택
3. **Presence/Frequency Penalty**: 반복 제어
4. **Max Tokens**: 출력 길이 제한
5. **Seed**: 재현 가능한 출력
6. **JSON Mode**: 구조화된 출력
7. **Best-of-N**: 여러 답변 중 최고 선택

## 🚀 시작하기

### 1. 환경 설정

```bash
# uv가 설치되어 있지 않다면
curl -LsSf https://astral.sh/uv/install.sh | sh

# 프로젝트 디렉토리로 이동
cd notebooks/2.4-sampling

# 의존성 설치
uv sync

# Jupyter 커널 등록
uv run python -m ipykernel install --user --name=sampling-practice
```

### 2. 환경 변수 설정

```bash
# .env.example을 복사하여 .env 파일 생성
cp .env.example .env

# .env 파일을 열어서 실제 값으로 수정
# - AZURE_OPENAI_ENDPOINT: Azure Portal에서 확인
# - AZURE_OPENAI_API_KEY: Azure Portal에서 확인
# - AZURE_OPENAI_DEPLOYMENT_NAME: 배포한 모델 이름
```

**Azure OpenAI 설정 방법:**

1. [Azure Portal](https://portal.azure.com)에 접속
2. "Azure OpenAI" 리소스 생성
3. "Keys and Endpoint" 탭에서:
   - `Endpoint` → `AZURE_OPENAI_ENDPOINT`
   - `Key 1` → `AZURE_OPENAI_API_KEY`
4. "Model deployments"에서 GPT-5-mini 배포
   - Deployment name → `AZURE_OPENAI_DEPLOYMENT_NAME`

### 3. Jupyter Notebook 실행

```bash
# Jupyter Lab 시작
uv run jupyter lab

# 또는 Jupyter Notebook
uv run jupyter notebook
```

브라우저가 자동으로 열리면 `2.4-sampling-practice.ipynb` 파일을 엽니다.

**커널 선택**: `sampling-practice` 커널을 선택하세요.

## 📓 실습 내용

### Part 1: Temperature (15분)
- Temperature가 출력에 미치는 영향
- 0 (결정론적) vs 0.7 (균형) vs 1.5 (창의적)
- 실무 활용 가이드

### Part 2: Top-p Sampling (10분)
- Nucleus sampling 개념
- Top-p vs Temperature 비교
- 언제 무엇을 사용할까?

### Part 3: Penalty 파라미터 (10분)
- Presence penalty (주제 다양성)
- Frequency penalty (반복 감소)
- 실제 사용 사례

### Part 4: 기타 파라미터 (15분)
- Max tokens (길이 제어)
- Seed (재현성)
- JSON mode (구조화된 출력)

### Part 5: Best-of-N (10분)
- 여러 답변 생성
- 최고 답변 선택 전략
- 비용 vs 품질

### Part 6: 종합 실습 (20분)
- 실제 시나리오별 최적 설정
- 비용 최적화
- 실무 베스트 프랙티스

**총 소요 시간: 약 1.5시간**

## 📊 실습 결과 예시

실습을 완료하면 다음을 이해하게 됩니다:

```python
# 사실 기반 답변 (Temperature 낮게)
completion = client.chat.completions.create(
    model="gpt-5-mini",
    temperature=0,
    messages=[{"role": "user", "content": "프랑스의 수도는?"}]
)

# 창의적 글쓰기 (Temperature 높게)
completion = client.chat.completions.create(
    model="gpt-5-mini",
    temperature=1.2,
    messages=[{"role": "user", "content": "SF 소설 아이디어 3개"}]
)

# JSON 출력
completion = client.chat.completions.create(
    model="gpt-5-mini",
    response_format={"type": "json_object"},
    messages=[{
        "role": "user",
        "content": "다음 텍스트에서 JSON 추출: 홍길동, 30세, 서울"
    }]
)
```

## 🎯 학습 후 활용

이 실습 후에는:

- ✅ 프로젝트에 맞는 최적 파라미터 선택 가능
- ✅ 출력 품질과 비용 균형 조정
- ✅ 일관성 vs 창의성 제어
- ✅ 구조화된 출력 생성

## 📚 참고 자료

- [Azure OpenAI Service 문서](https://learn.microsoft.com/azure/ai-services/openai/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
- Book: AI Engineering, Chapter 2.4 Sampling

## 💡 문제 해결

### Azure OpenAI 연결 오류
```
Error: The API deployment for this resource does not exist.
```
→ `.env` 파일의 `AZURE_OPENAI_DEPLOYMENT_NAME`이 실제 배포 이름과 일치하는지 확인

### 인증 오류
```
Error: Unauthorized
```
→ API Key가 올바른지, Endpoint가 정확한지 확인

### 패키지 설치 오류
```bash
# uv 캐시 초기화
uv cache clean

# 다시 설치
uv sync
```

## 📝 피드백

실습 중 문제가 있거나 개선 사항이 있다면 이슈로 남겨주세요!

---

**Happy Learning! 🚀**
