title:: Next.js & React - The Complete Guide (incl. Two Paths)

- title:: nextjs-course-code
  tags:: course #programming #frontend-developer
- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: https://www.udemy.com/course/nextjs-react-the-complete-guide/learn/lecture
  GitHub: https://github.com/mschwarzmueller/nextjs-course-code
-
- Secton 3 : Pages & File-based Routing
  collapsed:: true
	- ```
	  // domain.com
	  pages/index.js
	  
	  // domain.com/about
	  pages/about.js
	  
	  // domain.com/about/動態 id
	  pages/about/[id].js
	  ```
	  >[Routing: Introduction | Next.js (nextjs.org)](https://nextjs.org/docs/routing/introduction)
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
	  >[Routing: Dynamic Routes | Next.js (nextjs.org)](https://nextjs.org/docs/routing/dynamic-routes)
	  #next/routing/dynamic
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
	  >[Routing: Dynamic Routes | Next.js (nextjs.org)](https://nextjs.org/docs/routing/dynamic-routes)
	  #next/routing/dynamic
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
	  > [Routing: Dynamic Routes | Next.js (nextjs.org)](https://nextjs.org/docs/routing/dynamic-routes#catch-all-routes)
	  #next/routing/dynamic
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
	  > [Routing: Introduction | Next.js (nextjs.org)](https://nextjs.org/docs/routing/introduction#linking-between-pages)
	  #next/routing/introduction
	- ```jsx
	  // pages/404.js
	  
	  const NotFoundPage = ()=>{
	    return <div>Error 404 </div>
	  }
	  ```
	  >[Advanced Features: Custom Error Page | Next.js (nextjs.org)](https://nextjs.org/docs/advanced-features/custom-error-page#404-page)
	  #next/routing/404
- Secton 4 : Project Time: Working with File-based Routing
	- [callumzhong/nextjs-course-code-practice at e9bcae3ac35d06b6c607fca9a0c25116c17ac4a4 (github.com)](https://github.com/callumzhong/nextjs-course-code-practice/tree/e9bcae3ac35d06b6c607fca9a0c25116c17ac4a4)
- Section 5 : Page Pre-Rendering & Data Fetching
	-