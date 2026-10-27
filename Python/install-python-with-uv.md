# Python 첫 설치와 uv

작성일: 2026-10-26

macOS 터미널 기준으로 uv 설치부터 Python 코드 실행까지 정리한다.
Python 버전은 3.14를 기준으로 정리했다.

## Python과 uv

- **Python**: Python 코드를 실행하는 언어 실행 환경이다.
- **uv**: Python 버전, 프로젝트별 가상 환경, 외부 패키지를 관리하는 도구다.
- **가상 환경**: 프로젝트마다 사용하는 Python과 패키지를 분리하는 공간이다.

uv를 사용하면 Python을 먼저 따로 설치하지 않아도 된다.

## 1. uv 설치

터미널에서 아래 명령을 실행한다. macOS와 Linux에서 사용할 수 있다.

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

설치 후 터미널을 새로 열고 설치 여부를 확인한다.
`uv`를 찾지 못하면 설치가 끝났을 때 안내된 PATH 설정을 적용한다.

```bash
uv --version
```

Windows 설치 방법은 [uv 공식 설치 문서](https://docs.astral.sh/uv/getting-started/installation/)를 참고한다.

## 2. Python 설치

```bash
uv python install 3.14
```

`python`이나 `python3` 명령은 기존에 설치된 다른 버전을 가리킬 수 있다.
프로젝트에서는 아래처럼 `uv run python`으로 실행할 버전을 확인한다.

## 3. 연습 프로젝트 만들기

`uv init`으로 연습용 프로젝트를 만든다. 학습 기록과 실행 환경은 별도 폴더로 구분한다.

```bash
uv init --python 3.14 python-practice
cd python-practice
uv run python --version
```

첫 `uv run` 실행 시 프로젝트의 가상 환경인 `.venv`가 준비된다.
`uv run`을 사용하면 가상 환경을 직접 활성화하지 않아도 된다.

## 4. 첫 코드 실행

`python-practice` 폴더의 `main.py`에 실행할 코드를 작성한다.

```python
print('Hello, Python!')
```

같은 폴더의 터미널에서 실행한다.

```bash
uv run python main.py
```

실행 결과:

```text
Hello, Python!
```

대화형 모드는 `uv run python`으로 시작하고, `exit()`으로 종료한다.

## 프로젝트에서 보게 되는 파일

| 파일 / 폴더 | 역할 |
| --- | --- |
| `pyproject.toml` | 프로젝트 정보, 필요한 Python 버전과 패키지 목록 |
| `.python-version` | 프로젝트에서 사용할 Python 버전 |
| `.venv/` | 프로젝트 전용 가상 환경. Git에 올리지 않는다. |
| `uv.lock` | 사용할 패키지의 구체적인 버전 등을 기록하는 잠금 파일 |

외부 패키지는 프로젝트 폴더에서 `uv add 패키지명`으로 추가한다.
지금 정리하는 기초 예제는 외부 패키지 없이 실행할 수 있다.

## 참고 자료

- [uv 설치](https://docs.astral.sh/uv/getting-started/installation/)
- [uv로 Python 설치 및 관리](https://docs.astral.sh/uv/guides/install-python/)
- [uv 프로젝트 사용법](https://docs.astral.sh/uv/guides/projects/)

[Python 학습 목록](./README.md)
