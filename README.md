# FAST API 강의를 위해 다음과 같이 버전을 통일하였음

## 1. Poetry 버전 통일
  - 강의 특성상 오류가 많이나서 프레임워크 등 환경설정을 동일하게 하고자 함
  - Poetry 요구 버전은 1.8.5 버전이며, 기존에 설치된 버전은 poetry --version으로 확인하기
  - 기존의 버전이 높은 경우 전체 삭제하고 다시 설치해야 한다.<br>
  <br>

### Poetry 전부 삭제하고 1.8.5버전으로 설치하기<br>
     1) Poetry가 설치된 모든경로 찾기 : find ~ -type f -name "poetry" 2>/dev/null 

     2) 위에서 표시된 경로 앞에 rm -rf "경로" 명령어로 기존설치 흔적 지우기

     3) 1.8.5버전 강제 재설치
        curl -sSL https://install.python-poetry.org | POETRY_HOME="$HOME/.poetry" POETRY_VERSION=1.8.5 python3 -
 
     4) PATH설정 : echo 'export PATH="$HOME/.poetry/bin:$PATH"' >> ~/.zshrc
                  source ~/.zshrc

     5) 설치 확인 : which poetry
                  poetry --version

     
### Poetry 1.8.5가 설치 되어 있는 경우 경로설정해주기<br>
     1) Poetry가 설치된 모든경로 찾기 : find ~ -type f -name "poetry" 2>/dev/null 
     
     2)경로가 /Users/사용자명/.poetry/bin/poetry 혹은 .local/bin에 위치한 경우 경로를 추가해주면 됨
      : echo 'export PATH="$HOME/.poetry/bin:$PATH"' >> ~/.zshrc
        source ~/.zshr
       (로컬에 있는 경우) echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
 
    3) 다시 설치경로 및 버전 확인  
      : which poetry
        poetry --version

    4) 다음과 같이 나오면 성공
      : /Users/사용자명/.poetry/bin/poetry
        혹은 /Users/사용자명/.local/bin/poetry
        Poetry (version 1.8.5)
 <br>

 ## 2. Black 설치하기
 
     1) 설치 명령어: poetry add --group=dev black==24.10.0

     2) Black 실행하기 : poetry run black .

     3) pyproject.toml(설치된 버전확인 가능)에 Black line length 추가해주기
     
       : [tool.black]
         line-length = 120
 


