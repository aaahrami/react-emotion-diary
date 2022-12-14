<div><h2>π Emotion Diary Stacks</h2></div>
<div>
<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"> 
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> 
<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"> 
<img src="https://img.shields.io/badge/firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black">
</div>
<div>
<h5>λ°°ν¬ π https://aaahrami-emotion-diary.web.app/ </h5>
<h5>κ°μ π https://www.inflearn.com/course/%ED%95%9C%EC%9E%85-%EB%A6%AC%EC%95%A1%ED%8A%B8/dashboard </h5>
</div>

### 5-4. State (μν)

state β μλ κ° 

setState β λ³κ²½λ κ°μ μ μ₯ (μν λ³ν ν¨μ)

### 5-5. Props

μ»΄ν¬λνΈμ λ°μ΄ν°λ₯Ό μ λ¬νλ λ°©λ²

### 6-2. useRef

### 6-4. Listμ data μΆκ°νκΈ°

Reactλ λ¨λ°©ν₯ λ°μ΄ν° νλ¦μΌλ‘ κ°μ depth λΌλ¦¬μ data κ³΅μ κ° λΆκ°ν¨

β κ³΅ν΅ λΆλͺ¨μμμμ λ΄λ €μ€μΌ ν¨

β eventλ μ­λ°©ν₯ νλ¦

### 6-7. React Lifecycle μ μ΄νκΈ° (useEffect)
1. νμ : Mount (νλ©΄μ λνλλ κ²)
2. λ³ν : Update (μλ°μ΄νΈ, λ¦¬λ λ)
3. μ£½μ : UnMount (νλ©΄μμ μ¬λΌμ§)

### React developer tools

chrome νκ²½μμ react κ°λ° μ μ μ©ν κ°λ°μ λκ΅¬

