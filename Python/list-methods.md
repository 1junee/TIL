# 리스트 메서드의 인자와 반환값

작성일: 2026-10-27

| 메서드 | 인자 | 동작·반환값 |
|---|---|---|
| `append(value)` | 추가할 값 | 끝에 값 하나 추가 → `None` |
| `insert(index, value)` | 위치, 값 | 해당 위치 앞에 삽입 → `None` |
| `remove(value)` | 삭제할 값 | 처음 일치하는 값 하나 삭제 → `None` |
| `pop(index=-1)` | 위치, 기본값 `-1` | 해당 위치의 값을 삭제하고 반환 |
| `count(value)` | 개수를 셀 값 | 일치하는 개수 반환 |
| `copy()` | 없음 | 복사한 새 리스트 반환 |

- `remove()`는 값으로, `pop()`은 위치로 삭제한다.
- `remove()`에 해당 값이 없으면 `ValueError`.
- `pop()`의 위치가 범위를 벗어나거나 리스트가 비어 있으면 `IndexError`.
- `count()`는 해당 값이 없으면 `0`을 반환한다.

## 딕셔너리의 `pop()`

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

## 참고 자료

- [Python 리스트 메서드](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
- [Python `dict.pop()`](https://docs.python.org/3/library/stdtypes.html#dict.pop)

[Python 학습 목록](./README.md)
