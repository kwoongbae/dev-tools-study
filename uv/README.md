### uv란

- rust로 개발된 python 패키지 및 프로젝트 관리 도구
- 기존의 pip 보다 훨씬 빠르며, 주로 macOS, Linux, Windows에서 지원함.



### uv 기반의 패키지 관리

#### 00. 맥북에서 가상환경 설치

```bash
brew install uv # with homebrew
```



#### 01. uv 프로젝트 초기화 및 가상환경 생성

```bash
uv init # un init을 하게되면 자동생성됨.
uv venv # .venv 가상환경 생성
```

- uv 초기화 시 생성되는 파일들: `pyproject.toml`, `.python-version`, `requirements-dev.txt`, `.myenv/`, `uv.lock`
  - `myenv/` 디렉토리는 가상환경이 생성되는 디렉토리로, 하위폴더로 `bin/`에는 실행 파일들, `lib`에는 설치된 패키지들, `include/`에는 C확장 모듈 헤더 파일들이 위치함.
  - `uv.lock`은 의존성의 정확한 버전을 잠그는 파일로, `uv lock` 명령으로 생성 및 업데이트 됨.



#### 02. 가상환경 실행

```bash
source .venv/bin/activate
```

- 이 때 같은 디렉토리에 `.envrc`파일을 생성 후 `source .myenv/bin/activate \\ dotenv`를 하면 편리하게 사용할 수 있음.



#### 03. 가상환경에 ipykernel 설치

```bash
uv add ipykernel # 
(uv pip install ipykernel)
uv sync # uv sync를 해주어야 현재 내 워크스페이스에서 사용할 수 있음.
```

- `uv add` 명령어와 `uv pip install`은 다음의 차이점이 있음.

  - | `uv add`                                                     | `uv pip install`                                             |
    | ------------------------------------------------------------ | ------------------------------------------------------------ |
    | - 프로젝트의 의존성을 체계적으로 관리할 때<br />- 개발 의존성과 프로덕션 의존성을 구분해야 할 때<br />- 의존성 버전을 명시적으로 관리해야 할 때<br />- 팀 프로젝트에서 의존성을 공유해야할 때 | - 일회성 패키지 설치가 필요할 때<br />- 임시로 패키지를 테스트할 때<br />- pip명령어와의 호환성이 필요할 때<br />- 의존성 목럭 관리가 필요 없을 때 |
    | 팀 프로젝트, 프로젝트 의존성 추가                            | 일회성 패키지 설치                                           |






---

### References

[1] https://devocean.sk.com/blog/techBoardDetail.do?ID=167420&boardType=techBlog

[2] https://devocean.sk.com/blog/techBoardDetail.do?ID=167420&boardType=techBlog
