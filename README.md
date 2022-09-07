<div><h2>📚 Emotion Diary Stacks</h2></div>
<div>
<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"> 
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> 
<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"> 
<img src="https://img.shields.io/badge/firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black">
</div>
<div>
<h5>배포 😎 https://aaahrami-emotion-diary.web.app/ </h5>
<h5>강의 🔗 https://www.inflearn.com/course/%ED%95%9C%EC%9E%85-%EB%A6%AC%EC%95%A1%ED%8A%B8/dashboard </h5>
</div>

### 5-4. State (상태)

state → 원래 값 

setState → 변경된 값을 저장 (상태 변화 함수)

### 5-5. Props

컴포넌트에 데이터를 전달하는 방법

### 6-2. useRef

### 6-4. List에 data 추가하기

React는 단방향 데이터 흐름으로 같은 depth 끼리의 data 공유가 불가함

→ 공통 부모요소에서 내려줘야 함

→ event는 역방향 흐름

### 6-7. React Lifecycle 제어하기 (useEffect)
1. 탄생 : Mount (화면에 나타나는 것)
2. 변화 : Update (업데이트, 리렌더)
3. 죽음 : UnMount (화면에서 사라짐)

### React developer tools

chrome 환경에서 react 개발 시 유용한 개발자 도구

[https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=ko](https://codesandbox.io/s/chapt-6-790r2)

### 6-10. 최적화 1 - 연산 결과 재사용

- **Memoization**
    
    이미 계산 해 본 연산 결과를 기억 해 두었다가, 
    
    동일한 계산을 시키면 다시 연산하지 않고, 기억 해 두었던 데이터를 반환 시키게 하는 방법
    
    마치 시험을 볼 때, 이미 풀어본 문제는 다시 풀어보지 않아도 답을 알고 있는 것과 유사함
    
    선언: **함수명A = useMemo( ( ) ⇒ { 함수 }, [ ] )**
    
    사용: **변수명A = 함수명A**
    
    ****** 함수A의 함수를 useMemo() 안에 최적화 한 후에는 useMemo()가 값을 리턴하고, 
    함수A는 값만 리턴 받기 때문에 함수명A는 더이상 함수가 아니다. 
    따라서 “함수명A()” 로 호출하는 것이 아니라 “함수명A” 로 호출해야 오류가 생기지 않는다.
    

### 6-11. 최적화 2 - 컴포넌트 재사용

- **React.memo()**
    
    [https://ko.reactjs.org/docs/react-api.html#reactmemo](https://ko.reactjs.org/docs/react-api.html#reactmemo)
    
    React.memo는 고차 컴포넌트이다. 
    
    (고차 컴포넌트란 컴포넌트를 가져와 새 컴포넌트를 반환하는 함수이다.)
    
    ```jsx
    // 고차 컴포넌트
    const EnhancedComponent = higherOrderComponent(WrappedComponent);
    
    // React.memo
    const MyComponent = React.memo(function MyComponent(props) {
      /* props를 사용하여 렌더링 */
    });
    
    // 동일한 값을 비교하는 동작 (얕은 비교 XX)
    function MyComponent(props) {
      /* props를 사용하여 렌더링 */
    }
    function areEqual(prevProps, nextProps) {
      /*
      nextProps가 prevProps와 동일한 값을 가지면 true를 반환하고, 
    	그렇지 않다면 false를 반환
      */
    }
    export default React.memo(MyComponent, areEqual);
    ```
    

### 6-12. 최적화 3 - useCallback

- **useCallback()**
    
    [https://ko.reactjs.org/docs/hooks-reference.html#usecallback](https://ko.reactjs.org/docs/hooks-reference.html#usecallback)
    
    useCallback()은 메모이제이션 된 콜백을 반환한다.
    

```jsx
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```

### 6-14. 복잡한 상태변화 로직 분리

- **useReducer()**
    
    [https://ko.reactjs.org/docs/hooks-reference.html#usereducer](https://ko.reactjs.org/docs/hooks-reference.html#usereducer)
    
    dispatch 사용 → dependency array 신경 안써도 됌 (의존성 배열)
    

### 6-15. 컴포넌트 트리에 데이터 공급

- **Context API**
    
    Context.Provider을 사용하여 props drilling을 해소

### 7-1. Page Routing

- **Routing**
    
    어떤 네트워크 내에서 통신 데이터를 보낼 결로를 선택하는 일련의 과정
    
    Router : 데이터의 경로를 실시간으로 지정해주는 역할을 하는 무언가
    
    ⇒ Route + ing : 경로를 정해주는 행위 자체와 그런 과정들을 다 포함하여 일컫는 말

### 7-2. 페이지 라우팅

[https://reactrouter.com/en/main](https://reactrouter.com/en/main)

```jsx
npm install react-router-dom@6
```

- React Router Dom의 유용한 기능
    
    REACT ROUTER V6
    
    : REACT에서 CSR기반의 페이지 라우팅을 할 수 있게 해주는 라이브러리
    
    1. **Path Variable**
        
        useParams
        
    2. **Query String**
        
        useSearchParams
        
        name과 value를 섞어서 전송 / 웹 페이지에 데이터를 전달하는 가장 간단한 방법
        
        (예시→) /edit?id=10&mode=dark
        
    3. **Page Moving**
        
        useNavigate
        

### 7. Emotion-Diary 실습 코드 작성

[https://github.com/aaahrami/react-emotion-diary](https://github.com/aaahrami/react-emotion-diary)

### 7-10. Web Storage API

Web Stirage API는 브라우저에서 키/값 쌍을 쿠키보다 훨씬 직관적으로 저장할 수 있는 방법을 제공한다. ( 참고문서 : [https://developer.mozilla.org/ko/docs/Web/API/Web_Storage_API](https://developer.mozilla.org/ko/docs/Web/API/Web_Storage_API) )

- **sessionStorage**
    
    각각의 출처에 대해 독립적인 저장 공간을 페이지 세션이 유지되는 동안(브라우저가 열려있는 동안) 제공한다.
    
    - 세션에 한정해, 즉 브라우저 또는 탭이 닫힐 때까지만 데이터를 저장한다.
    - 데이터를 절대 서버로 전송하지 않는다.
    - 저장 공간이 쿠키보다 크다. (최대5MB)
- **localStorage**
    
    sessionStorage와 같지만 브라우저를 닫았다 열어도 데이터가 남아있다.
    
    - 유효기간 없이 데이터를 저장하고, JavaScript를 사용하거나 브라우저 캐시 또는 로컬 저장 데이터를 지워야만 사라진다.
    - 저장 공간이 쿠키, sessionStorage 보다 크다.
    - localStorage에 저장될 때에는 string 형식으로 저장이 됨 → 숫자 꺼내올 경우에 parseInt() 사용 / 객체를 꺼내올 경우에는 JSON.parse()
    

### 7-13. 배포하기

**firebase** 이용하여 배포하기 !

**배포 완료** 🙂 [https://aaahrami-emotion-diary.web.app](https://aaahrami-emotion-diary.web.app/)
