tags:: course #programming #frontend-developer

- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: [Understanding TypeScript - 2022 Edition | Udemy](https://www.udemy.com/course/understanding-typescript/learn/lecture/17751414)
- Section 1 : Getting Started
	- What Is TypeScript & Why Should You Use It? #typescript/introduction
		- >[TypeScript: JavaScript With Syntax For Types. (typescriptlang.org)](https://www.typescriptlang.org/)
		- TypeScript 是 [JavaScript](https://zh.wikipedia.org/wiki/JavaScript) 的嚴格語法超集，提供了可選的靜態型別檢查，可以編譯成 JavaScript 執行於任何 JavaScript 環境上。
- Secton 2 : TypeScript Basis & Basic Types
	- Type Assignment & Type Inference #typescript/types
		- ```ts
		  // 多餘的 code , typescript 本身就會自行推斷 "name" 的型別
		  // 不需要指定 string 給它
		  const name:string = "name"
		  // 正確
		  const name = "name"
		  // 只有宣告變數未賦予值，才需要給予型別
		  let name2:string
		  name2="name"
		  ```
	- Object Types #typescript/types/object
		- ```ts
		  const person:{
		    name: string,
		    age:number
		  } = {
		    name: 'Name',
		    age:30
		  }
		  
		  // 巢狀結構
		  const product = {
		    id: 'abc1',
		    price: 12.99,
		    tags: ['great-offer', 'hot-and-new'],
		    details: {
		      title: 'Red Carpet',
		      description: 'A great carpet - almost brand-new!'
		    }
		  }
		  
		  
		  ```
		-
-
-
-