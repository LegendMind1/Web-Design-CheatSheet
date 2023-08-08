# **How to Deploy a React App for Free With GitHub Pages**  
If you have a project and want to host it for free without buying a domain, using GitHub Pages is a great choice. GitHub Pages converts your repositories into websites and allows you to host unlimited project sites.  

Deploying a React site with navigation requires extra configuration compared to deploying a static site. This tutorial walks you through the whole process from creating a GitHub repository to having a hosted site.

## **Create a React App**  
 - If you have an existing React project, feel free to skip this step. Otherwise create React-App first with npm or yarn and start the app.  
 ```console
 1. npx create-react-app react-gh  
 2. npm run start  
 ```
- Next, open the project folder with your preferred code editor. In the src folder, delete everything except App.js and index.js. Replace the contents in App.js with the following:

```console
function App() {
  return (
    <div>
     <h2>Github Pages</h2>
     <h3>Deploying React to Github</h3>
    </div>
  );
}
export default App;
```

## **Add Routing**  
- To add routing to your application, first, install react-router-dom:

```console
npm install react-router-dom
```

- In App.js, add the link to the about page:

```console
import { Link } from "react-router-dom";
function App() {
  return (
    <div>
      <Link to="/about">About</Link>
     <h2>Github Pages</h2>
     <h3>Deploying React to Github</h3>
    </div>
  );
}
export default App;
```

- Since App.js will act as your home page, you only need to create the About component:

```console
const About = () => {
    return ( 
        <div>
          <Link to="/">Home</Link>
          <h2>About Page</h2> 
        </div>
        );
}
export default About;
```

- Now, you need to create the routes and configure a React router.

- Modify index.js to match the URL to the respective components:
  
```console
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
import { HashRouter, Routes, Route } from "react-router-dom";
import About from "./About";
ReactDOM.render(
  <React.StrictMode>
    <HashRouter>
      <Routes>
        <Route path="/" element={<App/>} />
        <Route path="/about" element={<About/>}/>
      </Routes>
    </HashRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```

- Notice how you used HashRouter instead of BrowserRouter. Using BrowserRouter would raise a 404 error. This is because routing works differently in GitHub pages. Hashrouter does not raise an error because it uses the hash portion of the URL to sync the UI with the URL.

- The final step is committing all the new changes to Git:

```console
git add .
git commit -m "Create React app"
```

## **Create GitHub Repository**  
- Since GitHub Pages will host your application by converting the repository to a website, you need to create a GitHub repository. Go to your GitHub account and create a new repository with the same name as your project.

- Next, add the GitHub repository to your local repository as a remote:

```console
git remote add origin <https://github.com/><username>/<repository name>.git
```

- Finally, push the local repository to GitHub:

```console
git branch -M main
git push --set-upstream origin main
```

## **Deploy React App to GitHub Pages**  

-In order to use GitHub Pages, you'll have to install it first:

```console
npm install gh-pages
```

- gh-pages will allow you to create the gh-pages branch where you'll deploy your code.

-  Next, go to your package.json file and add the homepage which will be the home URL of the app:

```console
"homepage": "https://<username>.github.io/<repository-name>/",
"scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build", 
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
  ```

- Run the following command to complete the deployment process:

```console
npm run deploy
```

- Your application is now deployed to GitHub and you can visit it at https://**<username>.github.io/<repository-name>.**  


**Author: LegendMind**
Leave comments if you find this useful please. Thanks






