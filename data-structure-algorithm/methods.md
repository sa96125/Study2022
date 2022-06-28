# 필수 메서드

****

### **배열 요소(문자열) 중복 제거 후 반환**

* \[...new Set(arr)] : Array

{% hint style="info" %}
&#x20;자료구조가 문자열로 이루어진 배열, 중복 제

\["muzi frodo","apeach frodo","frodo neo","muzi neo","apeach muzi"]
{% endhint %}







### **객체 키, 배열 루프**

* let \[key, value] of Object.entries(obj) : Array
* key of Object.keys(obj) : Array
* value of Object.values(obj) : Array

\


### **배열 값(문자) 포함 확인**

* arr.includes(string) : Index

\


### **배열 값의 위치 인덱스 반환**

* arr.indexOf(str)

### **배열 분리, 합체, 역순**





* str.split(‘’) : Array
* arr.join(‘’) : String
* arr.reverse() : Array

\


### **문자열 대/소문자로 변경 후 반환**

* str.toLowerCase() : String
* str.toUpperCase() : String

\


### **문자열 잘라서 반환 (0\~15 포함)**

* str.slice(0, 15)

\


### **배열 잘라서 반환 (0\~ 15 포함)**

* arr.slice(0, 16)

\


### **문열 반복 후 반환**

* str.repeat(?)

\


### **마지막 요소/문자 반환**

* [arr.at](http://arr.at)(-1)
* str.charAt(str.length -1)

\


### **형변환**

* parseInt(str, n) : 숫자(n진수)
* num.toString(n) : 문자열(n진수)

\


### **수학 메서드**

* Math.abs  :  절대값

\


### **% 연산**

* %2 === 0 : 짝수
* %8 : 0 \~ 7까지의 수. (8은 0)

\


### **두 수의 비교(오름차순), 연산(합)**

* arr.reduce((a,b) => a+b)
* arr.sort((a,b) => a-b)&#x20;

\


### **소수 확인**

```
const isPrime = (number) => {
    for(let i = 2; number > i; i++) {
        if(number % i === 0) { 
            return false;
        }
    }
    return number > 1;    
}
```

\


### **Map**

* map.has(k)
* map.get(k)
* map.set(k, v)
* map.delete(k)
* const \[key, values] of map
* \[…map.keys()]
* \[…map.values()]
* \[...map].sort((a,b) => b\[1] - a\[1]).map(el => el\[0])

\


### **문자열의 검색 또는 치환하여 반환(feat. RegExp)**

* str.replace(/\[^\w-\_.]/g, '')
* str.replace(/\\.{2,}/g, '.')
* str.replace(/^\\.|\\.$/g, '')
* str.replace(/^$/, 'a')
* str.replace(/\\.$/, '');
* str.replace(new RegExp(<변수명>, "gi"), "대체문자열")

\


### 정규표현식

정규표현식은 문자열에서 특정 문자 조합을 찾기 위한 패턴입니다. 문자를 처리하는 방식중 하나로 특정 조건의 검색 또는 치환하는 과정을 매우 편리하게 할 수 있습니다.

정규 표현식을 만드는 방법은 두가지 입니다. 정규 표현식 리터럴, 슬래시로 패턴을 감싸서 작성하는 방법과 new RegExp('') 생성자를 호출하는 방법입니다. 리터럴의 경우 스트크립트를 불러올 때 컴파일 되므로, 패턴이 바뀔 일이 없을 때 사용하면 성능이 향상될 수 있습니다. 반면 생성자 함수를 사용하면 정규식이 런타임에 컴파일됩니다. 바뀔 수 있는 패턴, 사용자 입력으로 구성된 패턴을 생성할 경우 사용할 수 있습니다. 정확하게 일치하는 부분외에 추가적인 조건의 탐색이 필요한 경우 특수문자를 사용합니다. 정규표현식을 전역으로 사용하는 것이 아니라면 가장 먼저 찾은 문자열을 반환합니다

\


* /abc/   :  "abc"와 정확하게 일치하는 부분을 탐색
* /ab\*c/   :  "ac" \~ "abbbbbbbbbbbbbbbbbbbbc" a와 c 사이에 0번 이상의 b를 포함하는 문자열을 탐색
* /ab+c/   :  "abc" \~ "abbbbbbbbbbbbbbbbbbbbc" a와 c 사이에 1번 이상의 b를 포함하는 문자열을 탐색
* /ab\\\*c/  :  "ab\*c" 실제 특수문자 \*포함한 문자 탐색&#x20;
* /\d/ or /\[0-9]/ <-> /\D/ or /^\[0-9]/  :  숫자 탐색
* /.y/  :  y로 끝나는 길이 2의 문자탐색
* /\w/ or /\[A-Za-z0-9\_]/  <-> /\W/ or /^\[A-Za-z0-9\_]/  :  기본적인 라틴 알파벳과 언더바 문자를 탐색
* /\s/  <-> /\S/   :  싱글 스페이스, 탭을 탐색
* /\b\d{4}\b/g  : 4자리 숫자를 가진 문자열 모두 탐색. (단, 단어의 중간에서는 매칭하지 않는다.)
* /\b\[aA]\w+/g : 알파벳 a로 시작하는 모든 문자 탐색
* /\w+ou?r/g  :  하나 \~ 여러문자를 시작으로 or 또는 our로 끝나는 문자 탐색
* /\[\w ]+/  : 1개 이상 알파벳 또는 숫자 또는 언더바 또는 스페이스의 문자
* /^\\/  : 빈 문자열
