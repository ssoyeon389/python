# 문자열,리스트,딕셔너리와 관련된 기본 함수
## 2025/03/21

- 파이썬 고유 기능
- min():인수로 받은 자료형 내에서 최소값을 찾아서 반환하는 함수
- max():인수로 받은 자료형 내에서 최댓값을 찾아서 반환하는 함수
- sum():이터러블 객체의 모든 요소를 합산하는 함수
- reversed():리스트 뒤집는 함수
- enumerate():현재 인덱스가 몇 번째인지 확인하는 함수
- items():딕셔너리에 있는 키와 값들의 쌍을 얻을수 있도록 해주는 함수

### 리스트에 적용할 수 있는 기본 함수: min(),max(),sum()
- 예제
```python
numbers = [103, 52, 273, 32, 77]
print(min(numbers)) #최솟값 출력 
print(max(numbers)) #최댓값 출력
print(sum(numbers)) #리스트 내부 값 합산한 값 출력
```
- 리스트를 사용하지 않고 최솟값,최댓값 구하기
```python
print(min(103, 52, 273)) #최솟값 출력
print(max(103, 52, 273)) #최댓값 출력
```

### reversed() 함수로 리스트 뒤집기
- reversed() 함수 사용 예제
```python
list_a = [1, 2, 3, 4, 5]
list_reversed = reversed(list_a)

print("# reversed() 함수")
print("reversed([1, 2, 3, 4, 5]):", list_reversed)
print("list(reversed([1, 2, 3, 4, 5])):", list(list_reversed))
print()

print("# reversed() 함수와 반복문")
print("for i in reversed([1, 2, 3, 4, 5]):")
for i in reversed(list_a):
    print("-", i)
```

```python
temp = reversed([1, 2, 3, 4, 5])

for i in temp:
    print("첫번째 반복문:{}".format(i))

for i in temp:
    print("두번째 반복문:{}".format(i))
```
- 두번째 반복문은 출력되지 않는다.
- reversed() 함수 결과가 **제너레이터** 이기 때문
- **제너레이터**는 특별한 종류의 **이터레이터** 이다. 모든 값이 미리 계산되지 않고 요청에 따라 하나씩 값을 생성함 --> 메모리 절약 + 반복 로직을 표현하기 쉬워짐
- reversed() 함수와 반복문을 조합할때 함수의 결과를 여러 번 활용X, for 구문 내부에 reversed() 함수를 곧바로 넣어서 사용O
```python
numbers = [1, 2, 3, 4, 5, 6]

for i in reversed(numbers):
    print("첫 번째 반복문: {}".format(i))

for i in reversed(numbers):
    print("두 번째 반복문: {}".format(i))
```
- 이 예제에선 for 구문 내부에 reversed() 함수를 바로 넣어 사용함.

### enumerate() 함수와 반복문 조합하기
- enumerate():리스트의 요소를 반복할 대 현재 인덱스가 몇 번째인지 나타내줌
- 에제
```python
example_list = ["요소A", "요소B", "요소C"]

print(example_list) #그냥 출력하기
print() #튜플로 출력

print(enumerate(example_list)) #enumerate 함수적용 출력
print()

print(list(enumerate(example_list))) #list() 함수로 강제 변환 출력
print()

for i, value in enumerate(example_list):
    print("{}번째 요소는 {}입니다.".format(i, value)) #for 반복문과 enumerate() 함수 조합해서 출력
```
enumerate() 함수를 사용하면 for 와 in 사이에 **반복 변수를 두개 넣을수 있음**

### 딕셔너리의 items() 함수와 반복문 조합하기
- 딕셔너리는 items() 함수와 함께 사용하면 **키와 값**을 조합해서 쉽게 반복문을 작성할수 있음
- 예제
```python
example_dictionary = {
    "키A": "값A",
    "키B": "값B",
    "키C": "값C",
}

print("items():", example_dictionary.items()) #딕셔너리 items() 함수 결과 출력
print()

for key, element in example_dictionary.items():
    print("dictionary[{}] = {}".format(key, elemet)) #for 반복문과 items()함수 조합
```

### 리스트 내포
- 다음 코드는 range(0, 20, 2)로 0 부터 20사이의 짝수를 구한 뒤 제곱해서 새로운 리스트를 만듦
```python
array = []

for i in range(0, 20, 2):
    array.append(i * i)

print(array)
```
- 파이썬에서는 더 간단하게 구현 가능
```python
array = [i * i for i in range(0, 20, 2)] #최종 결과를 앞에 작성
print(array)
```
