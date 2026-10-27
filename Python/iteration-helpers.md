# 반복을 돕는 내장 함수

작성일: 2026-10-27

## `enumerate(iterable, start=0)`

값과 번호를 함께 꺼낸다. 번호의 기본 시작값은 `0`이다.

```python
menus = ['라면', '김밥']

list(enumerate(menus))
# [(0, '라면'), (1, '김밥')]

list(enumerate(menus, start=1))
# [(1, '라면'), (2, '김밥')]
```

`start=1`은 붙이는 번호만 바꾼다. 실제 리스트 인덱스는 그대로다.

## `zip(a, b)`

같은 위치의 원소를 튜플로 묶는다. 기본적으로 짧은 쪽이 끝나면 종료한다.

```python
names = ['민수', '지은', '현우']
scores = [80, 95]

list(zip(names, scores))
# [('민수', 80), ('지은', 95)]

dict(zip(names, scores))
# {'민수': 80, '지은': 95}
```

`enumerate()`, `zip()`, `reversed()`는 리스트를 바로 반환하지 않는다. 전체 결과를 확인하려면 `list()`로 감싼다.

## 참고 자료

- [Python 내장 함수 `enumerate()`](https://docs.python.org/3/library/functions.html#enumerate)
- [Python 내장 함수 `zip()`](https://docs.python.org/3/library/functions.html#zip)

[Python 학습 목록](./README.md)
