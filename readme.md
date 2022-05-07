# The Van Life Club - Landing Page
   
   A simple landing page for a club with a working input email form in the middle for subscription using *getrevue.co* code.

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)

## Overview

### Screenshot

![](./screenshot.png)

### Links

- Live Site URL: [https://julfinch.github.io/The-Van-Life-Club/](https://julfinch.github.io/The-Van-Life-Club/)

## My process

1. Open terminal or command prompt.
      > Type:
      > 
      > `npm create vite landing-page-1`
      > 
      > *Need to install the following packages:*
      > 
      > `create-vite`
      > 
      > Ok to procees? (y)
      > 
      > - **Click ENTER**
      > 
      > *Select a framework:*
      > 
      > `react`
      > 
      > *Select a variant:*
      > 
      > `react`
      >
      > Scaffolding project in C:\Users\lenovo\landing-page-1...
      >
      > *Done. Now run:*
      >
      > *cd landing-page-1*
      > 
      > *npm install*
      > 
      > *npm run dev*
      >
      > `npm i`
      >
      > *added 80 packages. and audited 81 packages...*
      > 
      > *found 0 vulnerabilities*
      >
      > `npm i -D tailwindcss@latest postcss@latest autoprefixer@latest`

2. From the **.src folder**, delete the following:
    - App.css
    - App.test.js
    - logo.svg
    - reportWebVitals.js
    - setupTests.js

3. Delete `import logo from './logo.svg';` from `App.js`
4. Delete `import reportWebVitals from './reportWebVitals';` from `index.js` including the lines below:
      > // If you want to start measuring performance in your app, pass a function
      > // to log results (for example: reportWebVitals(console.log))
      > // or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
      > reportWebVitals();
5. Under **.src folder**, create an `assets` folder and `components` folder.
6. Type `npm start` in the terminal to start the live server.
7. Open `App.js` and delete everything, only leave the following lines:
  
  ```js
  function App() {
    return (
      <>
        
      </>
    );
  }

  export default App;
  ```
8. Type `npm i -D tailwindcss@latest postcss@latest autoprefixer@latest` to install Tailwind.
9. Create a **Tailwind CSS config file** and **PostCSS config file**:
      >`npx tailwindcss init -p`
10. Open the **tailwind.config.js**
11. Add the following:
    - source link for the content `["./src/**/*.{js,jsx}"]`
    - under the **colors** add `primary: '#EE9789'`
    - add `fontFamily: { sans: ['Montserrat', 'sans-serif'] }`

    ```js
     module.exports = {
      content: ["./src/**/*.{js,jsx}"],
      theme: {
          extend: {
              colors: {
                  primary: '#EE9789'
              }
          },
          fontFamily: {
              sans: ['Montserrat', 'sans-serif']
          }
      },
      plugins: [],
    }
    ```

12. Under **index.html**, paste in the **<head>** section the link of the Montserrat font from *www.fonts-google.com*
    ```html
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,700;0,900;1,400&display=swap" rel="stylesheet">
    ```
 
13. Under the **index.css**, write the following:
    ```css
      @tailwind base;
      @tailwind components;
      @tailwind utilities;
  
      body {
          background-image: url('./bg.jpg');
          background-size: cover;
          background-position: top center;
      }
    ```
 
14. Open the **App.jsx** and delete everything and leave the following codes:
    ```js
      function App() {
          return (
              <div>
              </div>
          )
      }

      export default App
    ```

15. To open the live server, write in the terminal: 
     >`npm run dev`

     *If this fails and live server doesn't load,*
     > 
     > If *'vite' is not recognized as an internal or external command, operable program of batch file.*
     >
     > `npm install`
     >
     > *then*
     >
     > `npm run dev`

16. Open the live server in: `http://localhost:3000/`

### Deployment of Vite App to Github
   
1. Open the **Source Control** in VsCode and publish the project as **Public on Github**
   
2. To sync all changes and connect to the github, on the terminal, type: 
   > `git pull`
   
3. Write on the terminal:
   > `npm i gh-pages`
   
4. This step is necessary for a **VITE App**, skip this if using only React. Open **vite.config.js** and add the github repo name as base:
   > `base: '/The-Van-Life-Club/',`
   
   ```js
      import { defineConfig } from 'vite'
      import react from '@vitejs/plugin-react'

      // https://vitejs.dev/config/
      export default defineConfig({
        base: '/The-Van-Life-Club/',
        plugins: [react()]
      })
   ```
   
4. A **dist folder** and **package.json** will be automatically created, open **package.json** and add the following:
   - `"homepage": "https://julfinch.github.io/The-Van-Life-Club/",`
   - Under scripts, add: 
      - `"predeploy": "npm run build",`
      - `"deploy": "gh-pages -d dist",`
   
   ```js
      {
     "name": "landing-page-1",
     "homepage": "https://julfinch.github.io/The-Van-Life-Club/",
     "private": true,
     "version": "0.0.0",
     "scripts": {
       "dev": "vite",
       "predeploy": "npm run build",
       "deploy": "gh-pages -d dist",
       "build": "vite build",
       "preview": "vite preview"
     },
     "dependencies": {
       "gh-pages": "^3.2.3",
       "react": "^18.0.0",
       "react-dom": "^18.0.0"
     },
     "devDependencies": {
       "@types/react": "^18.0.0",
       "@types/react-dom": "^18.0.0",
       "@vitejs/plugin-react": "^1.3.0",
       "vite": "^2.9.2"
     }
   }
   ```
   
5. Now, go back to the terminal and type:
   > `npm run deploy`
   
6. On the Github repo, open **Settings** then **Pages**. Make sure that in the **Source**, the **Branch** should indicate the `gh-pages` instead of `master`
   
### Deployment of Create-React-App to Github
 1. Write in the terminal:
      >`npm install gh-pages --save-dev`
 2. A **build folder** and **package.json** will be automatically created, open **package.json** and add the following:
      - `"homepage": "https://julfinch.github.io/shortly/",`
      - Under scripts, add: 
         - `"predeploy": "npm run build",`
         - `"deploy": "gh-pages -d build",`
            **BE MINDFUL OF THE COMMA TO AVOID ERRORS!**
 3. Go the Github website and create a new repository with the same name as the folder `secure-data`.
 4. Write in the terminal:
      >`git init`
      >then...
      >`git remote add origin https://github.com/julfinch/shortly.git`
 5. Then lastly:
      >`npm run deploy`
 6. The message should show **Published**.
   
### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- ReactJS
- Vite
- Tailwind CSS

---
 
## Author

- Twitter - [@julfinch](https://www.twitter.com/julfinch)
