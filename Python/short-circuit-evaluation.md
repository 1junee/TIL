# 단축 평가

작성일: 2026-10-26

`and`와 `or`는 왼쪽부터 확인하고, 결과를 결정할 수 있으면 오른쪽 식을 평가하지 않는다.

| 식 | 동작 |
| --- | --- |
| `x and y` | `x`가 거짓이면 `x`를 반환하고, 그렇지 않으면 `y`를 평가해 반환한다. |
| `x or y` | `x`가 참이면 `x`를 반환하고, 그렇지 않으면 `y`를 평가해 반환한다. |

반환값은 항상 `True`나 `False`인 것이 아니라, 선택된 피연산자 자체다.

```python
divisor = 0
print(divisor != 0 and 10 / divisor > 1)  # False: 나눗셈을 실행하지 않는다.

print([] and "오른쪽 값")  # []: 피연산자 자체를 반환한다.
```

`False`, `None`, 숫자 `0`, 빈 문자열과 빈 컨테이너(`[]`, `()`, `{}`, `set()` 등)는 거짓으로 취급한다.
`or`로 기본값을 정하면 `0`이나 빈 문자열도 기본값으로 바뀐다.

`None`일 때만 기본값을 쓰려면 명시적으로 구분한다.

```python
value = 0
print(value or 10)                      # 10
print(10 if value is None else value)   # 0
```

## 참고 자료

- [Python 참/거짓 판정과 논리 연산](https://docs.python.org/3/library/stdtypes.html#truth-value-testing)

[Python 학습 목록](./README.md)
