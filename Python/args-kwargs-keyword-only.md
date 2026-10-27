# `*args`, `**kwargs`, 단독 `*`

작성일: 2026-10-27

| 표현 | 의미 |
|---|---|
| `*args` | 여러 위치 인수를 튜플로 받음 |
| `**kwargs` | 여러 키워드 인수를 딕셔너리로 받음 |
| 단독 `*` | 뒤의 매개변수를 키워드로만 받도록 지정 |

```python
def add_all(*numbers):
    return sum(numbers)

add_all(1, 2, 3)
# 6
```

```python
def make_profile(**info):
    return info

make_profile(name='민수', age=25)
# {'name': '민수', 'age': 25}
```

```python
def shout(text, *, upper=False):
    return text.upper() if upper else text

shout('hi', upper=True)  # 가능
# shout('hi', True)      # TypeError
```

`args`, `kwargs`는 관례적인 이름이며, 기능은 별표가 정한다. `*args` 뒤에 오는 일반 매개변수도 키워드로만 전달한다.

## 참고 자료

- [Python 임의 인수 목록](https://docs.python.org/3/tutorial/controlflow.html#arbitrary-argument-lists)
- [Python 키워드 전용 인수](https://docs.python.org/3/tutorial/controlflow.html#special-parameters)

[Python 학습 목록](./README.md)
