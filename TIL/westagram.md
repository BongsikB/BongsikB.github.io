# <p align="center"> 🌈 WESTAGRAM clone project

<p align="center"> 2022.Oct. 24th ~

## 🌈 westagram | Vanila JS

1. `Login page`

   - HTML
   - CSS
   - Java script

2. `Feed page`

   - HTML
   - CSS
   - Java script

<hr>

## 1️⃣ Log-in page

- HTML | 가독성 높이기 👀

  - 🏷 `semantic tag`
  - 유지보수가 쉬운 `태그이름 짓기`

- CSS | 가독성 높이기 👀

  - CSS 컨벤션 사용
  - `들여쓰기`를 사용
  - Layout-properties → Box-prop → visual prop → Typo-prop → Misc prop 순
  - 선택자들 사이 `<br>` 한 줄 띄우기

  - CSS 레이아웃
    - `display: flex` 사용으로 추후 반응형에 적합하도록 제작
    - `rem` 단위를 사용하여 반응형을 제작

- JavaScript
  - 🎉 `Event` 사용
  - `addEventListner`동작과 원리 이해
  - `알맞은 태그명` 사용
    - e.g. `thisIsPassword`, `thisIsLoginBtn`

<hr>

## HTML | 2022.Oct.24

```HTML
  <body>
    <section class="login-page">
      <div class="login-container">
        <h1 class="instagram-logo">westagram</h1>
        <div class="login-box">
          <input
            type="text"
            id="id-input"
            placeholder="전화번호, 사용자 이름 또는 이메일"
          />
          <input type="password" id="password-input" placeholder="비밀번호" />
          <button disabled class="button_beforeType login-btn">로그인하기</button>
          <h3 class="login-failure_help">비밀번호를 잊으셨나요?</h3>
        </div>
      </div>
    </section>
    <script src="app.js"></script>


```

## CSS

```CSS
* {
  box-sizing: border-box;
}
body {
  display: flex;
  width: 100vw;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  flex-wrap: nowrap;
  text-align: center;
  background-color: #fafafa;
}

h1 {
  font-family: "Lobster", cursive;
  font-size: 3rem;
  margin-top: 0;
  margin-bottom: 4rem;
  font-weight: 200;
}

h3 {
  font-family: "Noto Sans KR", sans-serif;
  font-size: 0.8rem;
  font-weight: 500;
  color: #003668;
  margin-top: 3rem;
}

.login-container {
  margin-top: 3rem;
  border: 0.5px solid #e6e6e6;
  background-color: white;
  padding: 3rem 2.5rem 1rem 2.5rem;
}

input {
  outline: none;
  appearance: unset;
  justify-items: center;
  width: 15rem;
  border: 1px solid #efefef;
  border-radius: 0.1rem;
  background-color: #fafafa;
  padding: 0.5rem;
}

input #text {
  color: #999999;
  font-size: small;
}

.login-box {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: column;
  gap: 1rem;
}

.button_beforeType {
  appearance: unset;
  border: none;
  border-radius: 0.3rem;
  background-color: #2962ff;
  padding: 0.5rem;
  color: white;
  opacity: 30%;
}

.active {
  appearance: unset;
  border: none;
  border-radius: 0.3rem;
  background-color: #2962ff;
  padding: 0.5rem;
  color: white;
  opacity: 100%;
}

```

## ✨ JavaScript

### JavaScript 필수구현 항목

- id, pw 에 각각 한 글자 이상 써야 버튼이 활성화 되도록 해주세요.<br>
  원래 연한 파란색이었다가 -> 활성화 되면 파란색으로!🔵

> ## 🤔pseudocode
>
> ✅ 삼항 연산자 사용 <br> `condition ? exprIfTrue : exprIfFalse`<br>
> 이메일과 비밀번호 둘 중 하나 입력이 된다면 버튼이 활성화 되도록 하기 <br>
> If true : 둘 중 하나라도 입력 되었을 때<br>
> If false : 둘 중 하나라도 입력 되지 않았을 때<br>
> OR ID가 1개라도 입력 되었거나 || PW가 1개라도 입력 되었다면 Btn on <br>
> 만약 둘 중 하나라고 입력이 되었다면 ? 버튼 온 : 아니라면 버튼 스탠바이 <br>
> 박스 login-box <br>
> 로그인 아이디 #id-input<br>
> 비밀번호 아이디 #password-input<br>
> 로그인 버튼 클래스 .login-btn<br>

