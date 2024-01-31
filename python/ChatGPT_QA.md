# Q : 세 정수를 기준으로 오름차순으로 출력하는 코드를 너가 다시 만들어줘 

# A : (explained below)
물론입니다. 아래는 주어진 세 정수를 오름차순으로 정렬하여 출력하는 코드입니다.

```python
a, b, c = map(int, input('세 정수를 입력하시오: ').split())
sorted_numbers = sorted([a, b, c])
print(*sorted_numbers)
```

이 코드는 `map` 함수를 사용하여 입력된 세 정수를 정수로 변환하고, 그 후 `sorted` 함수를 사용하여 정렬된 리스트를 생성합니다. 마지막으로 `print(*sorted_numbers)`를 사용하여 정렬된 숫자를 공백으로 구분하여 출력합니다.

## 이전 코드:

```python
a, b, c = input('세 정수를 입력하시오 : ').split()
a = int(a)
b = int(b)
c = int(c)

'''
if a < b:
    if b < c:
        print(a, b, c)
    elif b > c and a > c:
        print(c, a, b)
    else:
        print(a, c, b)
elif a >= b:
    if a < c:
        print(b, a, c)
    elif a > c and b > c:
        print(c, b, a)
    else:
        print(b, c, a)
'''
  
if a < b < c:
    print(a, b, c)
elif a < c < b:
    print(a, c, b)
elif b < a < c:
    print(b, a, c)
elif b < c < a:
    print(b , c, a)
elif c < a < b:
    print(c, a, b)
elif c < b < a:
    print(c, b, a)
```