[https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=ko](https://codesandbox.io/s/chapt-6-790r2)

### 6-10. μ΅μ ν 1 - μ°μ° κ²°κ³Ό μ¬μ¬μ©

- **Memoization**
    
    μ΄λ―Έ κ³μ° ν΄ λ³Έ μ°μ° κ²°κ³Όλ₯Ό κΈ°μ΅ ν΄ λμλ€κ°, 
    
    λμΌν κ³μ°μ μν€λ©΄ λ€μ μ°μ°νμ§ μκ³ , κΈ°μ΅ ν΄ λμλ λ°μ΄ν°λ₯Ό λ°ν μν€κ² νλ λ°©λ²
    
    λ§μΉ μνμ λ³Ό λ, μ΄λ―Έ νμ΄λ³Έ λ¬Έμ λ λ€μ νμ΄λ³΄μ§ μμλ λ΅μ μκ³  μλ κ²κ³Ό μ μ¬ν¨
    
    μ μΈ: **ν¨μλͺA = useMemo( ( ) β { ν¨μ }, [ ] )**
    
    μ¬μ©: **λ³μλͺA = ν¨μλͺA**
    
    ****** ν¨μAμ ν¨μλ₯Ό useMemo() μμ μ΅μ ν ν νμλ useMemo()κ° κ°μ λ¦¬ν΄νκ³ , 
    ν¨μAλ κ°λ§ λ¦¬ν΄ λ°κΈ° λλ¬Έμ ν¨μλͺAλ λμ΄μ ν¨μκ° μλλ€. 
    λ°λΌμ βν¨μλͺA()β λ‘ νΈμΆνλ κ²μ΄ μλλΌ βν¨μλͺAβ λ‘ νΈμΆν΄μΌ μ€λ₯κ° μκΈ°μ§ μλλ€.
    

### 6-11. μ΅μ ν 2 - μ»΄ν¬λνΈ μ¬μ¬μ©

- **React.memo()**
    
    [https://ko.reactjs.org/docs/react-api.html#reactmemo](https://ko.reactjs.org/docs/react-api.html#reactmemo)
    
    React.memoλ κ³ μ°¨ μ»΄ν¬λνΈμ΄λ€. 
    
    (κ³ μ°¨ μ»΄ν¬λνΈλ μ»΄ν¬λνΈλ₯Ό κ°μ Έμ μ μ»΄ν¬λνΈλ₯Ό λ°ννλ ν¨μμ΄λ€.)
    
    ```jsx
    // κ³ μ°¨ μ»΄ν¬λνΈ
    const EnhancedComponent = higherOrderComponent(WrappedComponent);
    
    // React.memo
    const MyComponent = React.memo(function MyComponent(props) {
      /* propsλ₯Ό μ¬μ©νμ¬ λ λλ§ */
    });
    
    // λμΌν κ°μ λΉκ΅νλ λμ (μμ λΉκ΅ XX)
    function MyComponent(props) {
      /* propsλ₯Ό μ¬μ©νμ¬ λ λλ§ */
    }
    function areEqual(prevProps, nextProps) {
      /*
      nextPropsκ° prevPropsμ λμΌν κ°μ κ°μ§λ©΄ trueλ₯Ό λ°ννκ³ , 
    	κ·Έλ μ§ μλ€λ©΄ falseλ₯Ό λ°ν
      */
    }
    export default React.memo(MyComponent, areEqual);
    ```
    

### 6-12. μ΅μ ν 3 - useCallback

- **useCallback()**
    
    [https://ko.reactjs.org/docs/hooks-reference.html#usecallback](https://ko.reactjs.org/docs/hooks-reference.html#usecallback)
    
    useCallback()μ λ©λͺ¨μ΄μ μ΄μ λ μ½λ°±μ λ°ννλ€.
    

```jsx
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);
```

### 6-14. λ³΅μ‘ν μνλ³ν λ‘μ§ λΆλ¦¬

- **useReducer()**
    
    [https://ko.reactjs.org/docs/hooks-reference.html#usereducer](https://ko.reactjs.org/docs/hooks-reference.html#usereducer)
    
    dispatch μ¬μ© β dependency array μ κ²½ μμ¨λ λ (μμ‘΄μ± λ°°μ΄)
    

### 6-15. μ»΄ν¬λνΈ νΈλ¦¬μ λ°μ΄ν° κ³΅κΈ

- **Context API**
    
    Context.Providerμ μ¬μ©νμ¬ props drillingμ ν΄μ

### 7-1. Page Routing

- **Routing**
    
    μ΄λ€ λ€νΈμν¬ λ΄μμ ν΅μ  λ°μ΄ν°λ₯Ό λ³΄λΌ κ²°λ‘λ₯Ό μ ννλ μΌλ ¨μ κ³Όμ 
    
    Router : λ°μ΄ν°μ κ²½λ‘λ₯Ό μ€μκ°μΌλ‘ μ§μ ν΄μ£Όλ μ­ν μ νλ λ¬΄μΈκ°
    
    β Route + ing : κ²½λ‘λ₯Ό μ ν΄μ£Όλ νμ μμ²΄μ κ·Έλ° κ³Όμ λ€μ λ€ ν¬ν¨νμ¬ μΌμ»«λ λ§

### 7-2. νμ΄μ§ λΌμ°ν

[https://reactrouter.com/en/main](https://reactrouter.com/en/main)

```jsx
npm install react-router-dom@6
```

- React Router Domμ μ μ©ν κΈ°λ₯
    
    REACT ROUTER V6
    
    : REACTμμ CSRκΈ°λ°μ νμ΄μ§ λΌμ°νμ ν  μ μκ² ν΄μ£Όλ λΌμ΄λΈλ¬λ¦¬
    
    1. **Path Variable**
        
        useParams
        
    2. **Query String**
        
        useSearchParams
        
        nameκ³Ό valueλ₯Ό μμ΄μ μ μ‘ / μΉ νμ΄μ§μ λ°μ΄ν°λ₯Ό μ λ¬νλ κ°μ₯ κ°λ¨ν λ°©λ²
        
        (μμβ) /edit?id=10&mode=dark
        
    3. **Page Moving**
        
        useNavigate
        

### 7. Emotion-Diary μ€μ΅ μ½λ μμ±

[https://github.com/aaahrami/react-emotion-diary](https://github.com/aaahrami/react-emotion-diary)

### 7-10. Web Storage API

Web Stirage APIλ λΈλΌμ°μ μμ ν€/κ° μμ μΏ ν€λ³΄λ€ ν¨μ¬ μ§κ΄μ μΌλ‘ μ μ₯ν  μ μλ λ°©λ²μ μ κ³΅νλ€. ( μ°Έκ³ λ¬Έμ : [https://developer.mozilla.org/ko/docs/Web/API/Web_Storage_API](https://developer.mozilla.org/ko/docs/Web/API/Web_Storage_API) )

- **sessionStorage**
    
    κ°κ°μ μΆμ²μ λν΄ λλ¦½μ μΈ μ μ₯ κ³΅κ°μ νμ΄μ§ μΈμμ΄ μ μ§λλ λμ(λΈλΌμ°μ κ° μ΄λ €μλ λμ) μ κ³΅νλ€.
    
    - μΈμμ νμ ν΄, μ¦ λΈλΌμ°μ  λλ ν­μ΄ λ«ν λκΉμ§λ§ λ°μ΄ν°λ₯Ό μ μ₯νλ€.
    - λ°μ΄ν°λ₯Ό μ λ μλ²λ‘ μ μ‘νμ§ μλλ€.
    - μ μ₯ κ³΅κ°μ΄ μΏ ν€λ³΄λ€ ν¬λ€. (μ΅λ5MB)
- **localStorage**
    
    sessionStorageμ κ°μ§λ§ λΈλΌμ°μ λ₯Ό λ«μλ€ μ΄μ΄λ λ°μ΄ν°κ° λ¨μμλ€.
    
    - μ ν¨κΈ°κ° μμ΄ λ°μ΄ν°λ₯Ό μ μ₯νκ³ , JavaScriptλ₯Ό μ¬μ©νκ±°λ λΈλΌμ°μ  μΊμ λλ λ‘μ»¬ μ μ₯ λ°μ΄ν°λ₯Ό μ§μμΌλ§ μ¬λΌμ§λ€.
    - μ μ₯ κ³΅κ°μ΄ μΏ ν€, sessionStorage λ³΄λ€ ν¬λ€.
    - localStorageμ μ μ₯λ  λμλ string νμμΌλ‘ μ μ₯μ΄ λ¨ β μ«μ κΊΌλ΄μ¬ κ²½μ°μ parseInt() μ¬μ© / κ°μ²΄λ₯Ό κΊΌλ΄μ¬ κ²½μ°μλ JSON.parse()
    

### 7-13. λ°°ν¬νκΈ°

**firebase** μ΄μ©νμ¬ λ°°ν¬νκΈ° !

**λ°°ν¬ μλ£** π [https://aaahrami-emotion-diary.web.app](https://aaahrami-emotion-diary.web.app/)
