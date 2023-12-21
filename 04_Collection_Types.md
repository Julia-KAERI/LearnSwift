# Collection Types

- 세가지 주요한 컬렉션 타입 : Array, Set, Dictionary

- 위의 세 타입은 mutable : 삽입, 삭제, 변경이 가능함

- 포함되는 아이템의 타입이 정해져 있음.

</br>

## 배열 (Array)

- 순서에 따라 같은 타입의 아이템을 저장한다

</br>

### 생성, 삽입, 비우기

```swift
var intArray: [Int] = []        // 빈 Array
intArray.append(5)              // 삽입
intArray = []                   // 비우기
```

</br>

### 배열 합치기

```swift
var doubleArray1 = Array(repeating : 1.0, count: 4)
var doubleArray2 = Array(repeating: 2.0, count: 2)
var addedArray = doubleArray1 + doubleArray2
```

</br>

### Literal 로 배열 만들기

```swift
var stringArray : [String] = ["Aba", "Beatles"]
print(stringArray)
```

</br>

### 아이템의 타입 지정 없이 배열 만들기 + 여러가기 조작

타입 추론을 통해 ..

```swift
var arr1 = [1, 2, 3]        // [Int]
var arr2 = [1, 2.0, 3]      // [Double]
```

### 배열의 프로퍼티들

- 함수가 아님

```swift
arr1.count      //아이템 갯수
arr1.isEmpty    //비어있는지 여부
```

</br>

### 배열의 조작

```swift
var arr1 = [1, 2, 3]        // [Int]
arr1 += [4, 5, 6]           // 배열의 뒤에 배열을 붙이기 [1, 2, 3, 4, 5, 6]
arr1[1...4]=[-1, -2, -3]    // 배열 수정 [1, -1, -2, -3, 6]
arr1.remove(at:0)           // 배열 아이템 제거 [-1, -2, -3, 6]
arr1.insert(100, at:2)      // 특정 인덱스에 아이템 삽입 [-1, -2, 100, -3, 6]
arr1.removeLast()           // 마지막 원소 삭제 [-1, -2, 100, -3]
```

`removeFirst()`, `removeLast()`, `removeAll()` 등도 있다.

</br>

### `enumerated`

```swift
var animalNameArr = ["Elephant", "Rabit", "Cow", "Pig"]
for (index, item) in animalNameArr.enumerated(){
    print(index, item)
}
```

</br>

## 집합 (Set)

- 서로 다른 값들을 담는 컬렉션
- hashable 한 값만 아이템이 될 수 있다. Swift 에서 정수, 실수, 문자열(String) 은 hashable 이다.

</br>

### 빈 집합 생성

```swift
var intSet = Set<Int>()
print("intSet is of type Set<Int> with \(intSet.count) items.")
```

</br>

### 집합 조작

```swift
var animalSet = Set(["Elephant", "Rabbit", "Cow", "Pig"])
animalSet.insert("Chicken")
animalSet.remove("Human")
print("Does animalSet contains Rabbit? \(animalSet.contains("Rabbit"))")
print("animalSet.isEmpty = \(animalSet.isEmpty)")
print("animalSet.coount  = \(animalSet.count)")
```

</br>

### 집합 연산

```swift
var set1 = Set<Int>([1, 3, 5, 7])
var set2 = Set<Int>([1, 2, 3, 6])
var set3 = Set([1, 5])
print(set1.intersection(set2))      // 교집합
print(set1.union(set2))             // 합집합
print(set3.isSubset(of:set1))       // 부분집합
print(set1.isSuperset(of: set1))    // superset
print(set1.isDisjoint(with: set2))  // 서로소
```

</br>

## 사전 (Dictionary)

### 빈 사전으로 초기화 하고 아이템 만들기

```swift
var testDict: [Int: String] = [:]       //empty dictionary
testDict[1] = "Item1"
testDict[-3] = "Item-3"
```

</br>

### 사전 literal 로 사전만들기

```swift
var airports: [String: String] = ["YYZ": "Toronto Pearson", "DUB": "Dublin"]
```

</br>

### 사전 순회

```swift
print(airports.keys)
print(airports.values)
for (key, value) in airports {
    print("key = \(key), value = \(value)")
}
```
