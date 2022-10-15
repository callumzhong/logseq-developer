- > Author(s): [[Maximilian Schwarzmiiller]]
  > Url: https://www.udemy.com/course/react-the-complete-guide-incl-redux/learn/lecture/25599264
  > Source Code: https://github.com/academind/react-complete-guide-code
  > tags:: #course #programming #[[frontend development]]
- Section 2 : JavaScript Refrescher
  collapsed:: true
	- Understanding "let" and "const" #javascript/variables
	  collapsed:: true
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
	  collapsed:: true
		- 注意陣列與物件是參考記憶體位址
	- Refreshing Array Functions #javascript/syntax/function
	  collapsed:: true
		- map 運用
- Section 3 : React Basics & Working With Components
	- What Are Component? And Why Is React All About Them? #react/introduction
	  collapsed:: true
		- React 用於構建使用者介面，以 UI 設計來說通常具有數個相同結構的視覺模型，需要進行分解其名詞稱為 Component。
		- 更多介紹 : https://beta.reactjs.org/learn/thinking-in-react
	- React Code Is Written In A "Declarative Way"! #react/introduction
	  collapsed:: true
		- collapsed:: true
		  ```js
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
			- 需求：
			  collapsed:: true
				- 某數字需要被使用者手動增加
			- 實作：
			  collapsed:: true
				- HTML Tag 建立
				- HTML 掛載
				- 狀態更新, 畫面更新
			- 缺點：
			  collapsed:: true
				- 當畫面複雜度增加、商業邏輯增加會過於疲累
				- 命令式：告知細節得到結果
		- collapsed:: true
		  ```js
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
			- 需求：
			  collapsed:: true
				- 某數字需要被使用者手動增加
			- 實作：
			  collapsed:: true
				- React 為需求設計 view
				- 狀態更新
			- 優點：
			  collapsed:: true
				- 不需要寫 querySelector ,  createElement, append
				- 不需要寫畫面更新，狀態更新即畫面更新
				- 宣告式：設計 view 結果由 React 幕後處理細節
	- Introducing JSX #react/syntax/jsx
	  collapsed:: true
		- JavaScript XML 使用類似 XML/HTML 的語法， 它支援 ECMAScript，讓 XML/HTML 文本可以與 JavaScript / React 代碼共存，簡稱 JSX
		- collapsed:: true
		  ```js
		  const element = <h1>Hello World</h1>
		  ```
			- 宣告變數的標籤語法就是 JSX，回傳 React Elemnet
		- collapsed:: true
		  ```js
		  const name = 'Josh Perez';
		  const element = <h1>Hello, {name}</h1>;
		  ```
			- 元素內可以崁入 Expression
		- collapsed:: true
		  ```js
		  // 字串
		  const element = <a href="https://www.reactjs.org"> link </a>;
		  // 或者是 Expression
		  const element = <img src={user.avatarUrl}></img>;
		  ```
			- HTML Tag 使用屬性純字串或變數
		- collapsed:: true
		  ```
		  const element = <img src={user.avatarUrl} />;
		  ```
			- 與 XML 標籤相似，當標籤是空白允許使用 /> 關閉標籤
		- collapsed:: true
		  ```js
		  const element = (
		    <div>
		      <h1>Hello!</h1>
		      <h2>Good to see you here.</h2>
		    </div>
		  );
		  ```
			- JSX 標籤多個 children
		- collapsed:: true
		  ```js
		  const element = <h1 className="greeting">Hello, World!</h1>
		  const element2 = React.createElement('h1',{className: 'greeting'},'Hello, World!');
		  ```
			- JSX 透過 Babel 編譯後會是呼叫 React.createElement() 去建立 XML 標籤
		- collapsed:: true
		  ```js
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
		- collapsed:: true
		  ```js
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
	  collapsed:: true
		-
	-
	-
	-
-