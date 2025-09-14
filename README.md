# Azure AI Foundry Workshop (2h)

본 워크샵은 **(1) Azure AI Foundry 구성**, **(2) 플레이그라운드 활용**에 **초점을 둡니다**.  
**(3) 챗봇 생성**, **(4) 평가·모니터링**은 추후 추가할 예정입니다.

---

## Prerequisites
- Azure 구독 권한(리소스 그룹 Owner 수준)
- Azure OpenAI 사용 승인 및 지원 리전

---

## Quick Start
1. 허브와 프로젝트를 생성합니다. *(Storage access: Identity-based 권장)*  
2. **Connections**에 Azure OpenAI, Azure AI Search, Storage(`workspaceblobstore`)를 등록합니다.  
3. RBAC을 최소 구성합니다.  
   - 사용자 → Storage: `Storage Blob Data Contributor` (+ 선택 `Storage Blob Data Delegator`)  
   - OpenAI(MI) → Search: `Search Service Contributor`, `Search Index Data Reader`  
   - OpenAI(MI) → Storage: `Storage Blob Data Contributor`  
   - Search(MI) → Storage: `Storage Blob Data Reader`  
4. 모델(예: GPT-4o)을 배포하고 **Chat Playground**를 엽니다.  
5. **Add data**로 파일/검색을 연동하고 샘플 프롬프트로 테스트합니다.

---

## 1) Azure AI Foundry 구성
- 허브를 생성하고 프로젝트를 추가합니다.  
- **Connections**에서 OpenAI / AI Search / Storage 연결 상태를 확인합니다.  
- 각 리소스의 **System-assigned Managed Identity**를 활성화하고 상기 RBAC을 적용합니다.  
- 네트워크 제한을 사용하는 경우 **신뢰할 수 있는 Microsoft 서비스 허용** 또는 **프라이빗 엔드포인트**를 구성합니다.

---

## 2) 플레이그라운드 활용
- **Deployments**에서 모델(gpt-4o 등)을 배포합니다.  
- **Chat Playground → Add data**에서 다음을 설정합니다.  
  - 데이터 원본: File upload(미리 보기) 또는 AI Search 인덱스  
  - 인증: **System-assigned managed identity**  
- 샘플 프롬프트 예시  
  - 1,000만 원 12개월 정기예금(단리) vs 월복리의 **기본/우대금리** 비교표를 제시하고 **기준일·출처**를 명시합니다.  
  - 50만 원×24개월 적금의 만기 수령액(우대 충족/미충족)을 계산하고 **중도해지 규정**을 요약합니다.

---

## 3) 챗봇 생성 *(추가 예정)*
- Playground 웹앱 배포, App Service MI 활성화, 웹앱 MI → Azure OpenAI `Cognitive Services OpenAI User` 역할 부여, (선택) Cosmos DB 연동을 포함할 예정입니다.

## 4) 평가·모니터링 *(추가 예정)*
- Playground **Evaluation**, 사용량/오류 모니터링 및 알림 구성을 포함할 예정입니다.

---

## Troubleshooting
- MI 검증 실패: 리소스 MI 활성화, RBAC 재확인, Search **API access control = Role-based/Both**로 설정합니다.  
- SAS + Key 비활성화 충돌: 데이터스토어를 **Identity 기반**으로 전환합니다.  
- On Your Data 리전 오류: **지원 리전**의 Azure OpenAI 리소스를 사용합니다.  
- 웹앱 401/403: 웹앱 MI에 `Cognitive Services OpenAI User` 역할을 부여합니다.