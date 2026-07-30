JavaScript는 위키피디아의 정의에 따르면 HTML, CSS와 함께 월드 와이드 웹의 핵심 기술을 이루는 프로그래밍 언어로 웹페이지에 동적 기능을 부여하고 사용자와 상호작용하는 역할을 한다.

우리가 자바스크립트를 웹에서 사용할 수 있는건 웹브라우저마다 자바스크립트를 해석하고 실행하는 엔진을 가지고 있기 때문이다. 구글 크롬과 마이크로스프트 엣지는 V8, 애플 사파리는 자바스크립트코어라는 엔진을 가지고 있다.

현재 자바스크립트는 웹에만 한정하여 사용하고 있지 않다. 대표적으로 앞서 말한 크롬의 V8 엔진을 기반으로 만들어진 자바스크립트 런타임(실행 환경)인 Node.js는 전통적인 언어(ex. C, Java, PHP)가 처리하지 못하던 비동기 방식으로 코드를 처리해주며 실시간 데이터/채팅, 미디어 스트리밍 & 실시간 트래픽 처리, 대규모 API 서버, 백엔드 개발 등 많은 곳에 쓰이고 있다.

---

자바스크립트의 현재 사용 용도와 기술을 정리하면 다음과 같다. 괄호는 해당 기술 기반으로 만들어졌다는 것을 의미한다.

1. 웹 프론트엔드
- React(Node.js): Meta가 만든 UI 라이브러리로 프론트엔드 생태계에서 가장 압도적인 점유율을 차지한다.
- Vue.js(Node.js): Evan You가 개발한 UI 구축용 Progressive 자바스크립트 프레임워크이다.
- Angular: Google에서 개발 및 유지 관리하는 오픈소스 TypeScript 기반 웹 애플리케이션 프레임워크이다.
2. 웹 백엔드
- **Node.js(Chrome V8 JavaScript Engine): 웹브라우저 밖에서도 자바스크립트를 실행/사용할 수 있게 해주는 실행 환경(런타임)이다. Node.js의 등장으로 자바스크립트 언어 하나만으로 웹 풀스택을 개발할 수 있게 되었다.**
- Express(Node.js)
- NestJS(Node.js)
3. 웹 풀스택(프론트엔드 + 백엔드)
- Next.js(React + Node.js)
- Nuxt.js(Vue.js + Node.js)
4. 모바일 앱 개발
- React Native(React): 하나의 React 소스 코드로 iOS와 Android 앱을 동시에 개발하는 기술로 실제 네이티브 UI 컴포넌트로 변환되어 빠른 속도를 낸다.
- Ionic
5. 데스크톱 앱 개발
- Electron(Node.js)
- Tauri(Rust)
6. 3D 웹 그래픽 및 게임 개발
- Three.js: 웹브라우저에서 3D 그래픽을 쉽게 구현할 수 있도록 도와주는 자바스크립트 라이브러리이다.
- Phaser: 웹브라우저에서 실행되는 2D 게임을 개발할 수 있도록 도와주는 오픈소스 자바스크립트 게임 프레임워크이다.

많은 기술들이 Node.js 기반으로 만들어졌기에 거의 모든 주요 클라우드 플랫폼(AWS, Google Cloud, Microsoft Azure)에서는 Node.js 개발 환경을 지원한다. **로컬에서 해당 기술들을 작업하기 위해서는 파이썬을 쓰기 위해 공식 홈페이지에서 파이썬 실행 환경(런타임)을 다운 받는 것처럼 다른 분야에서 자바스크립트를 쓰기 위해 Node.js 실행 환경(런타임)을 설치해야 한다.**

---

자바스크립트 주요 문법

1. 변수 선언
- const: 재할당이 불가능한 상수 선언
- let: 재할당이 가능한 변수 선언
- var
2. 데이터 타입
- 기본형(메모리에 값을 저장): Number, String, Boolean, undefined, null, Symbol, BigInt
- 참조형(메모리에 값이 저장된 주소를 저장): Object, Array, Function
3. 함수
- 일반 함수 선언
- 화살표 함수 선언

