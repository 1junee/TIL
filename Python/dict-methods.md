# 딕셔너리 메서드

작성일: 2026-10-27

## 조회

| 표현 | 동작 |
|---|---|
| `data[key]` | 값 조회. 없는 키면 `KeyError` |
| `data.get(key)` | 값 조회. 없는 키면 `None` |
| `data.get(key, default)` | 없는 키일 때만 `default` 반환 |
| `key in data` | 키가 있는지 확인 |

```python
user = {'name': '민수', 'city': '서울'}

user['name']
# '민수'

user.get('age')
# None

user.get('age', 0)
# 0

'city' in user
# True
```

`get()`은 조회만 하고 딕셔너리를 바꾸지 않는다.

## 삭제: `pop()`

| 표현 | 동작 |
|---|---|
| `data.pop(key)` | 키를 삭제하고 값을 반환. 없으면 `KeyError` |
| `data.pop(key, default)` | 키가 없으면 지정한 기본값 반환 |

```python
user = {'name': '민수', 'city': '서울'}

city = user.pop('city')
# city: '서울'
# user: {'name': '민수'}

user.pop('city', '없음')
# '없음'
```

리스트의 `pop()`은 위치를 받고, 딕셔너리의 `pop()`은 키를 받는다. 딕셔너리에서는 키를 생략할 수 없다.

## 순회: `keys()`, `values()`, `items()`

| 표현 | 꺼내는 값 |
|---|---|
| `data.keys()` | 키 |
| `data.values()` | 값 |
| `data.items()` | `(키, 값)` 쌍 |

```python
scores = {'민수': 80, '지은': 95}

for name, score in scores.items():
    print(name, score)
# 민수 80
# 지은 95
```

딕셔너리를 `for`로 바로 순회하면 키를 꺼낸다.

## 참고 자료

- [Python 딕셔너리](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)

[Python 학습 목록](./README.md)
