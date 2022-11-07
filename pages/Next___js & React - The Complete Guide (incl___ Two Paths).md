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
		  // domain.com/product/123
		  
		  // pages/product/[id].js
		  
		  import { useRouter } from 'next/router';
		  
		    const router = useRouter();
		  const {} = router.
		  };
		  ```
		  >#next/routing/dynamic
	- Building Nested Dynamic Routes & Paths
		- ```jsx
		  // pages/clients/[id]/[clientprojectid].js
		  import { useRouter } from 'next/router';
		  
		  const SelectedClientProjectPage = () => {
		    const router = useRouter();
		    return (
		      <div>
		        <ul>
		          {Object.entries(router.query).map(
		            ([key, value], idx) => (
		              <li key={idx}>
		                key: {key}
		                <br />
		                value: {value}
		              </li>
		            ),
		          )}
		        </ul>
		      </div>
		    );
		  };
		  ```
		  >#next/routing/dynamic
	- Adding Catch-All Routes
		-