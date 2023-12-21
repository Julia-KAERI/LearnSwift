# 연산자


## 볌위 연산자

### 닫힌 범위 연산자

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
```

</br>

### 반 열린 범위 연산자

```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<(count-1) {
    print("Person \(i + 1) is called \(names[i])")
}
```

</br>

### 단방향 범위 연산자

```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names[2...] {
    print(name)
}
// Brian
// Jack


for name in names[...2] {
    print(name)
}
// Anna
// Alex
// Brian

for name in names[..<2] {
    print(name)
}
// Anna
// Alex
```

</br>

## 논리 연산자

| 연산자 | 의미 |
|:----:|:----------:|
| `!a` | NOT |
| `a && b` | AND |
| `a \|\| b` | OR |


