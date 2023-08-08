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

`function App() {
  return (
    <div>
     <h2>Github Pages</h2>
     <h3>Deploying React to Github</h3>
    </div>
  );
}
export default App;
`


