# 들어가기 전에

1. 라이브러리(library)
    - 모듈과 패키지의 모음
    - 엄밀히 정의하자면 패키지 보다 상위 개념
    - 보통 module / package 등이 publish 되면 library라고 부른다.
    - library는 특정한 기능을 제공하는게 아니다.

2. 패키지(package)
    - 모듈의 묶음 
    - 여러 모듈들을 하나의 상위 폴더에 넣어 놓는것.
    - 기능적으로 유사한 모듈의 집합
    

3. 모듈(module)
    - import로 불러오는것이 module

4. 함수 
    - 하나의 기능을 정의 

# 프레임워크 vs 라이브러리 vs API
프레임워크 : 전체적인 흐름을 자체적으로 지님
라이브러리 : 프로그래머가 전체적인 흐름을 지님
API(Application Programming Interface): 라이브러리 컴포넌트 자체 

# SSR vs CSR vs Static Stie
- Server-side Rendering (SSR)
    - HTML을 보게 만들어 주는 작업을 서버에서 수행한다고 생각하면 된다. 
    장점 : 초기 랜더링 속도가 매우 빠르다.
          검색 엔진 최적화(SEO)를 사용할 수 있다.
    단점 : 간단한 데이터 수정에도 서버를 거쳐하는 불편함
          초기 랜더링의 수행은 빠르지만 연속적으로 랜더링을 할경우 서버에 과부하가 올 수 있다.

- Client-Side Rendering(CSR)
    - 기존 서버사이드 랜더링을 사용하게 된다면 서버에서 엄청난 과부하가 생기는 불편함이 발생하게 되어 클라이언트에 모델-뷰-컨트롤러를 장착하는 클라이언트사이드 랜더링 기술이 발달하게 된다.
    CSR은 랜더링에서 사용자가 필요한 부분만 서버에서 로딩하기 때문에 주고 받게 되는 데이터양이 현저히 줄어든다.
    장점 : 서버와 클라이언트 사이의 데이터 양과 트래픽이    현저하게 감소하게된다.
          연속된 랜더링으로 인한 과부하를 줄일 수 있다.

    단점 : 검색 엔진 최적화 사용이 불가능하다.
          랜더링을 위해 필요한 작업이 많아진다.
- Static Site 
    - 완성된 페이지  
    - 요청시 페이지만 불러옴


----
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
 - ES6 문법에서 var 사용은 지양하는것이 좋고, constfmf 우선적으로 사용하고, 값의 변경이 필요한 경우 let을 사용.

---
## next.js 설치 방법  
1. <https://nextjs.org/docs/getting-started/installation>
2. 터미널에 npx create-next-app@latest .
    1. Would you like to use TypeScript with this project? … No / __Yes__
    2. Would you like to use ESLint with this project? … No / __Yes__
    3. Would you like to use Tailwind CSS with this project? … __No__ / Yes
    4. Would you like to use `src/` directory with this project? … No / __Yes__
    5. Use App Router (recommended)? … __No__ / Yes
    6. Would you like to customize the default import alias? … __No__ / Yes
3. yarn
4. yarn dev


# yarn vs npm
npm 과 yarn은 __자바스크립트 패키지 매니저__ 이다.
우선 개발에 있어 이 둘의 차이는 크게 없다고 볼 수 있다. 다만 yarn이 npm의 부족한 점들을 개선 하였기 때문에 사용하게 되었다. 
    
- 개선 사항
    1. 속도가 빠르다.
    2. 보안성이 좋다.

npm은 이름 그대로 __노드 패키지 매니저__ 이다. 런타임 동안 노드 환경에 쓰이는 다양한 패키지들을 관리한다. 
yarn은 npm의 부족한 부분들을 개선하기 위해 개발 되어 npm과 동일한 구조에 의존한ㄷ다. 따라서 패키지의 레지스트리에 대한것은 바뀌지 않았고, 설치 절차가 바뀌 었다고 생각하면 된다.

npm은 필수 단계를 순차적으로 수행하는 경향이 있어 다음 패키지로 넘어가전에 각 패키지를 완전히 설치 해야한다. 하지만 yarn은 동시에 여러 패키지들을 설치 할 수 있기 때문에 속도 면에서 크게 향상 되었다고 볼 수 있다.(병령로 설치한다.) 
하지만, npm 5.0 버전과 비교 하였을때 차이는 크지 않다.

npm은 의존 관계를 가지는 다른 패키지들이 즉시 포함 되도록 한다.
이런 부분이 더 편리하긴 한데 보안 문제에 있어 여러 취약점들을 불러 올 수 있다.
yarn은 yarn.lock이나 package.json 파일에 있는 것들만 설치를 한다.



- axios < api 
- fetch < api node.js 내장 되어 있음
- client > backend api 호출 / client > next api 호출 > backend api 호출  차이 
