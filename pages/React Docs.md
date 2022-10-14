- ## React 思考
	- 前提摘要我們得知 React 使用宣告式設計 view ，這將改變你對設計應用程式的看法
	- ![image.png](../assets/image_1665712240492_0.png)
	- 框線表示 HTML TAG ，具體表達出層級結構。以卡片為例設計 view 可變成 Card Header, Card Body Card Footer，也可以稱為 Product，其分解層級結構的過程中，會以單一職責為準則不混雜處理多個畫面結構與邏輯。
	  
	  >延伸知識 💡
	  建議閱讀官方介紹 - [Thinking in React (reactjs.org)](https://beta.reactjs.org/learn/thinking-in-react#step-3-find-the-minimal-but-complete-representation-of-ui-state)
- ## JSX 介紹
  collapsed:: true
	- React 使用 JavaScript XML，是一種使用類似 XML/HTML 的語法， 它支援 ECMAScript，讓 XML/HTML 文本可以與 JavaScript / React 代碼共存，簡稱 JSX
	- ```js
	  const element = <h1>Hello World</h1>
	  ```
	- 宣告變數的標籤語法就是 JSX，回傳 React Elemnet
	- 元素內可以崁入 Expression
	- ```js
	  const name = 'Josh Perez';
	  const element = <h1>Hello, {name}</h1>;
	  ```
	- HTML Tag 使用屬性純字串或變數
	  ```js
	  // 字串
	  const element = <a href="https://www.reactjs.org"> link </a>;
	  // 或者是 Expression
	  const element = <img src={user.avatarUrl}></img>;
	  ```
	- 與 XML 標籤相似，當標籤是空白允許使用 /> 關閉標籤
	  
	  ```
	  const element = <img src={user.avatarUrl} />;
	  ```
	- JSX 標籤多個 children
	  
	  ```js
	  const element = (
	    <div>
	      <h1>Hello!</h1>
	      <h2>Good to see you here.</h2>
	    </div>
	  );
	  ```
	- 深入了解
	- JSX 透過 Babel 編譯後會是呼叫 React.createElement() 去建立 XML 標籤
	  
	  ```js
	  const element = <h1 className="greeting">Hello, World!</h1>
	  ```
	  
	  ```js
	  const element = React.createElement('h1',{className: 'greeting'},'Hello, World!');
	  ```
	- 查看 build 後的程式碼
	  
	  ```js
	  function App() {
	    return (
	      <div>
	        <h2>Let's get started!</h2>
	        <ExpenseItem></ExpenseItem>
	      </div>
	    );
	  }
	  ```
	  
	  ```js
	  function App() {
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
	- 經編譯後是呼叫一個 function 與 React.createElement 傳的參數一致，React.createElement() 會檢查寫法是否有 BUG
	- 執行後會產生物件
	  
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