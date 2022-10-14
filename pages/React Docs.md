- ## 簡介
	- 每一件工具總有能解決的問題，則 React 解決什麼問題呢 ?
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
- ## React 思考
	- 前提摘要我們得知 React 使用宣告式設計 view ，這將改變你對設計應用程式的看法
	- ![image.png](../assets/image_1665712240492_0.png)
	- 框線表示 HTML TAG ，具體表達出層級結構。以卡片為例設計 view 可變成 Card Header, Card Body Card Footer，也可以稱為 Product。
	- 分解層級結構的過程中，會以單一職責、一個 view 做一件事為準則