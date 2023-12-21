# 흐름 제어

## `for`-`in`

</br>

## `while` 과 `repeat-while`

- while 은 처음부터 조건을 확인하지만 `repeat-while` 은 수행 후 조건 확인

```swift
var c = 2
while(c>=3){
    c -= 1
}
print(c)

c=2
repeat{
    c -= 1
} while(c>=3)
print(c)
```

앞의 결과는 2 이며 뒤의 결과는 1 이다.

</br>

## `if` - `else if` - `else`

```swift
var a = 1
if a>1 {
    print(1)
} else if a>0 {
    print(2)
} else {
    print(3)
}
```

</br>

### `if` 문을 이용한 변수 할당

```swift
var a = 0
var b:Int? = if a<0 {
    -1
} else if a>0 {
    1
} else {
    nil
}
print(b)
```

</br>

## `switch`-`case`-`default`

```swift
let mychar: Character = "a"
switch mychar {
case "a":
    print("a")
case "z":
    print("z")
default:
    print("not in b-y")
}
```

</br>

### Value binding and where

- tuple 에서만 가능함.
  
```swift
let anotherPoint = (2, 0)
switch anotherPoint {
case (let x, 0):
    print("on the x-axis with an x value of \(x)")
case (0, let y):
    print("on the y-axis with a y value of \(y)")
case let (x, y):
    print("somewhere else at (\(x), \(y))")
}
```



```swift
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
case let (x, y) where x == y:
    print("(\(x), \(y)) is on the line x == y")
case let (x, y) where x == -y:
    print("(\(x), \(y)) is on the line x == -y")
case let (x, y):
    print("(\(x), \(y)) is just some arbitrary point")
}
```

</br>

### Compound Cases

```swift
let someCharacter: Character = "e"
switch someCharacter {
case "a", "e", "i", "o", "u":
    print("\(someCharacter) is a vowel")
case "b", "c", "d", "f", "g", "h", "j", "k", "l", "m",
    "n", "p", "q", "r", "s", "t", "v", "w", "x", "y", "z":
    print("\(someCharacter) is a consonant")
default:
    print("\(someCharacter) isn't a vowel or a consonant")
}
```

</br>

## 제어 전환 표현

다음과 같은 제어 전환 표현이 있다.

- `break`
- `continue`
- `fallthrough`
- `return`
- `throw`

</br>

### `continue`

- loop 에서 현재번의 수행을 중지하고 다음 번의 수행으로 넘어간다
- 다음 코드는 `2` 를 빼고 출력한다
  
```swith
for i in 1...4 {
    if i == 2 {
        continue
    }
    print(i)
}
```

</br>

### `break`

- 흐름제어를 탈출한다
- 다음 코드는 `1` 만을 출력한다

```switch
for i in 1...4 {
    if i == 2 {
        break
    }
    print(i)
}
```

</br>

## `defer`

함수나 제어문 안의 `defer { }` 구문은 함수나 제어문이 종료 되기 직전에 `{ }` 안의 구문이 실행된다.


