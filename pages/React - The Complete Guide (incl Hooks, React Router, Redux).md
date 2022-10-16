- > Author(s): [[Maximilian Schwarzmiiller]]
  > Url: https://www.udemy.com/course/react-the-complete-guide-incl-redux/learn/lecture/25599264
  > Source Code: https://github.com/academind/react-complete-guide-code
  > tags:: #course #programming #[[frontend development]]
- Section 2 : JavaScript Refrescher
  collapsed:: true
	- Understanding "let" and "const" #javascript/variables
		- ```js
		  const test = 'A';
		  ```
	- Arrow Functions 箭頭函式 #javascript/syntax/function
	- Exports and Imports #javascript/module
	- Understanding Classes #javascript/class
	- Classes, Properties and Methods #javascript/class
	- The Spread & Rest Operator #javascript/syntax
	- Destructuring #javascript/syntax
	- Reference and Primitive Types Refresher #javascript/types
		- 注意陣列與物件是參考記憶體位址
	- Refreshing Array Functions #javascript/syntax/function
		- map 運用
- Section 3 : React Basics & Working With Components
	- What Are Component? And Why Is React All About Them? #react/introduction
		- React 用於構建使用者介面，以 UI 設計來說通常具有數個相同結構的視覺模型，需要進行分解撰寫可重複使用的代碼，其名稱為 Component
		- >延伸閱讀 💡
		  [用 React 思考 – React (reactjs.org)](https://zh-hant.reactjs.org/docs/thinking-in-react.html)
		  [React 術語表 – React (reactjs.org)](https://zh-hant.reactjs.org/docs/glossary.html#components)
	- React Code Is Written In A "Declarative Way"! #react/introduction
		- 假設功能需求某數字需要被使用者手動增加
		- ```js
		  var root = document.querySelector("#root");
		  var button = document.createElement("button")
		  var p = document.createElement("p");
		  var amount = 0 
		  
		  p.textContent = amount;
		  button.textContent = "+";
		  root.append(p);
		  root.append(button)
		  
		  function  clickHandler(e){
		    amount +=1
		    p.textContent=amount
		  }
		  
		  button.addEventListener('click', clickHandler)
		  ```
		- 取得 ROOT DOM
		- 建立 DOM
		- 添加 Content
		- 添加事件監聽
			- 當使用者點擊後更新
		- 掛載 DOM
		- 上述操作稱為指令式程式設計(Imperative Programming) 告知細節得到結果
		- ```js
		  function App() {
		    const [count, setCount] = useState(0);
		    const clickHandler = () => {
		      setCount((prevState) => prevState + 1);
		    };
		    return (
		      <div className="App">
		        <p>{count}</p>
		        <button onClick={clickHandler}>+</button>
		      </div>
		    );
		  }
		  ```
		- 設計 view 結果
		- 添加事件監聽
		- 上述稱為宣告式程式設計，告知結果細節由封裝好的 React 處理
	- Creating a new React Project #react/install
	  collapsed:: true
		- CSR
			- [create-react-app-github](https://github.com/facebook/create-react-app)
		- 混合(SSG and SSR)
			- [Nextjs](https://nextjs.org/)
		- 靜態專案
			- [Gatsby](https://www.gatsbyjs.com/)
			- [docusaurus](https://docusaurus.io/)
				- [與其他工具比較介紹](https://docusaurus.io/zh-CN/docs#comparison-with-other-tools)
		- CDN 方式載入 HTML
			- [官方介紹文件](https://reactjs.org/docs/add-react-to-a-website.html)
		- 線上編譯 Coding 工具
			- [CodePen](https://codepen.io/pen?&editable=true&editors=0010)
			- [CodeSandbox](https://codesandbox.io/s/new)
			- [Glitch](https://glitch.com/edit/#!/remix/starter-react-template)
			- [Stackblitz](https://stackblitz.com/edit/react-jpp86w)
		- reference
			- https://zh-hant.reactjs.org/docs/create-a-new-react-app.html
	- Analyzing a Standard React Project #react/install
	  collapsed:: true
		- 透過 CLI 建立專案
		- ```
		   npx create-react-app my-app
		  ```
		- ![image.png](../assets/image_1665889988364_0.png)
		- react 定義 component 所需要的功能
		- react-dom 定義 DOM 與 server 渲染
		- react-scripts 定義 scripts & configuration 配置
	- Introducing JSX #react/syntax/jsx
		- JavaScript XML 使用類似 XML/HTML 的語法， 它支援 ECMAScript，讓 XML/HTML 文本可以與 JavaScript / React 代碼共存，簡稱 JSX
		- ```js
		  const element = <h1>Hello World</h1>
		  ```
		- 宣告變數的標籤語法就是 JSX，回傳 React Elemnet
		- ```js
		  const name = 'Josh Perez';
		  const element = <h1>Hello, {name}</h1>;
		  ```
		- >💡 通常 element 不會被直接使用，而是在 component 中被返回
		- 元素內可以崁入 Expression
		- ```js
		  // 字串
		  const element = <a href="https://www.reactjs.org"> link </a>;
		  // 或者是 Expression
		  const element = <img src={user.avatarUrl}></img>;
		  ```
		- HTML Tag 使用屬性純字串或變數
		- ```
		  const element = <img src={user.avatarUrl} />;
		  ```
		- 與 XML 標籤相似，當標籤是空白允許使用 /> 關閉標籤
		- ```js
		  const element = (
		    <div>
		      <h1>Hello!</h1>
		      <h2>Good to see you here.</h2>
		    </div>
		  );
		  ```
		- JSX 標籤多個 children
		- ```js
		  const element = <h1 className="greeting">Hello, World!</h1>
		  const element2 = React.createElement('h1',{className: 'greeting'},'Hello, World!');
		  ```
		- JSX 透過 Babel 編譯後會是呼叫 React.createElement() 去建立 XML 標籤
		- ```js
		  function App() {
		    return (
		      <div>
		        <h2>Let's get started!</h2>
		        <ExpenseItem></ExpenseItem>
		      </div>
		    );
		  }
		  
		  function App2() {
		    return */*#__PURE__*/*Object(react_jsx_dev_runtime__WEBPACK_IMPORTED_MODULE_1__["jsxDEV"])("div", {
		      children: [*/*#__PURE__*/*Object(react_jsx_dev_runtime__WEBPACK_IMPORTED_MODULE_1__["jsxDEV"])("h2", {
		        children: "Let's get started!"
		      }, void 0, false, {
		        fileName: _jsxFileName,
		        lineNumber: 6,
		        columnNumber: 7
		      }, this), */*#__PURE__*/*Object(react_jsx_dev_runtime__WEBPACK_IMPORTED_MODULE_1__["jsxDEV"])(_components_ExpenseItem__WEBPACK_IMPORTED_MODULE_0__["default"], {}, void 0, false, {
		        fileName: _jsxFileName,
		        lineNumber: 7,
		        columnNumber: 7
		      }, this)]
		    }, void 0, true, {
		      fileName: _jsxFileName,
		      lineNumber: 5,
		      columnNumber: 5
		    }, this);
		  }
		  ```
		- 查看 build 後的程式碼
		- 經編譯後是呼叫一個 function 與 React.createElement 傳的參數一致，React.createElement() 會檢查寫法是否有 BUG
		- ```js
		  // 注意：這是簡化過的結構 (模擬 DOM 樹狀結構)
		    const element = {
		      type: 'h1',
		      props: {
		        className: 'greeting',
		        children: 'Hello, world!'
		      }
		    };
		  ```
		- 執行後會產生物件
	- How React Works #react/introduction
	- Building a First Custom Component #react/component
		- Component 返回一個被 render 在頁面的 React element
		- ```js
		  // Function
		  function Welcome() {
		    return <h1>Hello</h1>;
		  }
		  
		  // ES6 Class
		  class Welcome extends React.Component {
		    render() {
		      return <h1>Hello, {this.props.name}</h1>;
		    }
		  }
		  ```
		- 命名規範
		- ```
		  /components/ExpenseItem.jsx
		  ```
		- Component 會返回 React element 所以可以被其他 Component 引用
		- ```jsx
		  <Todo></Todo>
		  ```
			- 小寫開頭是原生 XML
			- 大寫開頭是自定義的 React Component
	- Writing More Complex JSX Code #react/syntax/jsx
		- JSX 透過 執行 React.createElement()
	-
-