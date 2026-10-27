# 입력과 출력

작성일: 2026-10-27

## `input()`은 문자열을 반환한다

```python
# 입력: 3 5
data = input().split()
print(data)
# ['3', '5']

print(data[0] + data[1])
# 35
```

`input()`은 입력을 항상 문자열로 받는다.
`split()`으로 나눠도 문자열 리스트이므로, `+`는 덧셈이 아니라 문자열 이어 붙이기가 된다.

## `map()`으로 정수 변환

```python
# 입력: 3 5
numbers = map(int, input().split())
print(numbers)
# <map object at 0x...>
```

`map(함수, 대상)`은 리스트가 아니라 map 객체를 반환한다.
값을 꺼낼 때 하나씩 함수를 적용하는 지연 평가 방식이며, 한 번 끝까지 꺼내면 비어 있다.

| 쓰는 곳 | 코드 |
|---|---|
| 값 개수가 정해져 있을 때 | `a, b = map(int, input().split())` |
| 값 개수가 정해져 있지 않을 때 | `numbers = list(map(int, input().split()))` |

언패킹은 튜플이나 리스트가 아니어도, 값을 하나씩 꺼낼 수 있는 대상이면 쓸 수 있다.
값의 개수와 변수의 개수가 다르면 `ValueError`가 발생한다.

## 빠르게 입력 받기: `sys.stdin.readline()`

```python
import sys

# 문자열 입력 받기
data = sys.stdin.readline().rstrip()

# 정수 입력 받기
a, b = map(int, sys.stdin.readline().split())
```

- 입력 줄이 많을 때 `input()`보다 빠르다.
- `readline()`은 끝의 줄바꿈 문자 `\n`까지 가져온다. `hello`를 입력하면 `'hello\n'`이며 길이는 6이다.
- 문자열은 `.rstrip()`으로 줄바꿈을 지운다. `split()`은 줄바꿈도 공백 문자로 처리하므로 숫자 입력에는 필요 없다.

## 출력: `print()`의 `sep`, `end`

| 인자 | 의미 | 기본값 |
|---|---|---|
| `sep` | 값 사이에 넣을 문자열 | `' '` |
| `end` | 마지막에 붙일 문자열 | `'\n'` |

```python
print(1, 2, 3, sep='-', end='!')
print('끝')
# 1-2-3!끝

for i in range(3):
    print(i, end=' ')
# 0 1 2
```

`end`를 바꾸면 줄바꿈이 일어나지 않으므로 다음 출력이 같은 줄에 이어진다.

## 리스트를 한 줄로 출력

```python
numbers = [1, 2, 3]

print(numbers)
# [1, 2, 3]

print(*numbers)
# 1 2 3

print(' '.join(map(str, numbers)))
# 1 2 3
```

- `*numbers`는 리스트의 원소를 풀어서 각각의 인수로 전달한다.
- `join()`의 원소는 문자열이어야 하므로 `map(str, ...)`으로 먼저 변환한다.

## 참고 자료

- [Python 내장 함수 `input()`](https://docs.python.org/3/library/functions.html#input)
- [Python 내장 함수 `map()`](https://docs.python.org/3/library/functions.html#map)
- [Python 내장 함수 `print()`](https://docs.python.org/3/library/functions.html#print)
- [Python `sys.stdin`](https://docs.python.org/3/library/sys.html#sys.stdin)
- [이것이 취업을 위한 코딩 테스트다 with 파이썬 · 나동빈](https://github.com/ndb796/python-for-coding-test)

[Python 학습 목록](./README.md)
