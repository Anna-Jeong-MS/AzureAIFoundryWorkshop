# 인증 정보 구성

1. VS Code 터미널에서 아래 명령어를 실행합니다.
    
    ```bash
    cp .env.example .env
    ```
    
2. [`AI Foundry 포털`](https://ai.azure.com/)에 접속하여 생성한 프로젝트를 클릭한 뒤, 아래와 같이 `.env 파일`을 구성합니다.
    
    ![image.png](./images/image.png)
    
    ```bash
    ENDPOINT="https://<resource>.services.ai.azure.com/models"
    API_KEY=<api-key>
    ```
    
3. 왼쪽 메뉴에서 `Models + endpoint`를 클릭합니다.
4. 생성한 `LLM 모델`과 `임베딩 모델`을 `.env 파일`에 업데이트합니다.
    
    ```bash
    MODEL_NAME="gpt-4o"
    TEXT_EMBEDDING_MODEL="text-embedding-3-small"
    ```
    

### AI Search 구성 후

1. 왼쪽 메뉴에서 `Management center` 메뉴를 클릭합니다.
2. `Connected resources` 메뉴를 클릭합니다.
3. 생성한 `<alias>aisearch` 항목을 클릭합니다.
4. 아래와 같이 `.env 파일`을 업데이트 합니다.
    
    ![image.png](./images/image%201.png)
    
    ```bash
    SEARCH_INDEX_NAME="healthtips-index"
    SEARCH_ENDPOINT=<search-endpoint>
    SEARCH_API_KEY=<search-api-key>
    ```