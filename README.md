# Azure AI Foundry Workshop

이 워크샵은 **Azure AI Foundry**를 활용하여 실제 기업 환경에서 생성형 AI 애플리케이션을 어떻게 설계·구현·운영할 수 있는지를 엔드투엔드로 체험할 수 있도록 구성되었습니다.  

참가자는 단순히 모델을 호출하는 수준을 넘어,  
- 데이터를 연결하고 임베딩하여 검색 가능한 지식으로 만드는 과정,  
- 사용자 조건에 따라 작동하는 **에이전트 설계와 구현**,  
- 여러 에이전트를 연동하여 **멀티 에이전트 시나리오**를 구성하는 방법,  
- 그리고 운영 단계에서 필수적인 **모니터링·평가 체계**까지 직접 실습하게 됩니다.  

---

### 1. Azure AI Foundry 기본 구성
- Foundry **Hub** 및 **Project** 생성
- Azure OpenAI, AI Search, Storage Blob, Application Insights 등 리소스 연결
- **역할 기반 접근 제어(RBAC)** 및 네트워크 옵션 설정
- 실습을 위한 샘플 데이터 업로드

### 2. Playground 체험
- 모델 배포 (예: GPT-4o, embedding 모델)
- **Chat Playground**에서 파일 업로드, AI Search 인덱스 연결
- 하이브리드 검색 + 벡터 검색 실습
- 간단한 프롬프트 테스트를 통해 데이터 검색 품질 확인

### 3. 첫 번째 에이전트 구현 – 사용자 프로필 추출
- `user_card_credit_summary_sample.json` 임베딩 후 **CreditProfileAgent** 생성
- 조건(연령대, VIP 등급, 연체 여부 등)에 맞는 사용자 **페르소나 JSON** 추출
- 스키마 정의, 필드 검증, Playground 테스트

### 4. 멀티 에이전트 구현 – 펀드 추천
- `fund_products_for_embedding.json` 기반 **FundRecommendationAgent** 생성
- **Connected Agents** 기능으로 CreditProfileAgent와 연계
- 사용자 조건 → 펀드 속성 매핑 로직 설계
- 추천 결과를 "사용자 요약 → 추천 펀드 목록 → 추천 사유" 형식으로 반환

### 5. 모니터링 및 평가
- **Application Insights**와 연동하여 로그/메트릭 수집
- Foundry **Observability Dashboard**에서 성능·안정성 확인
- KQL 쿼리로 traces / exceptions / dependencies 분석
- **Evaluation 메뉴**에서 CSV/JSONL 데이터셋 기반 품질·안전성 평가 수행
- Groundedness, Relevance, ToolCallAccuracy 등 주요 지표 확인

---

## ⏱️ 권장 시간 배분 (총 3시간)

- Foundry 구성 & Playground 체험: **50분**  
- 첫 번째 에이전트 구현 (CreditProfileAgent): **40분**  
- **휴식: 10분** ☕  
- 멀티 에이전트 구현 (FundRecommendationAgent): **50분**  
- 모니터링 및 평가 실습: **30분**  

---

## ✅ 사전 준비
- Azure 구독 및 Resource Group Owner 권한  
- Azure OpenAI 서비스 사용 승인 (지원 리전)  
- Visual Studio Code + Azure Tools 확장 (선택)  
- 기본 Azure Portal 사용 경험  

---

이 과정을 통해 참가자는 **Azure AI Foundry에서의 데이터-에이전트-관찰성 파이프라인**을 엔드투엔드로 경험할 수 있습니다.