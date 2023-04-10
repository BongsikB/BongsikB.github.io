## <p align="center"> `Internship` 📆 12/12

### ⏰ Setting time

1. install nvm: [https://github.com/creationix/nvm](https://github.com/creationix/nvm)
   ```jsx
   $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
   ```
2. install node stable version: `nvm install stable`
3. install yarn: `npm install -g yarn`
   ```jsx
   $ nvm install vNN.NN.N
   //사용하고자 하는 버전 으로 변환 합니다
   ```
4. install requirements: `yarn install`
5. create `.env` according to `.env.example`
6. start project `yarn start`

## 📍 NVM 버전을 고정하기

1. 재부팅 후 접속시, 터미널의 nvm 버전이 바뀌는 것을 방지 하기 위함입니다.
1. 최신 버전이 아닌 특정 버전을 써야하는 경우에 필요합니다.

   ```jsx
   $ nvm list
   //현재 nvm 버전을 확인
   ```

   ```jsx
   $ nvm use v14
   //원하는 버전으로 변경 (임시적)
   ```

   ```jsx
   $ nvm alias default v14
   //원하는 버전으로 디폴트 값 고정
   ```

   <img width="856" alt="재부팅" src="https://user-images.githubusercontent.com/110847597/207327527-45b7bedb-a64f-46bc-80cb-bd6415532f3b.png">
   > 가끔은 터미널도 재부팅이 필요하다

### 🛥 Onboarding

1. 깃허브 세팅이 완료 되었다면
1. 깃허브 `package.json` 을 둘러보며 사용되는 것들 확인하기!

🌳 성장 포인트

1.`yarn` `npm` 차이 학습 1.`redux`학습 필요!

---

## <p align="center"> `Internship` 📆 12/13

## 🛥 Onboarding 🌊🌊🌊

### 👀 미리 둘러 볼 것!

- [x] `packagelock.json`의 의존성 확인
- [x] `Git branch` 확인
- [x] `Pull Request` 컨벤션 확인
- [x] `Commit message` 컨벤션 확인

---

## <p align="center"> `Internship` 📆 12/16

### 📍 Class Components

```jsx
// App.js

import React from 'react';

class App extends React.Component {
  render() {
    return <h1>This is Class Component!</h1>;
  }
}
export default App;
```

> 클래스 컴포넌트에서는 위와 같이 반드시 render() 메서드가 있어야 하고, 그 안에서 화면에 보여줄 JSX(Javascript Syntax eXtension) 를 반환합니다. state 및 lifecycle(라이프사이클) API를 통해 관련 기능을 사용할 수 있습니다.

```jsx
console.log(this.props);
console.log(columns);
//위의 두가지로 알아낸 데이터 구조
```

🌳 성장 포인트 :

- 클래스 컴포넌트를 사용
  - 학습을 위하여 class component를 사용 중, 기존의 작업되어있는 프로젝트도 클래스 컴포넌트로 구성되어 있다.
- `console.log`를 찍어보며 어떤 데이터가 들어오는지 확인해 보는 습관을 가지자.
- `this`의 컴백

---

## <p align="center"> `Internship` 📆 12/19

### 📚 `antd table` library

엣헴... [📎 antd table: 공식 사이트](https://ant.design/components/table)

> 어쩐지... props로 어떤 값을 넣어도 오류가 났다.<br>
> 당연함, 라이브러리의 명세를 확인 했어야했다.<br>
> 오늘의 교훈, package.json을 열심히 확인하고... 검색을 꼭 해보자.<br>
> 둘째 날... 사수께서 확인해보라던게 이런 라이브러리가 있다는 걸 보란거였다. 하지만 아는만큼 보인다고 응애인 나는 몰랐다. antd를 자체적으로 만든건 줄 알았다.. 오늘이라도 알아서 다행이다.

```jsx
<Table
  className='table table_small'
  rowSelection={rowSelection}
  columns={columns}
  dataSource={data}
  onRow={record => ({
    onClick: () => {
      this.selectRow(record);
    },
  })}
/>
```

```jsx
    const data = [
      {
        key: '1',
        SCHEDULE_NAME: 'test1',
        CREATED: '2022/12/25',
        SCHEDULE_TAG: 32,
      },
      {
        key: '2',
        SCHEDULE_NAME: 'test2',
        CREATED: '2022/12/30',
        SCHEDULE_TAG: 42,
      },
...
    ];

    const columns = [
      {
        title: 'SCHEDULE NAME',
        dataIndex: 'SCHEDULE_NAME',
        key: 'SCHEDULE_NAME',
      },
      {
        title: 'SCHEDULE TAG',
        dataIndex: 'SCHEDULE_TAG',
        key: 'SCHEDULE_TAG',
      },
...
    ];
```

공식문서를 따라 작성하면 짜잔, 이렇게 이미지가 뜬다. 👏👏👏
![after table screenshot](https://user-images.githubusercontent.com/110847597/208448995-d5fbacc8-0d0d-4702-bcb1-a7876419f791.png)

내일 할 일:

- [ ] SCSS를 수정하기, 커밋하기

<br>

### <p align="center">📛 `This.state?` `This.Props?`

> 현업 코드를 보다보니, this가 정말 많이 쓰이고 있었다.
> 어디서 호출하느냐에 따라 바인딩 되는것이 결정된다는데 더 적극적으로 공부를 해야겠다.

📝 This.state

1. `this.state` : state를 해당 컴포넌트에서 만들 때

🧚‍♀️ This.props

1. `this.props` : 부모 컴포넌트나, 리덕스에서 `해당 컴포넌트에 주입` 할 때

🌳 성장 포인트 :

- 내가 어렵다면, 어려운 것이 맞다!
  - 그때마다 물어보고 또 알아보자!
- 라이브러리를 많이 써보고 친숙해 져야겠다.
- `this` 공부도 잊지 말자!

## <p align="center"> `Internship` 📆 12/21

### 📝 class components Error + `this`

### 😈 오늘 만난 에러

_`Uncaught RefereceError:isStagingSchedulingTableShown`이 선언되지 않았다는 것._
<img width="1000px" alt="Error!!" src="https://user-images.githubusercontent.com/110847597/208923021-1b281f3d-db2f-494d-b0a9-23cab8b6a201.png" align="center">

🤔 하지만 난 분명 선언을 했는데?
이렇게 말이다! 👇
<img width="1000px" alt="Error!!2" src="https://user-images.githubusercontent.com/110847597/208923028-c15f834d-f8e7-485b-9a67-e710c3dd7d4d.png" align="center">

🧐 차근히 코드를 훑어보다, `this`를 사용한다는걸 알게 되었고 함수형 컴포넌트와는 다름을 알게 되었다.
<img width="1000px" alt="Error!!3" src="https://user-images.githubusercontent.com/110847597/208923033-9a6026af-92a1-42ac-bfd2-b5dc1dc09cf7.png" align="center">

아래와 같이 this.state 이 컴포넌트에서 만들고, 선언하겠음을 컴퓨터에게 알렸다.
<img width="1000px" alt="Error!!fix!" src="https://user-images.githubusercontent.com/110847597/208923037-cf51b5e3-3585-4b75-8fa1-3ce7eb44d8ce.png" align="center">

잘 해결하였다. 뿌듯 💪

```jsx
//Counter.js
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      increaseNum: 0,
      decreaseNum: 100,
    };
  }

  render() {
    const { increaseNum, decreaseNum } = this.state;
    return (
      <div>
        <h1>증가하는 값 : {increaseNum}</h1>
        <h2>감소하는 값 : {decreaseNum}</h2>
        <button
          onClick={() => {
            this.setState({
              increaseNum: increaseNum + 1,
              decreaseNum: decreaseNum - 1,
            });
          }}
        >
          Increase / Decrease
        </button>
      </div>
    );
  }
}

export default Counter;
```

> [[React] 클래스형 컴포넌트에서 state 사용하기](https://velog.io/@choie0423/React-%ED%81%B4%EB%9E%98%EC%8A%A4%ED%98%95-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EC%97%90%EC%84%9C-state-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)

### 🌳 성장 포인트 :

- 에러에 당황하지 않고 읽어보고, 검색하고 코드를 하나씩 체크하며 스스로 해결하고 있다.
- 비록 클래스 컴포넌트를 많이 사용하지 않는 추세이지만, 부딪혀보고 경험하고 있어 많이 배우고 있다.

출처:

- [[React] 클래스형 컴포넌트에서 state 사용하기](https://velog.io/@choie0423/React-%ED%81%B4%EB%9E%98%EC%8A%A4%ED%98%95-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EC%97%90%EC%84%9C-state-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)

## <p align="center"> `Internship` 📆 12/22

### 📝 class components `componentDidMount()`

- `uncaught invariant violation: hooks can only be called inside`

  - 통신 준비를 위하여 `useEffect와` `fetch`를 작성하고 렌더 하는 순간, 발생된 오류
    <img width="529" alt="KakaoTalk_Photo_2022-12-23-00-14-51" src="https://user-images.githubusercontent.com/110847597/209169628-7c2a358b-1bba-49e7-ad13-95cb3f83f52e.png">
  - 코드를 아무리 확인 해도, 내 hook은 함수 내부에 선언 되어 있었다.
  - 클래스 컴포넌트와 함수형 컴포넌트의 차이를 몸소 배우는 시간이었다.
  - 함수형과 클래스 컴포넌트의 가장 큰 차이점은, 생명주기를 관리 할 수 있는 Hook의 차이

    - Hook이 등장하기 전 까지, 클래스 컴포넌트만 생명주리를 관리할 수 있었다고 한다.
    - Hook의 등장으로 함수 컴포넌트가 많이 활성화 되었다고 한다.
    - 즉, Hook이 나오기 전에는 함수 컴포넌트에서 생명주기를 관리하기 어려웠다는것!

    ### 📌 Component types

    | &#32;    | Class component                | Function component            |
    | -------- | ------------------------------ | ----------------------------- |
    | 난이도   | 심화 및 필수!                  | 초심자에게 추천               |
    | 필수사항 | ✨ `render()` 메서드           | &#32;                         |
    | 특징     | State & Lifecycle API 사용가능 | Hook 등장이후 `state`사용가능 |

    - [My TIL:🧢 React Component](https://github.com/Dabnii/Dabnii.github.io/blob/main/React/React%20component.md)

    ```jsx
    componentDidMount() {
      fetch('../../../api/requests/MockDataSchedule.json').then(res =>
        tagReadData(res).then(console.log('Saved!')),
      );
    }
    ```

    [Ref: Fetching Data in React using Hooks](https://blog.bitsrc.io/fetching-data-in-react-using-hooks-c6fdd71cb24a?gi=bc14f2a9db99)

    > 클래스컴포넌트를 사용하게 되어서 영광이다. 함수 컴포넌트를 쓸 때 보다 더 많이 넘어지지만, 확실히 많이 배워간다. 특히나 `this`의 개념이 확립되는 중.

    ![KakaoTalk_Photo_2022-12-23-00-14-40 002](https://user-images.githubusercontent.com/110847597/209169661-13f590b6-db7d-452a-966b-2f87dd34a2bc.png)

    <img width="519" alt="KakaoTalk_Photo_2022-12-23-00-14-40 001" src="https://user-images.githubusercontent.com/110847597/209169666-6735970f-9fd5-46ad-946e-d81bf9ebd156.png">

    - 그리고 콘솔로그를 많이 찍어보며, 코딩하는 중입니다.

    ![KakaoTalk_Photo_2022-12-23-00-14-40 004](https://user-images.githubusercontent.com/110847597/209169654-30fbbff1-5745-4c94-ade7-aecd424ac119.png)

    <img width="514" alt="KakaoTalk_Photo_2022-12-23-00-14-40 007" src="https://user-images.githubusercontent.com/110847597/209169643-d20127ee-c18b-48d8-9b84-3c58a82fc5fc.png">

    - 담기지 않았습니다. 슬픕니다.

## <p align="center"> `Internship` 📆 12/23

### 📝 class components

- `object` + `map`

```jsx
//Parent
state = {
    responseType: null,
  };
//최상위에서 state를 선언합니다.

const {
      responseType,
    } = this.state;
//구조분해 할당을 통하여 this.state에 responseType을 넣습니다

const typeList = [
  {
    label: 'Retraining',
    value: 'retraining',
  },
  { label: 'Batch Prediction',
		value: 'batch_prediction' },
];

//기존에 하드코딩 하던 부분을, 맵을 돌려 사용합니다.
<div className="tabs-menu__item">
    {typeList.map(item => {
      return (
        <button
          key={item.value}
          type="button"
          className="button-menu__link link_active"
          value={item.value}
          onClick={() =>
            this.setState({ responseType: item.value })
          }
        >
          <div className="tab-text">
            <span className="tab-menu__item">
              <span>{item.label}</span>
            </span>
          </div>
        </button>
      );
    })}
</div>

		<SchedulingTag
        workspaceId={workspaceId}
        projectId={projectId}
        responseType={responseType}
      />
```

2. 위의 부모 컴포넌트에서 작업이 끝났다면, 자식 컴포넌트에 프롭스로 전달 합니다.

```jsx
//child
componentWillMount() {
    const { workspaceId, projectId, responseType } = this.props;
    this.getTableApi({ workspaceId, projectId });
  }
//전달 받은 프롭스 구조분해할당을 해줍니다

//responseType은 fetch를 사용할 때
`url${workspaceId}/projects/${projectId}/tags/type/${responseType}`,
//추가: 훌륭한 네임으로 바꾸는 것이 좋겠군요...
```

### 🧢🏈 `try & catch`

- `try...catch` 문은 실행할 코드블럭을 표시하고 예외(exception)가 발생(throw)할 경우의 응답을 지정합니다.
- `오류 및 예외를 처리` 함 대게 같이 작용함 [Try...catch MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/try...catch)
- 사용하게 된 이유는, 유효한 url을 호출 하지만 의도대로 되지 않아 확인을 위하여 사용했다.

```jsx
try {
  nonExistentFunction();
} catch (error) {
  console.error(error);
  // expected output: ReferenceError: nonExistentFunction is not defined
  // Note - error messages will vary depending on browser
  // MDN
}
```

```jsx
try {
  hello.toUpperCase();
} catch {
  console.log('Error');
}
```

```jsx
function yell(msg) {
  try {
    console.log(msg.toUpperCase().repeat(3));
  } catch (e) {
    console.log('try again');
  }
}
```

### 🫡 실제 try catch를 활용한 코드

```jsx
//child
//Try & Catch
getTableApi = async ({ projectId, workspaceId, responseType }) => {
  const authToken = localStorage.getItem('auth_token');
  try {
    const response = await fetch(`url`, {
      method: 'GET',
      headers: {
        Authorization: authToken,
        'client-server': 'application/json',
      },
    });

    const tagReadData = await response.json();
  } catch (err) {
    console.log(err);
  }
};
//async await도 사용하여 너무나 반가웠다.
```

- 😩 아직 내가 헷갈리는 파트
  - `this.setState({ responseType: item.value })`
  - 어제 담지 못한 데이터를 담았다! 👏
- `fetch`할 때 한 실수들:
  - 1️⃣ `fetch url`을 감싸는 중괄호가 두 개 였다.
    - 목데이터용, 실제 테스트용을 복붙하여 작성하다 생긴 실수였다.
  - 2️⃣ `postman`에 등록된 데이터가 없는 url에서 데이터를 호출했다.
    - 하드코딩으로 주소를 고정하여 테스트 했음

### 🌳 인턴 둘째 주 회고 :

### 👍 잘한 것:

- `👩‍🏫 class component`를 사용하기로 한 것
  - 많은 차이점들을 몸소 느낄 수 있었고, 새롭고 어렵기에 꾸준한 동기부여가 된다.
  - 꾸준히 TIL을 쓰고 있고 출퇴근 시간에 복기하고 있다!
- `🙋‍♀️ 효율적인 질문`
  - 모두의 시간은 금. 사수의 시간도 금이기에 충분히 시도해보고, 노력한 후 객곽적으로 정리하여 물어봤다.
    - 예를 들어, 이러한 기능을 구현하려고 부모, 자식 컴포넌트도 확인 하고 콘솔로 확인 했는데 두 번째 부터 찍히지 않는다.

### 💪 아쉬운 것:

- `🕰️ 시간 관리`
  - 일정을 세세하게 짜고 진행 했지만, 의외의 에러와 이슈로 일정이 조금씩 딜레이 되고 있다.
  - 특히 라이브러리 CSS 구간에서 시간을 많이 소요했는데, 앞으로 디테일은 기능 구현 이후에 하는 것으로...

---

## <p align="center"> `Internship` 📆 12/26

### 📊 antd table ✅ checkbox

```jsx
//한참 찾은 input 값 배열에 넣기!
state = {
  keys: [],
};

<Table
  columns={columns}
  dataSource={tagReadData.results}
  rowSelection={{
    type: 'radio',
    selectedRowKeys: this.state.keys,
    onChange: this.onRowKeysChange,
  }}
  rowKey={record => record.id}
  onRow={record => ({
    onClick: () => {
      this.selectRow(record);
    },
  })}
/>;
```

- `keys`를 배열로 선언 합니다.
- `rowselection={{ type: 'radio'}}`로 디폴트 값을 바꿔줍니다.

### 🔌 Fetch!

```jsx
getTableApi = async ({ projectId, workspaceId, responseType }) => {
  console.log('table api 통신 시작!!!');
  const authToken = localStorage.getItem('auth_token');

  try {
    const response = await fetch(`url`, {
      method: 'GET',
      headers: {
        Authorization: authToken,
        'client-server': 'application/json',
      },
    });

    const tagReadData = await response.json();
    console.log(tagReadData.results);
    this.setState({ tagReadData });
  } catch (err) {
    console.log(err);
  }
};

const { selectedRowKeys, tagReadData } = this.state;
//렌더하는 곳에서 구조분해 할당을 해주어야함.
```

## <p align="center"> `Internship` 📆 12/27

```jsx
uploadTagCreate = async () => {
  const { workspaceId, projectId } = this.props;
  const { responseType, keyDataFromChild } = this.state;
  console.log(keyDataFromChild);
  await api({
    url: `url`,
    method: 'post',
    headers: { 'content-type': 'application/json' },
    data: {
      tag_id: keyDataFromChild[0],
    },
  }).then(response => {
    const { data } = response;
  });
};
//200 OK 🫡
```

![200OK!](https://user-images.githubusercontent.com/110847597/209746568-7568e051-a34f-45fe-8922-6453cbd94f33.png)

### 📎 axios

```jsx
//fetch로 발생할 수 있는 오류를 방지하기 위하여 axios 활용
sortTagsApi = async () => {
  const { workspaceId, projectId } = this.props;
  const { responseType, schedulingTagList } = this.state;

  await api({
    url: `url`,
    method: 'get',
    headers: { 'content-type': 'application/json' },
  }).then(response => {
    const { data } = response;
    this.setState({ schedulingTagList: data.results });
    // tagID : Num
  });
};
```

### 👩‍👩‍👧‍👦 자식에서 부모로 데이터 보내기

```jsx
//parent
state = {
  keyDataFromChild: [],
};

uploadTagCreate = async () => {
  const { keyDataFromChild } = this.state;

  await api({
    url: `url`,
    method: 'post',
    headers: { 'content-type': 'application/json' },
    data: {
      tag_id: keyDataFromChild[0],
    },
  }).then(response => {
    const { data } = response;
  });
};

const getKeyData = value => {
  this.setState({ keyDataFromChild: value });
};

//child
state = {
  keys: [],
};

onRowKeysChange = keys => {
  this.setState({ keys });
  const { getKeyData } = this.props;
  getKeyData(keys);
};
```

### 🛡 임시방편 로직

```jsx
const { invalid } = this.props;
// invalid는 form field의 값들을 체크하고 업로드 버튼을 제어하고 있다
// 너무 깊은 프롭스인 관계로 원 출처를 찾지 못했다.
// 그러하여 아래의 임시 방편 방안으로 해결..

const { invalidCheck: true } = this.state
// invalid응 임시방편으로 사용할 새로운 스테이트를 선언

const getKeyData = value => {
  this.setState({ keyDataFromChild: value });
  this.state.keyDataFromChild !== []
    ? this.setState({ invalidCheck: false })
    : this.setState({ invalidCheck: true });
};
// 위의 작성 한, 자식 요소에서 받아온 keys값을 담은 스테이트를 사용
// keyDataFromChild가 빈 값이 아니라면 (즉, key값이 배열에 있다면)
// invalidCheck의 값은 false가 되어 disabled를 해제합니다.
// TMI 나의 최애 삼항
<BlueButton
  type="submit"
  className="button_uppercase"
  disabled={invalid || invalidCheck}
  onClick={onClickButton}
>
```

### 🌳 성장 포인트 :

- console.log를 찍으며 어떤 문제가 있는지 확인!
- 혼자서 해낼 수 있는 것들이 많아지고 있다. 🥹
  - fetch도 혼자서 척척.. 200 ok 짜릿
- 자식에서 부모로 넘기기 까지 성공
- 임시방편 로직도 작성했다.
  - 나는... 유지보수가 쉽게 코드를 쓸것이다.
  - 돌아가는 코드 말고, 잘 짜여진 코드를 쓰자.

## <p align="center"> `Internship` 📆 12/29

- `retraining_batch` 라면 분할 하여 `retraining`,`batch_prediction`로 렌더
- 태그가 하나일 때 `matchingTag` 하나의 박스로 렌더하기
- 처음에 `for`을 사용하여 매핑 하려 했지만, 조건이 2가지가 되기 때문에 아래의 코드로 수정.

```jsx
state = {
  matchingTag: '',
  // 하나의 태그일 경우의 스테이트
  matchingTags: '',
  retrainingTag: '',
  // 두가지 경우 일 때, retrainingTag 값을 담는 곳
  batchPredictionTag: '',
  // 두가지 경우 일 때, batchPredictionTag 값을 담는 곳
};

mapApiData = () => {
  const { scheduleDetails } = this.props;
  const scheduleType = scheduleDetails.type;
  const scheduleTags = scheduleDetails.tags;

  if (scheduleType === 'retraining_batch') {
    scheduleTags.map((el, i) => {
      if (el.type === 'retraining') {
        this.setState({ retrainingTag: el.tag });
      }
      if (el.type === 'batch_prediction') {
        this.setState({ batchPredictionTag: el.tag });
      }
    });
  } else {
    scheduleDetails.map((el, i) => {
      this.setState({ matchingTag: el.tag });
    });
  }
};
```

```jsx
<div className='ant-form-item-control-wrapper'>
  {scheduleDetails.type === 'retraining_batch' ? (
    //리액트에서 삼항 조건을 주어 렌더링 할 수 있음
    <>
      <input
        className='tagInput'
        name='name'
        type='text'
        placeholder={this.state.retrainingTag}
        readOnly
      />
      <input
        className='tagInput'
        name='name'
        type='text'
        placeholder={this.state.batchPredictionTag}
        readOnly
      />
    </>
  ) : (
    <input
      className='tagInput'
      name='name'
      type='text'
      placeholder={this.state.matchingTag}
      readOnly
    />
  )}
</div>
```

## <p align="center"> `Internship` 📆 12/27

```jsx
if (Number.isInteger(keepCount) === false) {
  inputValue = Math.round(keepCount);
}
```

- total 데이터 수 와 사용자가 입력하는 값을 연산하여 남는 값을 렌더링 해야한다.
  - 간단해 보였지만 조건이 여러가지가 필요했다.
  - 상수여야 한다 → 소수점 이라면 반올림 한다
    - `isInteger`을 활용하여 로직을 짰지만 작동하지 않는다.
    - `while`을 사용하여 값이 참이면 계속 조건을 순회하게 할지 고민이다.
  - 지울 값이 가진 데이터 값보다 클 수 없다

### 🌳 인턴 셋째 주 회고 :

### 👏 잘한 점

1. 라이브러리에 대한 이해도 up
1. 개발자의 업무 환경 이해
1. 컴퓨팅 사고력 up
1. 검색하고 질문하는 용기

### 💪 아쉬운 점

1. 누가 봐도 이해하기 쉬운 코드를 작성하는 것이 아직은 부족하다.
1. 리팩토링 한 코드를 보면 늘 `아... 이렇게 적을 걸` 이라는 아쉬움

### 🏆 앞으로의 다짐

1. 더 적극적으로 질문하고, 고민하기
1. 절대적인 코드 작성 시간 늘리기!

   - 홀로 앓는 시간을 줄이는 것

1. 기록과 회고를 통한 복습
   <img width="427" alt="스크린샷 2023-01-02 오전 11 09 22" src="https://user-images.githubusercontent.com/110847597/210249410-a8992621-ad6f-4bb7-a969-85217e67360f.png">

## <p align="center"> `Internship` 📆 1/2

## ✨ 메뉴탭 CSS 바꾸기

```jsx
className={classNames('tab-menu__link', {
          'tab-menu__link_active': type === 'retrainedModels',
        })}
```

### 📍 useEffect + state 업데이트

```jsx
useEffect(() => {
  if (createCount >= predictionKeepModel) {
    setPreDeleteCount(createCount - predictionKeepModel);
  }
}, [createCount, predictionKeepModel]);
//useEffect와 의존성 배열을 활용 한 ui 렌더

<input
  type='number'
  className='delQuality'
  placeholder={0}
  id='delQuality'
  step={1}
  min={0}
  max={createCount}
  value={retrainingKeepModel}
  onChange={e => setRetrainingKeepModel(Number(e.target.value))}
/>;
```

### 🍯 `Input`

- `step={1}`을 넣으면 1씩 커진다.
- `max={createCount}`
- input의 화살표를 계속 보여주는 방법은 `opacity: 1`

```jsx
input[type='number']::-webkit-inner-spin-button,
input[type='number']::-webkit-outer-spin-button {
    opacity: 1;
}
```

### 📝 조건부 렌더: scheduleType 타입에 따른

```jsx
//scheduleMethodTob.js
const scheduleType = scheduleDetails.type;

//index.js
{
  scheduleType && scheduleType.includes('prediction') ? (
    <div className='studio-container_auto_del'>
      <div className='title-wrap'>
        <span className='title-wrap-text'>Enable Prediction Auto-delete</span>
      </div>
      {predictionAutoDeletion && (
        <ScheduleAutoDeleteViewOption
          prediction={scheduleType.includes('prediction')}
          createCount={schedulingOptions.createCount}
          predictionKeepModel={predictionKeepModel}
          setPredictionKeepModel={setPredictionKeepModel}
        />
      )}
    </div>
  ) : (
    <></>
  );
}
```

### 📊 antd table CSS

```jsx
 {
    title: 'CREATED',
    dataIndex: 'created_at',
    key: 'created_at',
    render: text => getFormattedDateTimeTable(text),
    className: 'tag-columns-custom',
  }
```

### 🌳 성장 포인트 :

- 표 CSS를 커스텀 하는 도중, 오류를 만났다.
- 클래스네임을 공유하고 있어 전체 css에 적용이 되는 것.
- `row`를 수정하지 않고 `column`을 수정하는 방법으로 변경 후 성공!
- 라이브러리 명세를 확인하여 위의 코드 4번째 코드 `className:'tag-columns-custom'`로 작성하여 열을 수정 함!
  - `key`를 활용하여 date의 포맷 변환도 완료
  - 라이브러리는 어렵지만 또 쉽다. 🥲
- 검색과 질문도 코딩이다.
- 얼마 안남은 마무리와 `QA`를 잘 마무리 할 것

## <p align="center"> `Internship` 📆 1/3

### 🧑‍🚒 Hot Fix: MAX는 입력값과 6값 사이

```jsx
//Parent
const [retrainingKeepModel, setRetrainingKeepModel] = useState(1);
//child
const MAX_KEEP = 6;
const possibleMax = Math.min(MAX_KEEP, createCount);
//...
<input
  type='number'
  className='delQuality'
  placeholder={1}
  id='delQuality'
  step={1}
  min={1}
  max={possibleMax}
  value={retrainingKeepModel}
  onChange={e => setRetrainingKeepModel(Number(e.target.value))}
/>;
```

### `Math.min()` [MDN Math.min()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math/min)

```jsx
Math.min([value1[, value2[, ...]]])
```

> Math.min() 함수는 주어진 숫자들 중 가장 작은 값을 반환합니다.

### `yarn build`

> "yarn build Bundles the app into static files for production." from Create React App by MAD9135.
>
> > https://stackoverflow.com/questions/54693223/what-does-yarn-build-command-do-are-npm-build-and-yarn-build-similar

### 🌳 성장 포인트 :

- `아는 만큼 가독성이 좋아지는 코드`
  - 처음 위의 기능을 구현할 때 `if (가진값 <= 입력값) {...} if(가진값.정수가 아닐 때)` 등 복잡한 로직을 작성했다. (약 7줄)
  - 자연스럽게 while과 작동 시점에 대해서 고민이 깊어졌고, 간단한 수정사항이었는데 복잡하게 느껴졌다.
  - 하지만 Input의 `min`, `max`, `step`을 활용하여 코드는 더 간결해졌다.
  - 또한 `const possibleMax = Math.min(MAX_KEEP, createCount)` 코드를 작성하여 `정수가 아닐 때, 입력값이 가진 값 보다 클 때` 두 가지 조건을 한 줄로 해결하였다. (선언까지 3줄)
  - _Kepp It Simple, Stupid_ 을 기억하며 오늘도 열심히 공부를!

---

## <p align="center"> `Internship` 📝 `Retrospective`

### 4L: Liked, Learned, Lacked, Longed for

- 😍 좋았던 것(Liked)
  - 협업 코드를 직접 체험 해 본 것
  - 라이브러리를 사용 한 것
  - 통신을 통하여 배포까지 진행 한 것
- 📚 배운 것(Learned)
  - 리액트 학습
  - 실무의 통신(postman, 인터페이서 참고서, 기획서 활용)
    - 예를 들어, Back에게 전송해야 할 데이터가 `console.log`에 찍어서 보이지 않는다면, 프론트에서 제작하는 것이 아닌 요청이나 질문을 통하여 데이터 전송 방식을 논의해야함
- 💦 부족했던 것(Lacked)
  - 리액트 학습
  - 데이터 통신의 타이밍
- 🕯 바라는 것(Longed for)
  - 적극적으로 질문하고, 검색하는 과정에서 많이 배웠다. 이전에 했던 실수를 다시 하지 않도록 복습하고 더 노력하기!
  - 짧은 4주동안 잘 해주시고 많이 배울 수 있어 너무 감사했습니다. :) 개발짱이 되어 다시 만나요..

---

E.O.D
