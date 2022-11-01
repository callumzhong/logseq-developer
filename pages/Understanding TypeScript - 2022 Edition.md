tags:: course #programming #frontend-developer

- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: [Understanding TypeScript - 2022 Edition | Udemy](https://www.udemy.com/course/understanding-typescript/learn/lecture/17751414)
- Section 1 : Getting Started
	- What Is TypeScript & Why Should You Use It? #typescript/introduction
		- >[TypeScript: JavaScript With Syntax For Types. (typescriptlang.org)](https://www.typescriptlang.org/)
		- TypeScript 是 [JavaScript](https://zh.wikipedia.org/wiki/JavaScript) 的嚴格語法超集，提供了可選的靜態型別檢查，可以編譯成 JavaScript 執行於任何 JavaScript 環境上。
- Secton 2 : TypeScript Basis & Basic Types
	- Working with Numbers, String & Booleans
		- ```ts
		  function add(n1:number,n2:number,showResult:boolean,phrase:string){
		   const result = n1+n2
		    if(showResult){
		      console.log(phrase + result)
		    }else {
		        return n1+n2
		    }
		  }
		  
		  const number1 = 5; // number type
		  const number2 = 2.8 // number type (沒有 float 型別)
		  const printResult = true
		  const phrase = "phrase is: "
		  ```
	- Type Assignment & Type Inference
		- ```ts
		  let isDone: boolean
		  isDone = "true" // ❌
		  isDone = true // ✅
		  
		  let isDone2: boolean = false // ❌
		  let isDone2 = false // ✅ typescript 推斷型別 boolean
		  ```
		  #typescript/types/declarations
	- Object Types
		- ```ts
		  const person:{
		    name: string,
		    age:number
		  }
		  ```
		  #typescript/types/basic
		-
	- Arrays Types
		- ```ts
		  const type = {
		    arr:string[],// [stirng,string]
		    arr2:[string,nubmer], // [string,number]
		    arr3:(string | number)[] // [5, "string", 5];
		  }
		  ```
		  #typescript/types/basic
	- Working with Enums #typescript/types/enums
		- 列舉是 TypeScript 提供的類型
		- ```ts
		  // TypeScript
		  enum Role {
		    ADMIN = "ADMIN",
		    READ_ONLY = 100,
		    AUTHOR = "AUTHOR",
		  }
		  
		  const person = {
		    name: "Maximilian",
		    age: 30,
		    hobbies: ["Sports", "Cooking"],
		    role: Role.ADMIN,
		  };
		  ```
		- ```js
		  // JavaScript
		  var Role;
		  (function (Role) {
		      Role["ADMIN"] = "ADMIN";
		      Role[Role["READ_ONLY"] = 100] = "READ_ONLY";
		      Role["AUTHOR"] = "AUTHOR";
		  })(Role || (Role = {}));
		  
		  var person = {
		      name: "Maximilian",
		      age: 30,
		      hobbies: ["Sports", "Cooking"],
		      role: Role.ADMIN
		  };
		  
		  ```
	- Type Aliases & Object Types #typescript/types/basic
		- type 是 typescript 提供的型別
		- ```ts
		  type User = { name: string; age: number };
		  const u1: User = { name: 'Name', age: 30 }; // this works!
		  ```
	- Function Return Types & "void" #typescript/types/function
		- ==void== 表示不返回值的函數
		- ```ts
		  function add(n1: number, n2: number): void {
		    console.log(n1 + n2);
		  }
		  // 實際上 add 去檢視 return 會得到 undefined
		  console.log(add(5,6)) 
		  
		  // 但以下是有錯誤的
		  // typescript 會認為有 return;
		  function add(n1: number, n2: number): undefined {
		    console.log(n1 + n2);
		  }
		  
		  // 正確 (但是通常會直接使用 void 因為沒有 return 值)
		  function add(n1: number, n2: number): undefined {
		    console.log(n1 + n2);
		    return;
		  }
		  
		  ```
	- Function Types & Callbacks #typescript/types/function
		- 如果  callback return 值需要被忽略請使用 ==void== 可以防止意外使用到 return 值
		- ```ts
		  function sendRequest(data: string, cb: (response: any) => void) {
		    // ... sending a request with "data"
		    return cb({ data: "Hi there!" });
		  }
		  
		  // value 推斷類型為 void
		  const value = sendRequest("Send this!", (response) => {
		    console.log(response);
		    return true
		  });
		  
		  // 實際上 value 是 boolean 類型，但 typescript 會推斷為 void
		  // error: 類型 'void' 沒有屬性 'name'
		  value.name()
		  // error: 因為類型 'void' 與 'boolean' 未重疊，所以此條件永遠會傳回 'false'
		  console.log(value === true)
		  ```
		- >💡 注意
		  不是強制你傳入不回傳任何值的 function，只是告知不會將回傳值做任何使用。
	- The "unknown" Type #typescript/types/basic
		- unknow 表示任何值但比 any 更嚴謹的類型
		- ```ts
		  let userInputByKnown:unknown;
		  let userInputByAny:any;
		  let userName:string;
		  
		  userInputByKnown = "name";
		  userInputByAny = 'name'
		  // ERROR: 類型 'unknown' 不可指派給類型 'string'
		  userName = userInputByKnown;
		  
		  // 透過檢查式確定是 string
		  if(typeof userInputByKnown === 'string'){
		    // PASS
		    userName = userInputByKnown;
		  }
		  // PASS
		  userName = userInputByAny
		  ```
		- any 可以未經檢查賦予其他變數
		- unknow 則不行
	- The "never" Type #typescript/types/basic
		- 表示 function 永遠不會返回值，通常用於拋出 throw 或者終止整個 JavaScript 程序
		- ```ts
		  function fail(msg: string): never {
		    throw new Error(msg);
		  }
		  
		  ```
-