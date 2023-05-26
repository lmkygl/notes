# ES6 문법 

## let , const , var 차이 
-  var의 scope는 함수 단위 이고 let, const의 scope는 블록 단위 이다.
- 예시 
```javascript
    function printMessage() {
        var message = "hello";

        if (true) {
            var message = "world!";

            console.log(message);
            // world!
        }

            console.log(message);
            // world!
    }

    printMessage();
```
```javascript
function printMessage() {
    let message = "hello";

    if (true) {
        let message = "world!";

        console.log(message);
        // world!
    }

    console.log(message);
    // hello
}

printMessage();
```
- var는 중복으로 변수 설정이 가능하지만, let 과 const는 변수를 중복으로 선언할 수 없다.
- var, let은 값을 다시 설정할 수 있지만, const는 한 번만 가능하다.

__정리__
 - let, const 블록스코프를 가지고 재선언 불가, 재할당 가능한 let 변수 선언 const 상수 선언 키워드  


## 템플릿 리터럴
- 내장된 표현식을 허용하는 문자열 리터럴이다.
- '', " ", 대신하여  ``사용 $와 중괄호로 표기 한다.

### Multi-line Strings
- 일반 String 사용핟여, multi-line String 들을 얻기 ES6 전에는
```javascript
console.log("string text line 1\n" + "string text line 2");
// "string text line 1
// string text line 2"
```
아래와 같이 변화함 
```javascript
console.log(`string text line 1
string text line 2`);
// "string text line 1
// string text line 2"
```

### Expression interpolation(표현식 삽입법)
- 표현식을 일반 문자열에 삽입 하기 위해서 
```javascript
var a = 5;
var b = 10;
console.log("Fifteen is " + (a + b) + " and\nnot " + (2 * a + b) + ".");
// "Fifteen is 15 and
// not 20."
```
```javascript
var a = 5;
var b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20."
```