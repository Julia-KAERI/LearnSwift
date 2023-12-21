# 함수 (Function)

## parameter 와 argument

swift 에서 함수의 정의의 예를 들어보자

```swift
func myfunc(initial vi:Int, final vf:Int)->[Int]{
    Array(stride(from:vi, to:vf+1, by:1))
}
var arr1 = myfunc(initial:1, final:10)
```

함수의 정의에서 `initial`, `final` 은 argument label 이라고 한다. 함수를 실제로 호출할 때 사용하는 변수이다. `vi`, `vf` 는 parameter name 이라고 한다. 함수를 정의할 때 내부에서 사용하는 변수이다. argument label 을 생략할 때는 `_` 를 쓴다.

```swift
func incr(_ input:Int)->Int {
    return input+1
}
print(incr(3))
```
</br>

## 묵시적 반환

함수의 몸체가 한줄일 때 `return` 이 없더라도 이 표현을 반환한다.

```swift
func incr(_ v: Int)->Int{
    v+1
}

let c:Int = incr(3) // c == 4
```

