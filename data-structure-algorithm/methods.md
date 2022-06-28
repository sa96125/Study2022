# Frequently used Methods

****

### Number

* Number(str) : Number
* Number.MAX\_SAFE\_INTEGER
* Number.MIN\_SAFE\_INTEGER
* Number.isInteger(num) : Boolean
* num.toString(n) : String // n진수
* %2 === 0 // Odd(짝수) 판별
* %n // 0 \~ n까지의 수 반환



### String

* String(num) : String
* String.fromCharCode(_num_) : String // 아스키값의 문자 반환
* char.charCodeAt() : Number // 문자의 아스키값 반환
* str.split(‘’) : Array
* str.toLowerCase() : String
* str.toUpperCase() : String
* str.slice(0, **15**) : String // ”0\~15”
* str.slice(-9, -4) : String // ”-9\~-4”
* str.repeat(2) : String
* str.charAt(str.length -1) : String
* str.padStart(n, 0) : String // 길이가 N이 되도록 0을 채움
* str.padEnd(n,0) : String
* str.localeCompare(str) : Number // 1, 0, -1
* parseInt(str, n) : Number // n진수를 문자를 10진수 숫자로 변환



### Array

* arr.includes(string) : Boolean
* arr.indexOf(str) : Number(-1 : null)
* arr.reduce((acc, cur) => acc + cur) // 누적 합계
* arr.sort((a,b) => a-b) // 오름차순
* arr.join(‘’) : String
* arr.reverse() : Array
* [arr.at](http://arr.at)(-1) : Any
* arr.slice(0, **16**) : Array // \[0 \~ 15]
* arr.slice(2) : Array // \[2 \~ length-1]



### object

* let \[key, value] of Object.entries(obj) : Array
* key of Object.keys(obj) : Array
* value of Object.values(obj) : Array



### Math

* Math.abs(num) : Number // 절대값
* Math.sqrt(n) : Number // N의 제곱근
* Math.ceil(num) : Number // 올림
* Math.round(num) : Number // .5이상 반올림
* Math.floor(num) : Number // 내림
* Math.round10(55.55, -1) : Number [//55.6](https://55.0.0.6)
* Math.ceil10(51, 1) : Number // 56
* Math.max(…arr) : Number



### Map

\<aside> ✔️ Object 개념에서 순차적인 개념이 추가됨.

\</aside>

* new Map()
* map.has(k)
* map.get(k)
* map.set(k, v)
* map.delete(k)
* const \[key, values] of map
* \[…map.keys()]
* \[…map.values()]
* \[...map].sort((a,b) => b\[1] - a\[1]).map(el => el\[0])



### Set

\<aside> ✔️ 원시타입은 중복이 제거되나 참조타입은 제거되지 않음

\</aside>

* new Set()
* set.has()
* set.add()
* set.delete()
* set.size
* let \[key, values] of set
* \[…set.keys()]
* \[…set.values()]
* \[...new Set(arr)] : Array
* Array.from(set) : Array



### **RegExp**

\<aside> ✔️ 정규표현식은 문자열에서 특정 문자 조합을 찾기 위한 패턴입니다. 문자를 처리하는 방식중 하나로 특정 조건의 검색 또는 치환하는 과정을 매우 편리하게 할 수 있습니다. 정규 표현식을 만드는 방법은 두가지 입니다. 정규 표현식 리터럴, 슬래시로 패턴을 감싸서 작성하는 방법과 new RegExp('') 생성자를 호출하는 방법입니다. 리터럴의 경우 스트크립트를 불러올 때 컴파일 되므로, 패턴이 바뀔 일이 없을 때 사용하면 성능이 향상될 수 있습니다. 반면 생성자 함수를 사용하면 정규식이 런타임에 컴파일됩니다. 바뀔 수 있는 패턴, 사용자 입력으로 구성된 패턴을 생성할 경우 사용할 수 있습니다. 정확하게 일치하는 부분외에 추가적인 조건의 탐색이 필요한 경우 특수문자를 사용합니다. 정규표현식을 전역으로 사용하는 것이 아니라면 가장 먼저 찾은 문자열을 반환합니다

\</aside>

> /abc/ : "abc"와 정확하게 일치하는 부분을 탐색
>
> /ab\*c/ : "ac" \~ "abbbbbbbbbbbbbbbbbbbbc" a와 c 사이에 0번 이상의 b를 포함하는 문자열을 탐색
>
> /ab+c/ : "abc" \~ "abbbbbbbbbbbbbbbbbbbbc" a와 c 사이에 1번 이상의 b를 포함하는 문자열을 탐색
>
> /ab\\_c/ : "ab_c" 실제 특수문자 \*포함한 문자 탐색
>
> /\d/ or /\[0-9]/ <-> /\D/ or /^\[0-9]/ : 숫자 탐색
>
> /.y/ : y로 끝나는 길이 2의 문자탐색
>
> /\w/ or /\[A-Za-z0-9\_]/ <-> /\W/ or /^\[A-Za-z0-9\_]/ : 기본적인 라틴 알파벳과 언더바 문자를 탐색
>
> /\s/ <-> /\S/ : 싱글 스페이스, 탭을 탐색
>
> /\b\d{4}\b/g : 4자리 숫자를 가진 문자열 모두 탐색. (단, 단어의 중간에서는 매칭하지 않는다.)
>
> /\b\[aA]\w+/g : 알파벳 a로 시작하는 모든 문자 탐색
>
> /\w+ou?r/g : 하나 \~ 여러문자를 시작으로 or 또는 our로 끝나는 문자 탐색
>
> /\[\w ]+/ : 1개 이상 알파벳 또는 숫자 또는 언더바 또는 스페이스의 문자
>
> /^\\/ : 빈 문자열

* str.replace(/\[^\w-\_.]/g, '')
* str.replace(/\\.{2,}/g, '.')
* str.replace(/^\\.|\\.$/g, '')
* str.replace(/^$/, 'a')
* str.replace(/\\.$/, '');
* str.replace(new RegExp(<변수명>, "gi"), "대체문자열")
* regexp.test(str) : Boolean
* str.matchAll(/\[0-9]+\[SDT]\[\*#]?/g)]
* str.replace(new RegExp(word, "gi"), str)
* 'For more information, see Chapter 3.4.5.1'.match(/see (chapter \d+(\\.\d)\*)/i)) // 조합 모두 검색.



### Algorithm

* 소수 판별, 전체 소수 갯수(에라토스테네스의 체)

```jsx
const isPrime = (number) => {
    for(let i = 2; number > i; i++) {
        if(number % i === 0) { 
            return false;
        }
    }
    
    return number > 1;
}

const getPriem = (number) => {
	const numArray = new Array(n + 1).fill(1).fill(0, 0, 2);
   
  for (let i = 2; i <= Math.sqrt(n); i++) {
     for (let j = 2; i * j <= n; j++){
         numArray[i * j] = 0;
     }
  }
    
  return numArray.reduce((acc, cur) => acc+ cur)
}
```

* 약수 갯수

```jsx
const getDivisorNumber = (i) => {
	let count = 0
    
    for(let j = 1; j <= i ; j++) {
        if(i%j === 0) {
            count += 1;
        }
    }
 
    return count
}
```

* 최대 공약수와 최대 공배수, 유클리드 호제법

```jsx
let getGCD = (num1, num2) => {
    let gcd = 1;

    for(let i=2; i<=Math.min(num1, num2); i++){
        if(num1 % i === 0 && num2 % i === 0){
            gcd = i;
        }
    }

    return gcd;
}

let getLCM = (num1, num2) =>{
	let lcm = 1;
   
    while(true){
      if((lcm % num1 == 0) && (lcm % num2 == 0)){
        break;
      }
      lcm++;
    }
  	return lcm
}

const gcd = (a, b) => a % b === 0 ? b : gcd(b, a % b);
const lcm = (a, b) => a * b / gcd(a, b);
```
