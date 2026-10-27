# 리스트·딕셔너리 컴프리헨션

작성일: 2026-10-27

## 리스트 컴프리헨션

```python
# [만들 값 for 변수 in 대상 if 조건]

numbers = [1, 2, 3, 4, 5]
squares = [n ** 2 for n in numbers if n % 2 == 0]
# [4, 16]
```

대상에서 값을 꺼내고, 조건을 확인한 뒤, 앞의 식으로 결과를 만든다.

```python
# 조건에 맞는 원소만 남김
[n for n in numbers if n % 2 == 0]

# 모든 원소에 대해 넣을 값을 선택
['짝' if n % 2 == 0 else '홀' for n in numbers]
```

## 딕셔너리 컴프리헨션

```python
# {키: 값 for 변수 in 대상}

names = ['민수', '지은']
lengths = {name: len(name) for name in names}
# {'민수': 2, '지은': 2}
```

딕셔너리를 순회하면서 조건을 붙일 수도 있다.

```python
scores = {'민수': 80, '지은': 95, '현우': 72}

passed = {
    name: score
    for name, score in scores.items()
    if score >= 80
}
# {'민수': 80, '지은': 95}
```

## 참고 자료

- [Python 리스트 컴프리헨션](https://docs.python.org/3/tutorial/datastructures.html#list-comprehensions)
- [Python 딕셔너리](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

[Python 학습 목록](./README.md)
