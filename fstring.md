# 숫자와 문자열의 다양한 기능
## 2025/03/19

-str()함수

```python
>>> "3 + 4 = " + str(3 + 4)
'3 + 4 = 7' #로 출력이된다.
```

### f-문자열
- format() 함수: format() 함수의 매개변수를 {} 안에 대치할 수있음
```python
a = 10
print("{}".format(a)) #a의 값이 출력됨
print(f"{a}") #a의 값이 출력됨
print("{}and{}".format(10, 20)) # 10and20 이 출력됨
print("{1}and{0}".format(10,20)) # 20and10이 출력됨
```
- 여러 줄 문자열 출력
```python
print(f"""1 + 2 = {1 + 2}
2 + 3 = {2 + 3}
3 + 4 = {3 + 4}""")
# 1 + 2 = 3
# 2 + 3 = 5
# 3 + 4 = 7
출력
```

### 정렬
- f-문자열을 이용하여 문자열 정렬하기
- < : 왼쪽 정렬 / > : 오른쪽 정렬 / ^ : 가운데 정렬
- f'{hello:*^10'} ---> 빈공간  * 로 채우기
- _를 공백으로 표시함.
```python
a = 'hello'
print(f'{a:<10}') #hello_ _ _ _ _
print(f'{a:>10}') #_ _ _ _ _hello
print(f'{a:^10}') #_ _hello_ _ _
print(f'{a:*^10'} #**hello***
```
## f-문자열보다 format()함수를 사용하는 것이 더 좋은 경우
- 문자열이 긴 상황
- 데이터를 리스트에 담아서 사용하는 경우

ex)f-문자열로 형식화해서 출력함
```python
data = ['별', 2, 'M', '서울특별시 강서구', 'Y']
print(f"""이름: {data[0]}
나이: {data[1]}
성별: {data[2]}
지역: {data[3]}
중성화 여부: {data[4]}""")
```
ex)format()함수와 전개 연산자를 사용하여 간단히 입력
```python
data = ['별', 2, 'M', '서울특별시 강서구', 'Y']
print("""이름 : {}
나이: {}
성별: {}
지역: {}
중성화 여부: {}""".format(*data)) #--- *data = data[0], data[1], data[2] ~~~
```

### 마무리

- format() : 함수를 이용하면 **숫자와 문자열**을 다양한 형태로 출력할 수 있다.
- f-문자열: 문자열 안에 값을 format() 함수보다 **간단하게** 삽입할 수 있다.

### 문제

3.
```python
a = input("> 1번째 숫자: ")
b = input("> 2번째 숫자: ")
print()

print(" {} + {} = {}".format(a, b, int(a)+ int(b)))
```
-->input()으로 입력받은 숫자는 **문자열**이므로 원하는 계산을 할 때는 숫자로 변환해야 한다. / int() 함수 사용

4.다음 프로그램의 실행 결과 예측
```python
string = "hello"

#string.upper()를 실행하고, string 출력
string.upper()
print("A지점:", string)
#string.upper() 실행하기
print("B지점", string.upper())
```
---> upper()함수를 실행하면 대문자로 변경/원본변수는 변하지 않기 때문에 첫번째 출력은 소문자이다.
