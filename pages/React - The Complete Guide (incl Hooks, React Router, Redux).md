- > Author(s): [[Maximilian Schwarzmiiller]]
  > Url: https://www.udemy.com/course/react-the-complete-guide-incl-redux/learn/lecture/25599264
  > Source Code: https://github.com/academind/react-complete-guide-code
  > tags:: #course #programming #[[frontend development]]
- Section 2 : JavaScript Refrescher
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
		- 注意陣列與物件是參考記憶體位址
	- Refreshing Array Functions #javascript/syntax/function
		- map 運用
- Section 3 : React Basics & Working With Components
	- What Are Component? And Why Is React All About Them? #react/introduction
		- React 用於構建使用者介面，以 UI 設計來說通常具有數個相同結構的視覺模型，需要進行分解其名詞稱為 Component。
		- 更多介紹 : https://beta.reactjs.org/learn/thinking-in-react
	- React Code Is Written In A "Declarative Way"! #react/introduction
		-
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
		- 需求：
			- 某數字需要被使用者手動增加
		- 實作：
			- HTML Tag 建立
			- HTML 掛載
			- 狀態更新, 畫面更新
		- 缺點：
			- 當畫面複雜度增加、商業邏輯增加會過於疲累
			- 命令式：告知細節得到結果
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
		- 需求：
			- 某數字需要被使用者手動增加
		- 實作：
			- React 為需求設計 view
			- 狀態更新
		- 優點：
			- 不需要寫 querySelector ,  createElement, append
			- 不需要寫畫面更新，狀態更新即畫面更新
			- 宣告式：設計 view 結果由 React 幕後處理細節
-