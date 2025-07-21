# Azure AI Search 구성

## Azure AI Search 생성

1. `AI Foundry`에서 생성한 프로젝트의 AI Foundry 리소스를 클릭합니다.
    
    ![image.png](./images/image.png)
    
2. `Resource group`을 기록해 둡니다.
3. 브라우저의 새 탭에서 [`Azure Portal`](https://portal.azure.com/)에 접속합니다.
4. 상단 메뉴 검색창에 `AI 검색`을 입력합니다.
5. `AI Foundry | AI Search` 화면에서 `+ 만들기` 버튼을 클릭합니다.
6. `구독`을 선택하고 기록한 `리소스 그룹`을 선택하고 아래와 같이 구성합니다.
    - 서비스 이름 : <alias>-ai-search
    - 위치 : (Asia Pacific) Korea Central
    - 가격 책정 계층은 표준으로 둡니다.
7. 나머지 설정은 그대로 두고 `검토 + 만들기` 버튼을 클릭하고 `만들기` 버튼을 클릭하여 리소스를 생성합니다.

## Azure AI Search 구성

1. [`Azure AI Foundry 포털`](https://ai.azure.com/)로 이동합니다.
2. 프로젝트 화면 왼쪽 메뉴 하단의 `Management center`를 클릭합니다.
3. 왼쪽 메뉴 `Resource`에서 `Connected resources`를 클릭하고 `+ New Connection` 버튼을 클릭합니다.
4. `Azure AI Search`를 선택합니다.
5. 리스트에서 생성한 `<alias>-ai-search`의 `Add Connection` 버튼을 클릭합니다.
    
    ![image.png](./images/image%201.png)
    
6. `Connected` 로 변경되면 `Close` 버튼을 클릭합니다.