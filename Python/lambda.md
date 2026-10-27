# 람다

작성일: 2026-10-27

```python
lambda 매개변수: 반환할_식
```

람다는 식 하나의 결과를 반환하는 이름 없는 함수다.
정렬 기준으로 사용하는 예제는 [정렬과 뒤집기](./sorting-and-reversing.md)에 정리했다.

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

## 여러 리스트에 함께 적용하기

```python
list1 = [1, 2, 3, 4, 5]
list2 = [6, 7, 8, 9, 10]

result = map(lambda a, b: a + b, list1, list2)
print(list(result))
# [7, 9, 11, 13, 15]
```

`map()`에 리스트를 여러 개 넘기면 같은 위치의 값을 하나씩 짝지어 함수에 전달한다.
람다의 매개변수 개수는 넘긴 리스트 개수와 같아야 한다. 다르면 `TypeError`가 발생한다.

`zip()`처럼 가장 짧은 리스트가 끝나면 멈춘다. 짝이 없는 값은 버려진다.

```python
list(map(lambda a, b: a + b, [1, 2, 3, 4, 5], [6, 7]))
# [7, 9]
```

같은 작업을 컴프리헨션과 `zip()`으로도 작성할 수 있다.

```python
[a + b for a, b in zip(list1, list2)]
# [7, 9, 11, 13, 15]
```

## 참고 자료

- [Python 람다 표현식](https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions)
- [Python 내장 함수 `filter()`](https://docs.python.org/3/library/functions.html#filter)
- [Python 내장 함수 `map()`](https://docs.python.org/3/library/functions.html#map)
- [이것이 취업을 위한 코딩 테스트다 with 파이썬 · 나동빈](https://github.com/ndb796/python-for-coding-test)

[Python 학습 목록](./README.md)
