# 사전 준비

먼저 레포지토리를 복제합니다.

```bash
git clone https://github.com/Anna-Jeong-MS/AzureAIFoundryWorkshop.git
```

**Python 3.10 또는 그 이상 버전의 설치가 필요합니다.**

## VS Code 구성

1. 브라우저에서 [https://code.visualstudio.com/](https://code.visualstudio.com/)에 접속하여 VS Code를 설치합니다.
2. VS Code를 실행하고  상단 메뉴의 `File > Open Folder…` 를 클릭 후, 복제한 `AzureAIFoundryWorkshop` 폴더를 엽니다.

### VS Code 확장 설치

1. 왼쪽 메뉴에서 `Extensions` 을 클릭합니다.
2. `Python` 확장을 설치합니다.
    
    ![image.png](./images/image.png)
    
3. 같은 방법으로 `Jupyter`, `Polyglot Notebooks` 확장을 설치합니다.

### 로컬 환경 구성

1. VS Code 상단 메뉴의 Terminal > New Terminal을 클릭합니다.
2. 하단 터미널에서 아래 명령어를 사용하여 `uv`를 설치합니다.

    ```bash
    # Unix/Linux/macOS
    curl -LsSf https://astral.sh/uv/install.sh | sh

    # Windows (PowerShell)   
    powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
    ```

3. venv 환경을 만들고 활성화합니다.

    ```bash
    uv venv
    source .venv/bin/activate  # Windows: .venv\Scripts\activate
    ```

4. 실습을 위해서 아래 패키지들을 설치합니다.

    ```bash
    # Install core Azure AI SDKs and Jupyter requirements
    uv pip install azure-identity azure-ai-projects azure-ai-inference[opentelemetry] azure-search-documents azure-ai-evaluation azure-monitor-opentelemetry

    # Install Jupyter requirements
    uv pip install ipykernel jupyterlab notebook

    # Register the kernel with Jupyter
    python -m ipykernel install --user --name=.venv --display-name="Python (.venv)"
    ```