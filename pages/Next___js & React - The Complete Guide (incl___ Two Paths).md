title:: Next.js & React - The Complete Guide (incl. Two Paths)

- title:: nextjs-course-code
  tags:: course #programming #frontend-developer
- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: https://www.udemy.com/course/nextjs-react-the-complete-guide/learn/lecture
  GitHub: https://github.com/mschwarzmueller/nextjs-course-code
-
- Secton 3 : Pages & File-based Routing
	- 基於文件系統的路由機制
	  ```
	  // domain.com
	  pages/index.js
	  
	  // domain.com/about
	  pages/about.js
	  
	  // domain.com/about/動態 id
	  pages/about/[id].js
	  ```
	  > #next/routing/introduction
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
	  import {useRouter} from 'next/router'
	  import Link from 'next/link'
	  
	  const Nav = ()=>{
	  	return <Link herf="/product"> product </Link> 
	  }
	  
	  // 可使用物件
	  const Nav2 = ()=>{
	  	return <Link herf={{
	          pathname:"/product/[id]",
	          query:{id:'123'}
	        }}> product </Link> 
	  }
	  
	  // 使用 router 物件
	  const Nav = ()=>{
	    const router= useRouter()
	    const clickHandler = ()=>{
	      router.push('/product')
	    }
	    const click2Handler = ()=>{
	      router.replace('/product')
	    }
	    const click2Handler = ()=>{
	      router.push({
	          pathname:"/product/[id]",
	          query:{id:'123'}
	      })
	    }
	    return <button onClick={clickHandler}></button>
	  }
	  ```
	  >  切換路由的方法
	  #next/routing/introduction
	- ```jsx
	  // pages/404.js
	  
	  const NotFoundPage = ()=>{
	    return <div>Error 404 </div>
	  }
	  ```
	  > 404 頁面使用關鍵字命名 file
	  #next/routing/404
	-