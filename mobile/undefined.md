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
* 함수마다 가변 매개변수는 하나만 가질 수 있다.



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
* !을 사용하여 값을 강제 추출할 수 있지만 선호하지 않음 만약 nil일 경우 런타임 오



#### 구조체

<pre class="language-swift"><code class="lang-swift"><strong>struct Int { 
</strong><strong>    static // 타입명에서 사용가능한 프로퍼티, 메서드
</strong><strong>} </strong></code></pre>

* 'class' 처럼 작은 따음표를 사용하면 키워드 네임을 사용할 수 있다.
* 구조체 인스턴스를 let, var 선언관계 없이 프로퍼티, 메서드 변경이 불가
* 상속할 수 없다.
* 값 타입
* 타입을 복사한다던지, 상속이 필요없을 경우 사용한다.
* 스위프트의 대부분의 기본 타입은 구조체로 이뤄진다.



#### 클래스

<pre class="language-swift"><code class="lang-swift"><strong>class Person {
</strong><strong>    static // 재정의 불가 타입메서드
</strong><strong>    class // 재정의 가능 타입메서
</strong><strong>} </strong></code></pre>

* 스위프트 클래스는 다중상속이 불가능
* 상속이 가능하다.
* 참조 타입
* 클래스 인스턴스를 let, var 선언하면 프로퍼티, 메서드 변경 가능
* 프레임워크는 클래스를 사용한다.



#### 열거형

<pre class="language-swift"><code class="lang-swift"><strong>enum Weekdays { 
</strong><strong>    case 월 = 0
</strong><strong>    case 화
</strong>    case 수
    case 목
<strong>}
</strong><strong>
</strong><strong>let 월: Weekdays? = Weekdays(rawValue:0)</strong></code></pre>

* 다른 언어에서는 정수로 열거되는 반면 스위프트에서는 문자열 지정을 통해 열거가능하다.
* 상속할 수 없다.
* Weekdays.월.rawValue 를 통해 열거된 케이스 값을 가져온다.
* 초기 0의 값을 할당하면 자동으로 다음 케이스에 1씩 증가된 값을 할당한다.
* 메서드를 추가할 수 있다.
* <mark style="background-color:red;">rawValue로 열거형 초기화하면 에러.</mark>



#### 클로저

```swift
{
    ( ) -> Void in
}

// 상수에 할
let minus: (Int, Int) -> Void
minus = { (a:Int, b:Int) -> Int in 
    return a-b
}

// 후행 클로저
result = calculate(a:10, b:10) { (left: Int, right: Int) -> Int in
    return left + right
}

// 반환 타입 생략
result = calculate(a:10, b:10) { (left: Int, right: Int) in
    return left + right
}

// 매개변수 타입 생략
result = calculate(a:10, b:10) {
    return $0 + $1
}

// 암시적 반환
result = calculate(a:10, b:10) { $0 + $1 }

```

* 콜백함수로 사용
* 컴파일러가 이미 클로저가 들어올 부분에 타입을 알고 있기 때문에 생략이 가능하다.
* 매개변수 타입 생략시 단축 인자이름으로 대체하여 사용할 수 있다. (ex $0: 첫번째, $1:두번째)
* 마지막 줄은 반환한다고 여기어 return 생략가능

