# LLM System

<br>

## LLM System 용어 정리

| 용어                     | 설명                                                                 |
|--------------------------|--------------------------------------------------------------------|
| **Prompt Engineering**    | AI 모델이 적절한 출력을 생성하도록 입력(prompt)을 설계하는 기법.                |
| **AI**                    | 인공지능(AI)은 인간의 지능적인 행동을 모방하는 시스템을 의미하며, 학습 및 문제 해결 능력을 갖춘 기술. |
| **Model / Foundation Model** | 대규모 데이터로 사전 학습된 AI 모델로, 다양한 작업에 맞게 미세 조정(Fine-Tuning)이 가능한 기본 모델. |
| **Pre-training**          | 모델이 대규모 데이터셋으로 사전 학습하는 과정. 모델이 기본 패턴과 언어 구조를 학습함.            |
| **Fine-Tuning**           | 특정 작업에 맞게 사전 학습된 모델을 추가적인 데이터로 미세 조정하는 과정.                     |
| **Deploy**                | AI 모델을 실제 환경에 배포하여 서비스로 제공하는 과정.                                    |
| **API / "Serving" the model** | API를 통해 모델을 호출하고, 이를 실제 서비스에 통합하여 사용자에게 제공하는 과정.             |
| **Post/Pre-processing**   | 모델이 입력 데이터를 처리하기 전/후에 필요한 작업을 수행하는 과정.                          |
| **Embedding**             | 데이터를 벡터화하여 모델이 이해할 수 있는 형식으로 변환하는 작업.                             |
| **LLM Ops**               | LLM의 배포 및 운영과 관련된 모든 관리 과정.                              |

<br>

---

<br>

## LLM System Workflow

1. **사용자 질문 입력**
   - 사용자가 질문을 입력한다.

2. **Pre-processing**
   - 입력된 질문은 전처리 과정을 거친다.
   - 전처리 과정에서 데이터는 적절한 형식으로 변환되고, 필요시 보안 처리 및 임베딩(embedding)이 수행된다.

3. **Grounding Information**  
   - 전처리된 질문은 다양한 데이터 소스에서 관련 정보를 검색하여 "Grounding Information"을 수집한다.  
     Grounding Information은 LLM이 더 신뢰할 수 있고 구체적인 응답을 제공할 수 있도록 외부 데이터를 활용하는 과정이다.  
     LLM이 사전에 학습된 데이터뿐만 아니라 실시간 정보나 외부 참조 데이터를 사용하여 응답의 정확성을 높이는 역할을 한다.  
     - **ML Model Outputs**  
     - **Vector DB**  
     - **Web Search**

4. **Prompt Generation**
   - 수집된 "Grounding Information"을 기반으로 AI 모델에 전달할 프롬프트를 생성한다.

5. **LLM Model**
   - 생성된 프롬프트는 LLM에 전달되며, 모델은 이를 바탕으로 응답을 생성한다.

6. **LLM Response**
   - LLM 모델은 입력된 프롬프트에 맞는 응답을 생성하고, 해당 응답은 후속 처리 단계로 넘어간다.

7. **Post-processing**
   - 생성된 응답은 후처리 과정을 거친다.
     - **RAI (Responsible AI)**: 응답이 윤리적이고 책임감 있게 생성되었는지 검토한다.
     - **Relevance Check**: 응답이 사용자의 질문과 관련 있는지 확인한다.

8. **최종 응답 반환 (Response Delivery)**
   - 후처리가 완료된 응답이 사용자에게 전달된다.
