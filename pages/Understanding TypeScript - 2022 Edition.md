tags:: course #programming #frontend-developer

- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: [Understanding TypeScript - 2022 Edition | Udemy](https://www.udemy.com/course/understanding-typescript/learn/lecture/17751414)
- Section 1 : Getting Started
  collapsed:: true
	- What Is TypeScript & Why Should You Use It? #typescript/introduction
		- >[TypeScript: JavaScript With Syntax For Types. (typescriptlang.org)](https://www.typescriptlang.org/)
		- TypeScript 是 [JavaScript](https://zh.wikipedia.org/wiki/JavaScript) 的嚴格語法超集，提供了可選的靜態型別檢查，可以編譯成 JavaScript 執行於任何 JavaScript 環境上。
- Secton 2 : TypeScript Basis & Basic Types
	- Type Assignment & Type Inference #typescript/types/string #typescript/types/number
	  collapsed:: true
		- ```ts
		  // typescript 本身就會自行推斷 "name" 的型別 (稱為靜態類型系統)
		  const name="name"
		  
		  // 指定類型給它稱為顯示類型，這點不需要
		  const name:string = "name"
		  
		  // Error : 類型 'string' 不可指派給類型 'number'
		  const name2:number = 'name'
		  
		  // 只有宣告變數未賦予值時，才需要顯示類型
		  let name2:string
		  name2="name"
		  ```
	- Object Types #typescript/types/object
	  collapsed:: true
		- ```ts
		  // Object 使用方式 (較少) 常使用 interface (整理至 /types 資料夾)
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
		  
		  const product: {
		    id: string;
		    price: number;
		    tags: string[];
		    details: {
		      title: string;
		      description: string;
		    }
		  }
		  ```
		-
	- Arrays Types #typescript/types/array
	  collapsed:: true
		- ```ts
		  const type = {
		    arr:string[],// [stirng,string]
		    arr2:[string,nubmer], // [string,number]
		    arr3:(string | number)[] // [5, "string", 5];
		  }
		  ```
	- Working with Enums #typescript/types/enums
	  collapsed:: true
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
	-
	-
		-