```javascript
//3차 - 멘토님 코칭
const thisIsId = document.querySelector("#id-input");
const thisIsPassword = document.querySelector("#password-input");
const thisIsLoginBtn = document.querySelector(".login-btn");

function activeButton() {
  thisIsLoginBtn.classList.remove("button_a");
  thisIsLoginBtn.classList.add("active");
  thisIsLoginBtn.disabled = false;
}
function inactiveButton() {
  thisIsLoginBtn.classList.remove("active");
  thisIsLoginBtn.classList.add("button_a");
  thisIsLoginBtn.disabled = true;
}

function handleClick(event) {
  const inputID = document.querySelector("#id-input").value;
  const inputPW = document.querySelector("#password-input").value;
  console.log(inputID, inputPW);

  const isValid = inputID.length >= 1 && inputPW.length >= 8;

  isValid ? activeButton() : inactiveButton();
}

thisIsId.addEventListener("keyup", handleClick);
```

🗝 핵심 포인트

- `thisIsLoginBtn`.disabled = false; 버튼이 제대로 활성화 되지 않았던 이유
  - 타겟을 지정해 주지 않았음
- `삼항연산자` 사용을 위한 함수 생성
  - ` isValid ? activeButton() : inactiveButton();`
  - 💬 과제 출제 의도 파악도 필요하다

## 📝 코드 들여다보기

- `href`

  - 뒤로 가기 가능

- `replace`

  - 뒤로 가기 불가
  - 보안이나 기획의도에 따라 이전페이지 접근을 막을 수 있음

- `addEventListner`

  - 여러 이벤트 리스너들을 함수로 제어할 수 있음

  ```javascript
  function init() {
    // 이벤트를 읽는 코드들을 집합
    //eventlistner...
  }
  init();
  ```

```javascript
//2차 작성코드 2022.Oct.27
const thisIsId = document.querySelector("#id-input");
const thisIsPassword = document.querySelector("#password-input");
const thisIsLoginBtn = document.querySelector(".login-btn");

function handleClick(event) {
  const inputID = document.querySelector("#id-input").value;
  const inputPW = document.querySelector("#password-input").value;

  if (inputID.length >= 1 && inputPW.length >= 8) {
    //작동은 하지만 아이디의 길이가 1이상이 아닌 3에서, 패스워드는 8이상에서 버튼이 활성화 된다.
    // 인덱스가 [0] 으로 시작하기 때문이라고 유추한다.
    // 28일 멘토님을 귀찮게 할 예정.. :)
    thisIsLoginBtn.classList.remove("button_beforeType");
    thisIsLoginBtn.classList.add("active");
    disabled = false;
  } else {
    thisIsLoginBtn.classList.remove("active");
    thisIsLoginBtn.classList.add("button_beforeType");
    disabled = true;
  }
}

thisIsId.addEventListener("keyup", handleClick);
```

```Javascript
//2차 작성코드 2022.Oct.26
const thisIsId = document.querySelector("#id-input");
const thisIsPassword = document.querySelector("#password-input");
const thisIsLoginBtn = document.querySelector(".login-btn");

thisIsLoginBtn.addEventListener("click", () => {
  const inputID = document.querySelector("#id-input").value;
  const inputPW = document.querySelector("#password-input").value;

  if (inputID.length > 1 && inputPW.length > 1) {
    console.log("hi");
  }

if (inputID.length >= 1 && inputPW.length >= 1) {
  document.getElementsByClassName("login-btn").disabled = false;
  //disable default값은 true 비활성화인상태.
  //disable은 시각적으로는 보이나 이벤트리스너가 작동하지 않는 '무'의 상태에 가깝다.
  //고로 위의 코드는 수정이 필요
}
});

thisIsId.addEventListener("keyup", handleClick);
```

```HTML
<button disabled class="button_beforeType login-btn" disabled>로그인하기</button>
```

`disabled` 채택한 이유:

- `disabled`을 사용하여 HTML 태그 사용법을 학습 하고자 하였다.
- JavaScript에서 `동적 요소`와 `disabled`의 확장성을 학습하였다.

<hr>

## 2️⃣ Main/feed page

- HTML

- CSS

- JavaScript

<hr>

## 2️⃣ Feed-in page

- HTML | 가독성 높이기 👀

  - 🏷 `semantic tag`
  - 직관적인 `태그이름 짓기`

