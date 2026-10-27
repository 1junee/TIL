# 문자열 메서드와 인자

작성일: 2026-10-27

| 메서드 | 인자·기본값 | 동작 |
|---|---|---|
| `split(sep=None, maxsplit=-1)` | 기본은 공백 문자 기준, 횟수 제한 없음 | 문자열을 나눠 리스트 반환 |
| `separator.join(values)` | 문자열들을 담은 대상 필수 | 구분자로 연결 |
| `strip()` / `strip(chars)` | 생략하면 공백 문자 | 양끝의 문자 제거 |
| `replace(old, new, count)` | 횟수 생략 시 모두 변경 | 문자열 치환 |
| `upper()` | 없음 | 대문자로 변환 |
| `lower()` | 없음 | 소문자로 변환 |
| `startswith(prefix, start, end)` | 범위 생략 시 처음부터 끝까지 | 접두사 검사 |

## `split()`

```python
' a  b '.split()
# ['a', 'b']

' a  b '.split(' ')
# ['', 'a', '', 'b', '']

'a,b,c'.split(',', 1)
# ['a', 'b,c']
```

- `split()`은 연속된 공백 문자를 묶어서 처리한다.
- 구분자를 직접 지정하면 연속된 구분자 사이에 빈 문자열이 생길 수 있다.
- `maxsplit`은 나누는 횟수다.

## `join()`, `strip()`

```python
' / '.join(['python', 'sql', 'git'])
# 'python / sql / git'

'  hello  \n'.strip()
# 'hello'

'abbaXba'.strip('ab')
# 'X'
```

- `join()`의 구분자는 메서드 앞에 쓴다. 연결할 원소는 문자열이어야 한다.
- `strip()`은 양끝만 처리한다.
- `strip('ab')`는 `'ab'`라는 단어가 아니라 `a`, `b` 각각을 제거할 문자로 취급한다.

## `replace()`, `startswith()`

```python
'a-a-a'.replace('a', 'b')
# 'b-b-b'

'a-a-a'.replace('a', 'b', 1)
# 'b-a-a'

'/lunch'.startswith('/')
# True

'go /lunch'.startswith('/', 3)
# True
```

문자열은 불변이므로, 변환 결과를 계속 사용하려면 새 값을 받아야 한다.

```python
text = text.strip()
```

## 참고 자료

- [Python 문자열 메서드](https://docs.python.org/3/library/stdtypes.html#string-methods)

[Python 학습 목록](./README.md)
