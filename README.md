2.테스팅과 디버깅 갖추기
===

#### 좋은 테스트란
- 반복성

테스트 결과는 항상 재현 가능해야 한다.


- 간결성

테스트는 테스트를 하는 것에만 집중해야 한다.

- 독립성

각 테스트는 독립적으로 동작해야 한다.


#### 테스트를 만드는 방법
- 제거적 테스트 케이스

테스트와 상관없는 모든 것을 제거하여 기존의 코드가 줄어들면, 제거적 테스트 케이스가 만들어진다.

- 추가적 테스트 케이스

작은 테스트 케이스를 가지고 확인하려는 버그가 재현될 때까지 테스트 케이스를 늘려 나간다.


#### 자바스크립트 단위테스트 프레임워크 요구사항
- 브라우저의 행동을 흉내 내는 기능
- 테스트 일시 정지와 재개를 지원
- 비동기 테스트에 대한 타임아웃 처리
- 실행되어야 하는 테스트들에 대한 필터링 기능

 
3.함수가 핵심이다
===

#### 1종 객체로서의 함수
- 리터럴로 생성 가능
- 변수, 배열 엘리먼트, 다른 객체의 프로퍼티에 할당 가능
- 함수의 인자로 전달 가능
- 함수의 결과 값으로 반환 가능
- 동적으로 생성된 프로퍼티를 가질수 있음

#### 브라우저 이벤트 루프
- 사용자 인터페이스를 설정한다.
- 이벤트가 발생하기를 기다리는 루프에 진입한다.
- 발생한 이벤트에 대한 핸들러를 호출한다.


#### 함수 호출하는 방법
- 함수로 호출. myFunc();
- 메서드로 호출. myObj.myFunc();
- 생성자로 호출. new MyFunc();
- apply나 call로 호출. myFunc.call()


#### argument
- 함수에 전달된 모든 인자들을 담고 있는 컬렉션
- 배열이 아님

#### this
- 함수 콘텍스트
- 함수 호출과 관련된 객체를 참조함

#### 함수를 생성자로 호출
- 비어있는 객체가 새로 생성된다.
- 새로 생성된 객체는 this 매개변수로 생성자 함수에 전달된다.
- 명시적인 반환값이 없다면 새로 생성된 객체가 반환된다.


####apply, call
- this를 직접 설정
- apply는 인자를 배열로 전달
- call은 인자를 목록으로 직접 전달


4.함수를 자유자재로 휘두르기
====

#### callee 프로퍼티
- ECMAScript5에서는 strict 모드에서 사용 금지되었다.

#### 함수의 length 프로퍼티
- 함수 매개변수의 수를 알 수 있다.
- arguments.length를 통해 호출 시 전달된 인자 수를 알 수 있다.

5.클로저와 가까워지기
=====

#### 클로저란
- 함수를 선언할 때 만들어지는 유효 범위

- 클로저를 이용한 타이머
- 인자를 채워주는 curry 함수
- 즉시실행함수

6.객체 지향과 프로토타입
====

- 모든 객체는 constructor 라는 프로퍼티를 갖고 있다.
- 프로퍼티 참조는 해당 객체에서 먼저 해석되고, 이것이 실패했을 때 프로토타입을 조사한다.
- 모든 객체 object이므로 typeof는 "object"를 반환한다.
- 어떤 생성자 함수를 사용하여 인스턴스를 만들었는지는 instanceof를 사용한다.
- 모든 DOM 엘리먼트는 HTMLElement 생성자를 상속한다.

#### 프로토타입 체인
- subClass.prototype = new SuperClass();

7.정규표현식에 대한 논의
====

#### 정규 표현식에 사용할 수 있는 플래그
- i - 표현식이 대소문자를 구별하지 않도록 한다.
- g - 맨 처음 나타나는 부분 뿐 아니라 해당하는 모든 부분을 매치시킨다.
- m - 여러 줄을 포함하고 있는 문자열을 매치할 수 있게 해준다.


#### 정확히 같은 부분 매칭하기
- /test/ test가 그대로 포함되어야함 

#### 문자 클래스를 이용해서 매칭하기
- [abc] a,b,c중 하나와 매치
- [^abc] a,b,c 제외한 문자와 매치

#### 이스케이핑
- 다른의미로 사용되는 문자들을 그대로 사용하려면 \뒤에 작성하기

#### 시작과 끝
- /^test/ test가 처음에 와야함
- /test$/ test가 끝에 와야함
- /^test$/ test와 정확히 일치

#### 반복된 출현
- ? - 1번 또는 0번 나타나는 경우
- + - 1번 이상 나타나는 경우
- * - 0번 이상 나타나는 경우
- {a} -  a번 나타나는 경우
- {a,b} - a~b번 나오는경우
- {a,} - a번 이상 나오는 모든 경우
- 연산자 뒤에 ? 를 붙이면 nongreedy 방식으로 동작함 기본은 greedy

#### 미리 정의된 용어
- \t 수평탭
- \b 백스페이스
- \v 수직탭
- \f 폼피드
- \r 개행 문자
- \n 줄바꿈 문자
- \cA : cZ 제어 문자
- \x0000:\xFFFF 유니코드 16진수
- \x00 : \xFF 아스키 16진수
- . 줄바꿈 문자를 제외한 모든 문자
- \d 0-9 사이의 10진수 숫자 = [0-9]
- \D 0-9 사이의 10진수 숫자에 속하지 않는 모든 문자
- \w _를 포함한 모든 영어 알파벳과 숫자 = [A-Za-z0-9_]
- \W 영어 알파벳과 숫자, _가 아닌 모든 문자
- \s 공백문자
- \S 공백을 제외한 문자
- \b 단어의 경계를 나타내는 문자
- \B 단어 내에서 문자의 경계가 아닌 문자

#### 선택(OR)
- | - /a|b/ a나 b에 매치

#### 역참조
- /^([dtn]a\1) - [dtn]으로 시작하며 a가 오고 그 다음 첫글자가 다시나옴
- ex] XML마크업 = /<(\x+)>(.+)<\/\1>/


#### 함수
- "string".match(/pattern/) [매치된 문자열, [...캡쳐]]
- "string".match(/pattern/g) [...매치된 문자열전체]
- /pattern/g.exec("string") 반복실행 [매치된 문자열1, [...캡쳐]], [매치된 문자열2, [...캡쳐]], [매치된 문자열3, [...캡쳐]]

#### 캡처
- ()으로 묶은 그룹을 캡처한다.
- (?:) 을 사용하면 캡처하지 않고 묶기만 한다.
- \1로 캡처내용 매치

8.스레드와 타이머 다루기
=====

- 자바스크립트 엔진은 싱글스레드이다. 비동기 이벤트는 큐에 저장된다.
- 타이머가 블록되면 다음 실행까지 대기한다.
* settimeout, setinterval 차이점


9.닌자비술: 런타임 코드 평가
=====

#### Function 생성자
- js의 모든 함수는 Function의 인스턴스이다.
- new Function("a", "b", "return a+b;"); 
- = function(a,b){ return a+b; } 

#### 런타임 평가를 위해 자바스크립트 제공하는 방법
- eval()
- Function 생성자
- 타이머
- 동적 <script> 블록










