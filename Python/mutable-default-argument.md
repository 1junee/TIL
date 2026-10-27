# 리스트 기본값과 `None`

작성일: 2026-10-27

```python
def add_item(item, items=[]):
    items.append(item)
    return items

print(add_item('라면'))
# ['라면']

print(add_item('김밥'))
# ['라면', '김밥']
```

기본값은 함수가 정의될 때 평가된다. 기본값이 리스트라면 이후 호출에서 같은 리스트를 공유하므로 값이 누적될 수 있다.

호출마다 새 리스트가 필요하면 `None`을 기본값으로 둔다.

```python
def add_item(item, items=None):
    if items is None:
        items = []
    items.append(item)
    return items

print(add_item('라면'))
# ['라면']

print(add_item('김밥'))
# ['김밥']
```

`if items is None:`은 `None`인지 확인한다. `if not items:`는 빈 리스트도 참으로 판단하는 조건이므로 의미가 다르다.

## 참고 자료

- [Python 기본 인수 값](https://docs.python.org/3/tutorial/controlflow.html#default-argument-values)

[Python 학습 목록](./README.md)
