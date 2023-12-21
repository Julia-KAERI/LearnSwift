# 문자와 문자열

## 문자열 literal

```swift
let someString = "Some string literal value"

let quotation = """
The White Rabbit put on his spectacles.  "Where shall I begin,
please your Majesty?" he asked.

"Begin at the beginning," the King said gravely, "and go on
till you come to the end; then stop."
"""

// `\` 는 이어지는 줄을 나타낸다.
let softWrappedQuotation = """
The White Rabbit put on his spectacles.  "Where shall I begin, \
please your Majesty?" he asked.

"Begin at the beginning," the King said gravely, "and go on \
till you come to the end; then stop."
"""
```

</br>

## 특수문자와 유니코드 표현

### 특수 문자

| literal | 의미 |
|:---:|:-------|
|`\0` | null 문자 |
|`\\` | backslash |  
| `\t` | horizontal tab |
| `\n`  | line feed |
| `\r`  | carriage return |
| `\"`  | double quotation mark|
| `\'`  | single quotation mark|


</br>

### 유니코드

```swift
let wiseWords = "\"Imagination is more important than knowledge\" - Einstein"
// "Imagination is more important than knowledge" - Einstein
let dollarSign = "\u{24}"        // $,  Unicode scalar U+0024
let blackHeart = "\u{2665}"      // ♥,  Unicode scalar U+2665
let sparklingHeart = "\u{1F496}" // 💖, Unicode scalar U+1F496
```

</br>

## Extended String Delimiters

`#` 로 감싼 문자열 리터럴은 내부의 특수문자나 특수표현을 무시한다.

```swift
let estr1 = #"alabama \n \s \""#
let estr2 = #"""
Here are three more double quotes: """
"""#
```

</br>

## 빈 문자열로 초기화

```swift
var emptyString = ""
var anotherEmptyString = String()
```

</br>

## `for` loop 에서의 문자열

```swift
for character in "Dog!🐶" {
    print(character)
}
// D
// o
// g
// !
// 🐶
```

</br>

## 문자열과 문자의 연결

```swift
let string1 = "hello"
let string2 = " there"
var welcome = string1 + string2
// welcome now equals "hello there"

let exclamationMark: Character = "!"
welcome.append(exclamationMark) // Character 는 append 함수를 사용한다.
```

### 다중 문자열 다음에 빈 줄을 넣을 것

```swift
let badStart = """
    one
    two
    """
let end = """
    three
    """
print(badStart + end)
// Prints two lines:
// one
// twothree


let goodStart = """
    one
    two

    """
print(goodStart + end)
// Prints three lines:
// one
// two
// three
```

</br>

## 문자열 보간

```swift
let multiplier = 3
let message = "\(multiplier) times 2.5 is \(Double(multiplier) * 2.5)"
// message is "3 times 2.5 is 7.5"
```

`#` 도 둘러친 문자열을 보간하기 위해서는 다음과 같이 한다.

```swift
print(#"6 times 7 is \#(6 * 7)."#)
// Prints "6 times 7 is 42."
```

</br>

## `count` 속성을 통해 문자열의 길이를 얻는다

```swift
let estr1 = #"alabama \n \s \""#
print(estr1.count)
```

</br>

## 인덱스를 통한 문자열 접근

문자열은 각 문자가 다른 바이트를 차지하며, 스위프트는 정수 인덱스를 지원하지 않는다.

```swift
let greeting = "Guten Tag!"
greeting[greeting.startIndex]
// G
greeting[greeting.index(before: greeting.endIndex)]
// !
greeting[greeting.index(after: greeting.startIndex)]
// u
let index = greeting.index(greeting.startIndex, offsetBy: 7)
greeting[index]
```

</br>

부적절한 인덱스를 이용한 접근은 런타임 에러를 발생시킨다.

```swift
greeting[greeting.endIndex] // Error
greeting.index(after: greeting.endIndex) // Error
```

문자열의 `Indices` 속성을 통해 각 문자에 접근 할 수 있다.

```swift
for index in greeting.indices {
    print("\(greeting[index]) ", terminator: "")
}
// Prints "G u t e n   T a g ! "
```

