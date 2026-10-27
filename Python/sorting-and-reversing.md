# 정렬과 뒤집기

작성일: 2026-10-27

| 표현 | 원본 변경 | 반환값 |
|---|---|---|
| `sorted(items)` | 없음 | 정렬된 새 리스트 |
| `items.sort()` | 있음 | `None` |
| `reversed(items)` | 없음 | 현재 순서를 반대로 순회하는 이터레이터 |
| `items.reverse()` | 있음 | `None` |

- `sorted()`와 `.sort()`의 기본값은 `key=None`, `reverse=False`.
- `key`는 비교 기준을 만드는 함수다.
- `reverse=True`는 내림차순 정렬이다.
- `key`, `reverse`는 이름을 붙여 전달한다.
- `reversed()`와 `.reverse()`는 정렬하지 않고 현재 순서만 뒤집는다.
- `items = items.sort()`라고 쓰면 `items`에 `None`이 들어간다.

## `.reverse()`도 `None`을 반환한다

```python
a = [3, 1, 2]
b = a.reverse()
print(a, b)
# [2, 1, 3] None
```

`.reverse()`는 정렬하지 않고 현재 순서만 뒤집는다. 내림차순 정렬은 `a.sort(reverse=True)`다.

## 정렬 기준 지정

```python
words = ['banana', 'kiwi', 'apple']

sorted(words, key=lambda word: len(word))
# ['kiwi', 'apple', 'banana']
```

길이만 기준으로 삼으면 `key=len`으로도 작성할 수 있다.

```python
people = [('민수', 31), ('지은', 25), ('현우', 28)]

sorted(people, key=lambda person: person[1])
# [('지은', 25), ('현우', 28), ('민수', 31)]
```

`key`에 전달한 함수는 각 원소에서 비교할 기준값을 반환한다.
`lambda`는 [람다](./lambda.md)에 정리했다.

## 참고 자료

- [Python 정렬 기법](https://docs.python.org/3/howto/sorting.html)
- [Python 내장 함수 `reversed()`](https://docs.python.org/3/library/functions.html#reversed)

[Python 학습 목록](./README.md)
