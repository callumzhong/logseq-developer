title:: Next.js & React - The Complete Guide (incl. Two Paths)

- title:: nextjs-course-code
  tags:: course #programming #frontend-developer
- >Author(s): [[Maximilian Schwarzmiiller]]
  Url: https://www.udemy.com/course/nextjs-react-the-complete-guide/learn/lecture
  GitHub: https://github.com/mschwarzmueller/nextjs-course-code
-
- Secton 3 : Pages & File-based Routing
	- What Is "File-based Routing"? And Why Is It Helpful?
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
	- Extracting Dynamic Path Segment Data (Dynamic Routes)
		- ```jsx
		  // pages/product/[id].js
		  // domain.com/product/xxx
		  import { useRouter } from 'next/router';
		  
		  const ProductItemPage = () => {
		    const router = useRouter();
		    const { id } = router.query
		    
		    return (
		     <div>
		        <h1> id: {id}</h1>
		     </div>
		    );
		  };
		  export default ProductItemPage;
		  ```
		  >[Routing: Dynamic Routes | Next.js (nextjs.org)](https://nextjs.org/docs/routing/dynamic-routes)
		  #next/routing/dynamic