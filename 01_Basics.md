# 기본

## 상수와 변수

상수는 `let` 으로 변수는 `var` 로  선연. 한줄 주석은 `//` 로, 여러줄 주석은 `/*  */` 로.

```swift
let maximumNumberOfLoginAttempts = 10   // 상수 선언
var currentLoginAttempt = 0             // 변수 선언
var underscoreInt = 3_224_5             // 23345 와 같음 
var underscoreDouble = 11_3.2_4235         // 113.24235 와 같음

var initialValue:Double = 0             // 타입과 함께 선언, 자동 타입 변환
```

</br>

다음의 경우 에러 발생

```swift
var initialValue:Int = 5.3              // Double -> Int 안됨. 
```

## 기본 수(number) 타입

### 기본 수 타입

#### 정수형

- Unsigned : `UInt8`, `UInt16`, `UInt32`, `UInt64`,
- Signed : `Int8`, `Int16`, `Int32`, `Int64`

</br>

#### 부동소수형

- `Float`(32 bit), `Double`(64 bit)

</br>

#### 불 타입

- `true` or `false`

- 불 타입을 정수로, 정수를 불타입으로 변환시키는 내장 함수는 없다.

```swift
let s=1
let bs = (s==1) ? true : false

let t = true
let nt = (t==true) ? 1 : 0
```

</br>

### Numeric Literals

Integer literals can be written as:

- 10진수 : 두문자 없음
- 2진수 : `0b`
- 8진수 : `0o`
- 16진수 : `0x`

```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 17 in binary notation
let octalInteger = 0o21           // 17 in octal notation
let hexadecimalInteger = 0x11     // 17 in hexadecimal notation
```

</br>

### 형변환

```swift
var v1 =  1.33
print(Int(v1))

var v2 = 5
print(Double(v2))
```

</br>

### Type Alias

```swift
typealias AudioSample = UInt16

let v:AudioSample = 3
print(type(of:v), v)
```

</br>

### Optional 변수와 `nil`

변수 타입 다음에 `?` 가 붙으면 그 타입의 값 혹은 `nil` 값을 가질 수 있다는 의미이다.

```swift
var serverResponseCode: Int? = 404
serverResponseCode = nil
```

optional 변수의 값을 초기화 하지 않으면 `nil` 로 초기화된다.

```swift
var opvar:Int?
print(opvar)
```

의 결과는 `nil` 이다.

</br>

### Optional binding

Optional 변수가 `nil` 인지 확인을 하는 방법은 임시 변수에 할당하는 방법이다. 

```swift
let x : Int? = 10
let y : Int? = nil

if let xx = x {
    print("x = \(xx)")
}
else {
    print("x is Optional")
}

if let yy = y {
    print("y = \(yy)")
}
else {
    print("y is Optional")
}
```

</br>

### nil-coalescing operator `??`



```swift
var d1:Int? = nil
var d2 = d1 ?? 4
print(d2)
```