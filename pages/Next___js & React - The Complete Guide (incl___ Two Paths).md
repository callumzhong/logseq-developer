title:: Next.js & React - The Complete Guide (incl. Two Paths)

- title:: nextjs-course-code
  tags:: course #programming #frontend-developer
- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: https://www.udemy.com/course/nextjs-react-the-complete-guide/learn/lecture
  GitHub: https://github.com/mschwarzmueller/nextjs-course-code
-
- Secton 3 : Pages & File-based Routing
	- ```
	  // domain.com
	  pages/index.js
	  
	  // domain.com/about
	  pages/about.js
	  
	  // domain.com/about/動態 id
	  pages/about/[id].js
	  ```
	  > file-system router 
	  #next/routing/introduction
	- ```jsx
	  // pages/product/[id].js
	  // domain.com/product/callum
	  
	  import { useRouter } from 'next/router';
	  
	  const ProductItemPage = ()=>{
	    const router = useRouter();
	    
	    console.log(router.query) // {id:callum}
	    
	    return <div>Hello World<div>
	  }
	  ```
	  >#next/routing/dynamic
	- ```jsx
	  // pages/clients/[id]/[clientprojectid].js
	  // domain.com/clients/callum/123
	  
	  import { useRouter } from 'next/router';
	  
	  const SelectedClientProjectPage = () => {
	    const router = useRouter();
	    
	    console.log(router.query) // {id:callum, clientprojectid:123}
	    
	    return <div>Hello World<div>
	  };
	  ```
	  >#next/routing/dynamic
	- ```jsx
	  // pages/blog/[...slug].js
	  // domain.com/blog/2022/11/07
	  
	  import { useRouter } from 'next/router'
	  
	  function BlogPostsPag() {
	    const router = useRouter();
	    
	    console.log(router.query) // { slug: ["2022","11","07"]}
	    
	    return <div>Hello World<div>
	  }
	  ```
	  > #next/routing/dynamic
	- ```jsx
	  import Link from 'next/link'
	  
	  const Navbar = ()=>{
	  	return <Link herf="/product"> product </Link> 
	  }
	  
	  // 可使用物件
	  const Navbar2 = ()=>{
	  	return <Link herf={{
	          pathname:"/product/[id]",
	          query:{id:'123'}
	        }}> product </Link> 
	  }
	  ```
	  >  使用 Link 進行跳轉路由
	  #next/routing/introduction
	- ```jsx
	  ```