- CSS | 가독성 높이기 👀

  - CSS 컨벤션 사용
  - `들여쓰기`를 사용
  - Layout-properties → Box-prop → visual prop → Typo-prop → Misc prop 순
  - 선택자들 사이 `<br>` 한 줄 띄우기

- JavaScript

  - 🎉 `Event` 사용
  - `appendChild`동작과 원리 이해
  - `innerHTML`동작과 원리 이해
  - `알맞은 태그명` 사용

### Javascript

```javascript
//필수 구현 항목 : 댓글 추가
const commentInput = document.querySelector(".main__feed_comments_input");
const commentForm = document.querySelector(".main__feed_comments_form");
const commentBtn = document.querySelector(".main__feed_comments_enter");
const commentArea = document.querySelector(".comment_area");
const addComment = document.getElementsByClassName("letAddNewComment");
let commentValue = "";
//값이 없다로 시작하기 위함

commentInput.addEventListener("keyup", function () {
  commentValue = commentInput.value;
  if (commentValue.length > 0) {
    commentBtn.disabled = false;
    commentBtn.style.cursor = "pointer";
    commentBtn.style.color = "#488bff";
  } else {
    commentBtn.disabled = true;
    commentBtn.style.cursor = "default";
    commentBtn.style.color = "#488bff";
  }
});

//${id} + ${ctx} + delete button
//const inputCtx = input.value;

commentForm.addEventListener("submit", (event) => {
  event.preventDefault();
  const newCommentCtx = commentInput.value;
  const newComment = document.createElement("li");
  newComment.innerHTML = `<li> <span><b>0713.jpg</b></span>   ${newCommentCtx} </li>`;
  addComment[0].appendChild(newComment);
});
```

> 엔터를 쳐서 값을 가져오고 싶은데 -> form태그에 input & button 넣기 <br>
> 왜 프리벤트이벤트가 안되던 오류 -> form 태그에 이벤트리스너를 붙여줬어야 함<br> `<ul><li></li></ul>`<br>
> ul안에 어펜드차일드 <br>`newComment.innerHTML = <li> ${newCommentCtx} </li>`<br>
> li에 새롭게 입력합니다<br>`addComment[0].appendChild(newComment)`<br> 원래는 `document.appendCHild`였는데 그 뜻은 전체 화면을 덮어 씌운다 라는 의미<br>
> 그래서 `addCommnet의 0번 인덱스`에서 가져온다로 수정<br>`getElementbyclassname`으로 가져왔기 떄문에 → 이 건 배열로 가져오게 됨<br> `const addComment = document.getElementsByClassName("letAddNewComment")` <br> ul이 중복 사용되었기 때문에 클래스네임을 할당함

> `<ul>` > ` <li>``</li> ` `</ul>`ul안에 어펜드차일드

> newComment.innerHTML = `<li> ${newCommentCtx} </li>`;
> li에 새롭게 입력합니다
> addComment[0].appendChild(newComment);
> 본래 document.appendCHild였는데 그 뜻은 전체 화면을 덮어 씌운다 라는 의미
> 그래서 addCommnet의 0번 인덱스에서 가져온다로 수정
> getElementbyclassname으로 가져왔기 떄문에 → 이 건 배열로 가져오게 됨

// const addComment = document.getElementsByClassName("letAddNewComment");
//ul이 중복 사용되었기 때문에 클래스네임을 할당함

<hr>

### 🌳 성장 포인트

- `시맨틱 태그` 사용을 통하여 사람과 컴퓨터에게 의미를 전달하는 HTML 작성
- 가독성을 높인 `들여쓰기`, `CSS 컨벤션`을 규칙을 적용하여 추후 `유지보수에 용이`하도록 함
- 각 HTML, CSS, JavaScript의 역할을 이해하였으며, JavaScript에서 method통하여 값을 변경하는 확장성에 중심을 두었습니다.
- JavaScript의 꽃, `Event`,`addEventListner`동작과 원리를 이해
- 삼항연산자를 사용한 가독성이 좋은 코드 작성
- `작동하는 코드가 아닌 더 나은 코드` 💪
  - `semantic tag` & `삼항연산자` & `tag convention`
- 나의 보폭에 맞는 속도로 차근히 생각하고 코드 작성이 도움이 되었다.
- I never lose, Either I win or lean.

<hr>
<p align="center"> E.O.D 2022/10/31