4. 최신 주요 문법(ES6+ 핵심 특성)
- Template Literals(템플릿 리터럴): 문자열 내부에서 백틱(`)을 사용하면 계산식이나 함수 호출, 변수를 자유롭게 삽입할 수 있다.
- Destructuring(구조 분해 할당): 배열이나 객체의 속성을 해체하여, 그 값을 각각의 독립된 변수에 직접 할당할 수 있게 해주는 자바스크립트 표현식이다.
- Spread Operator(스프레드 연산자): 점 3개를 사용해 배열이나 객체를 복사하거나 합친다.

5. **DOM: HTML 문서의 모든 요소를 자바스크립트가 이해하고 조작할 수 있는 객체의 트리 구조로 나타낸 것이다.** DOM 요소는 참조형(객체) 데이터로 상수가 가리키는 메모리 주소는 그대로 두고, 객체 내 속성을 바꾸는 것은 자유롭게 허용되기 때문에 const여도 내부 값을 바꿀 수 있다.
- Document Querying(요소 탐색): 화면에 그려진 HTML 요소를 자바스크립트 변수로 가져온다.
```js
// ID가 'submit-btn'인 요소를 탐색하여 submitBtn 상수에 할당
const submitBtn = document.querySelector('#submit-btn');

// 클래스가 'item'인 모든 요소를 탐색하여 items 상수에 배열(NodeList)로 할당
const items = document.querySelectorAll('.item');
```
- 내용 및 속성 변경: 선택한 요소의 글자, HTML 구조, CSS 스타일, 속성을 수정한다.
```js
// ID가 'main-title'인 요소를 탐색하여 title 상수에 할당
const title = document.querySelector('#main-title');

// 1. 글자 내용 변경 (텍스트만 안전하게 변경)
title.textContent = '반갑습니다!';

// 2. HTML 구조 변경 (태그를 해석하여 화면에 반영)
title.innerHTML = '<span>강조된 제목</span>';

// 3. CSS 스타일 변경 (상수에 할당되었지만 객체 내부 속성은 변경 가능)
title.style.color = 'blue';
title.style.fontSize = '24px';


// 클래스가 'profile'인 요소를 탐속하여 profileImg 상수에 할당
const profileImg = document.querySelector('.profile');

// 4. 속성 변경 (이미지 태그의 src 속성을 새 주소로 변경)
profileImg.setAttribute('src', 'new-image.png');
```
- 요소 생성 및 삭제: 새로운 HTML 요소를 동적으로 만들어서 화면에 붙이거나 삭제한다.
```js
// 새로운 <li> 태그 요소를 생성하여 newTodo 상수에 할당
// (아직 화면에 나타나지 않고 메모리 상에만 존재함)
const newTodo = document.createElement('li');

// 생성한 <li> 요소의 내부 글자 속성을 변경 (const이지만 내부 속성이므로 변경 가능)
newTodo.textContent = '자바스크립트 공부하기';

// 새 요소가 들어갈 부모 태그(<ul>)를 탐색하여 todoList 상수에 할당
const todoList = document.querySelector('#todo-list');

// 부모 태그인 todoList의 마지막 자식으로 newTodo 요소를 화면에 붙임
todoList.appendChild(newTodo);


// 화면에서 지우고 싶은 요소를 탐색하여 oldItem 상수에 할당
const oldItem = document.querySelector('.old-item');

// oldItem 상수가 가리키는 주소의 HTML 요소를 화면과 DOM 트리에서 완전히 제거
oldItem.remove();
```
- **Event Handling(이벤트 리스너): 사용자의 클릭, 키보드 입력, 마우스 이동 등의 행동을 감지한다.**
```js
<button id="myButton">버튼</button>

const btn = document.getElementById('myButton');

// 버튼을 클릭하면 콘솔에 "안녕하세요!"가 출력
// 일반 함수 사용
btn.addEventListener('click', function() {
  console.log('안녕하세요!');
});

// 버튼을 클릭하면 콘솔에 "안녕하세요!"가 출력
// 화살표 함수 사용
btn.addEventListener('click', () => {
  console.log('안녕하세요!');
});
```