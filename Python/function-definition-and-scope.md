# 함수의 구조와 스코프

작성일: 2026-10-27

```python
def greet(name: str, message: str = '안녕하세요') -> str:
    return f'{name}님, {message}'
```

- `name`, `message`: 매개변수
- `: str`: 매개변수 타입힌트
- `= '안녕하세요'`: 인수 생략 시 사용할 기본값
- `-> str`: 반환 타입힌트

타입힌트는 실행 중 자동 검사나 형변환을 수행하지 않는다.

```python
greet('민수')
greet('민수', '반가워요')
greet(message='반가워요', name='민수')
```

## 반환값과 스코프

- `print()`는 화면에 표시한다.
- `return`은 호출한 곳에 값을 돌려주고 함수를 끝낸다.
- 반환값 없이 끝나는 함수는 `None`을 반환한다.
- 함수 안에서 만든 지역 이름은 함수 밖에서 바로 사용할 수 없다.
- 인수로 받은 리스트가 자동으로 복사되는 것은 아니다.

## 참고 자료

- [Python 함수 정의](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [Python 타입힌트](https://docs.python.org/3/library/typing.html)

[Python 학습 목록](./README.md)
