# 리스트 메서드의 인자와 반환값

작성일: 2026-10-27

| 메서드 | 인자 | 동작·반환값 | 시간 복잡도 |
|---|---|---|---|
| `append(value)` | 추가할 값 | 끝에 값 하나 추가 → `None` | O(1) |
| `insert(index, value)` | 위치, 값 | 해당 위치 앞에 삽입 → `None` | O(N) |
| `remove(value)` | 삭제할 값 | 처음 일치하는 값 하나 삭제 → `None` | O(N) |
| `pop(index=-1)` | 위치, 기본값 `-1` | 해당 위치의 값을 삭제하고 반환 | 끝은 O(1), 그 외 O(N) |
| `count(value)` | 개수를 셀 값 | 일치하는 개수 반환 | O(N) |
| `sort()` / `sort(reverse=True)` | 정렬 방향, 기본값 `False` | 원본을 오름차순 / 내림차순 정렬 → `None` | O(N log N) |
| `reverse()` | 없음 | 원본의 순서를 뒤집음 → `None` | O(N) |
| `copy()` | 없음 | 복사한 새 리스트 반환 | O(N) |

- `remove()`는 값으로, `pop()`은 위치로 삭제한다.
- `remove()`에 해당 값이 없으면 `ValueError`.
- `pop()`의 위치가 범위를 벗어나거나 리스트가 비어 있으면 `IndexError`.
- `count()`는 해당 값이 없으면 `0`을 반환한다.
- 딕셔너리의 `pop()`은 위치 대신 키를 받는다. [딕셔너리 메서드](./dict-methods.md)에 정리했다.
- `sort()`, `reverse()`와 `sorted()`, `reversed()`의 차이는 [정렬과 뒤집기](./sorting-and-reversing.md)에 정리했다.

## 중간에 넣고 빼면 O(N)인 이유

리스트는 값들이 빈칸 없이 순서대로 붙어 있다.
인덱스로 위치를 찾는 것은 바로 되지만, 중간에 넣거나 빼면 뒤의 값들을 한 칸씩 옮겨야 한다.

```text
insert(0, 5) 전:  10  20  30  40  50
값을 뒤로 밀기:    _   10  20  30  40  50
빈자리에 넣기:     5   10  20  30  40  50
```

- `append()`, `pop()`은 끝에서만 다루므로 기존 값을 옮기지 않는다.
- `insert(0, x)`, `pop(0)`은 모든 값을 한 칸씩 옮긴다.
- 앞에서 값을 자주 꺼내야 하면 `collections.deque`의 `popleft()`를 쓴다. O(1)이다.

```python
from collections import deque

queue = deque([1, 2, 3])
queue.popleft()
# 1
# queue: deque([2, 3])
```

## 참고 자료

- [Python 리스트 메서드](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
- [Python 연산별 시간 복잡도](https://wiki.python.org/moin/TimeComplexity)
- [Python `collections.deque`](https://docs.python.org/3/library/collections.html#collections.deque)
- [이것이 취업을 위한 코딩 테스트다 with 파이썬 · 나동빈](https://github.com/ndb796/python-for-coding-test)

[Python 학습 목록](./README.md)
