# Mutable과 Immutable

작성일: 2026-10-26

객체를 만든 뒤 그 객체 자체를 변경할 수 있는지의 차이다.
변수는 객체를 가리키는 이름이며, 변수에 다른 값을 대입하는 것과 객체를 변경하는 것은 다르다.

| 구분 | 의미 | 대표 자료형 |
| --- | --- | --- |
| Mutable | 객체 자체를 변경할 수 있다. | `list`, `dict`, `set` |
| Immutable | 객체 자체를 변경할 수 없다. | `int`, `float`, `bool`, `str`, `tuple`, `frozenset` |

## 리스트 대입은 복사가 아니다

```python
original = [1, 2]
shared = original
copied = original.copy()

shared.append(3)
print(original)  # [1, 2, 3]
print(copied)    # [1, 2]
```

`original`과 `shared`는 같은 리스트를 가리킨다.
`.copy()`는 새 리스트를 만들지만, 얕은 복사이므로 안쪽에 중첩된 리스트까지 복사하지는 않는다.

## Immutable도 변수 재대입은 가능하다

`text = text.upper()`는 기존 문자열을 바꾸는 대신, 반환된 새 문자열을 `text`에 재대입한다.
문자열의 특정 위치에 대입하는 `text[0] = "P"`는 `TypeError`가 발생한다.

튜플도 요소를 교체할 수 없지만, 안에 들어 있는 리스트 자체는 변경할 수 있다.

```python
items = ([1, 2], "python")
items[0].append(3)
print(items)  # ([1, 2, 3], 'python')
```

## 참고 자료

- [Python 객체와 가변성](https://docs.python.org/3/reference/datamodel.html#objects-values-and-types)
- [Python 리스트 복사](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)

[Python 학습 목록](./README.md)
