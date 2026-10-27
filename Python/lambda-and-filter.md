# 람다와 `filter()`

작성일: 2026-10-27

```python
lambda 매개변수: 반환할_식
```

람다는 식 하나의 결과를 반환하는 이름 없는 함수다.
정렬 기준으로 사용하는 예제는 [`sorted()`, `.sort()`, `reversed()`](./sorted-sort-reversed.md)에 정리했다.

## 조건에 맞는 값 고르기

```python
numbers = [1, 2, 3, 4, 5, 6]

list(filter(lambda n: n % 2 == 0, numbers))
# [2, 4, 6]
```

`filter()`는 함수 결과가 참으로 취급되는 원소를 남긴다. 같은 작업을 컴프리헨션으로도 작성할 수 있다.

```python
[n for n in numbers if n % 2 == 0]
# [2, 4, 6]
```

## 참고 자료

- [Python 람다 표현식](https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions)
- [Python 내장 함수 `filter()`](https://docs.python.org/3/library/functions.html#filter)

[Python 학습 목록](./README.md)
