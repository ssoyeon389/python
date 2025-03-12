# python
## 숫자와 문자열 
  - 2025-03-12

```python
print("a45b".isalnum()) # 문자열이 알파벳 또는 숫자로만 구성되어 있는지 확인합니다.

print("abc".isalpha()) #문자열이 알파벳으로만 구성되어 있는지 확입합니다.

print("abc_123".isidentifier()) #문자열이 식별자로 사용할 수 있는 것인지 확인합니다.
#T:영문(A~z),숫자(0~9),_로만 구성
#F:숫자로 시작,공백이나 특수문자 포함

print("123".isdecimal()) #문자열이 정수 형태인지 확인합니다.

print("123".isdigit()) #문자열이 숫자로 인식될 수 있는 것인지 확인합니다.

print("  ".isspace()) #문자열이 공백으로만 구성되어 있는지 확인합니다.

print("abc".islower()) #문자열이 소문자로만 구성되어 있는지 확인합니다.

print("ABC".isupper()) #문자열이 대문자로만 구성되어 있는지 확인합니다.
```
## 문자열 찾기

- find() - 왼쪽부터 찾아서 처음 등장하는 위치를 찾습니다. 
- rfind() - 오른쪽부터 찾아서 처음 등장하는 위치를 찾습니다.

```python
a = "안녕안녕하세요".find("안녕") 
print(a) #0이 출력됨

b = "안녕안녕하세요".rfind("안녕")
print(b) #2가 출력됨
```
## 문자열과 in 연산자

- in 연산자:문자열 내부에 어떤 문자열이 있는지 확인할때 쓰인다.
- 출력은 True(맞다)/False(아니다) 로 나온다.

```python
print("안녕" in "안녕하세요")
#True가 출력됨
print("잘자" in "안녕하세요")
#False가 출력됨
```
## 문자열 자르기: split() 연산자

- split():문자열을 특정한 문자로 자를때 쓰인다.

```python
a = "10 20 30 40 50".split(" ") #공백을 기준으로 문자열을 자른다.
print(a) #['10', '20', '30', '40', '50'] 가 출력된다.
```
