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
		  >#next/routing/introduction
	- Extracting Dynamic Path Segment Data (Dynamic Routes)
		- ```jsx
		  // pages/product/[id].js
		  import { useRouter } from 'next/router';
		  
		  const ProductItemPage = ()=>{
		    const router = useRouter();
		    const {id} = router.query
		    return (
		      <div>
		      	id: {id}
		      </div>
		    ) 
		  }
		  ```
		  >#next/routing/dynamic
	- Building Nested Dynamic Routes & Paths
		- ```jsx
		  // pages/clients/[id]/[clientprojectid].js
		  import { useRouter } from 'next/router';
		  
		  const SelectedClientProjectPage = () => {
		    const router = useRouter();
		    const {id,clientprojectid} = router.query
		    return (
		      <div>
		        <p>id: {id}</p>
		        <p>clientprojectid: {clientprojectid}</p>
		      </div>
		    );
		  };
		  ```
		  >#next/routing/dynamic
	- Adding Catch-All Routes
		- ```jsx
		  // pages/blog/[...slug].js
		  // url: domain.com/blog/2022/11/07
		  import { useRouter } from 'next/router'
		  
		  function BlogPostsPag() {
		    const router = useRouter();
		    const {} =
		  }
		  ```