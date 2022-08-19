# 스위프트 기본 문법

#### 콘솔 로그 남기는 방법

```swift
// 문자열 또는 관련된 정보를 문자열로 보여준다.
print("hello Olsen")

// 실제 인스턴스의 프로퍼티, 객체안에 모든 정보를 나열한다.
dump(variable)
```

####

#### 문자열 보간법&#x20;

```swift
"문자열과 함께 쓸 수 있는 /(스위프트 수식어)"
```



#### 변수와 상수

```swift
// mutable
var 변수명: type = value

// immutable (변경 불가능한 값)
let 상수명: type = value

```

* 띄어쓰기 잘 구분해서 사용한다.
* 변수 선언 키워드 둘다 할당 전에 선언가능하다.
* 타입은 생략할 수 있다. 값이 할당 되는 시점부터 컴파일러가 타입추론 가능하다.



#### 데이터 타입

```swift
// 기본 타입(구조체)
: Bool, Int, UInt(양의 정수), Float(32bit), Double(64bit), Character(unicode), String

// 컬렉션 타입(구조체)
: Array 
.append()
.contains()
.remove(at:)
.removeLast()
.removeAll() 
.count
 
: Dictionary, 
.removeValue(forkey:"keyname")

: Set
.insert()
.sorted()
.contains()
.remove()
.removeFirst()
.count
.union() //합
.intersection() //교
.subtracting() //차
  
// 기타 타입
: Any(모든 타입), AnyObject(모든 클래스 타입), Nil
 
```

* nil은 값이 존재하지 않는다는 의미이며, nil을 할당하면 변수의 값은 삭제한다.
* nil은 Nil 또는 Optional를 제외한 타입에 사용할 수 없다.
* 타입선언 Array\<Int>는  \[Int]로 축약하여 사용할 수 있다.
* 배열생성 Array\<Int>(), \[]를 사용한다.&#x20;
* 딕셔너리생성 Dictionary\<String, Any>(), \[:]를 사용한다.
* Set타입은 축약문법 존재하지 않는다.



#### 함수의 선언

```swift
func sum(a: Int, b: Int) -> Void {
    return a+b
}

// 타입 생
func noInputAndOutput() {
}

// 디폴트 값 
func sum(a: Int, b: Int = 100) -> Void {
    return a+b
}

// 전달인자 레이블, 생략
func sum(inputA a: Int, _ b: Int = 100) -> Void {
    return a+b
}
sum(inputA: 3, 4) // 7

// 가변 매개변수
func sum(inputA a: Int, inputRest b: Int...) -> Void {
    return a+b
}

let someFunc:(String, String) -> Void = sum(a:b:)

```

* 함수 호출시 사용하는 매개변수를 이해하기 쉬운 형태로 지정한 이름을 사용할 수 있다.
* 가변 매개변수를 사용하는 스코프에서 매개변수의 타입을 배열이다.



#### 조건문

```swift
if condition {}
else if condition {}
else {}

switch <varName> {
    case condition:
    case condition:
    default :
}
```

* 스위치문에서 모든 범위를 커버할 수 없을 때를 대비하여 default는 필수
* 스위치 case에서 break는 생략하여도 동작, 무시하려면 fallthough
* 스위치 condition에 범위연산자 사용가능



#### 반복문

```swift
for in { }
while { }
repeat { } while { }
```



#### 옵셔널

```swift
var number: Int?

// nil이 아닐 경우, 실행하는 블록
if let number { }
```

* nil의 가능성을 따로 주석으로 표현할 필요없이 코드로 표현(명시적)
* optional은 nil을 할당할 수 있다.
* optional은 일반 변수처럼 사용할 수 없다. 연산하는 것이 불가능

