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
    - logo.svg

3. Paste the **bg.jpg** to the **.src folder**
4. Create a **Tailwind CSS config file** and **PostCSS config file**:
      >`npx tailwindcss init -p`
5. Open the **tailwind.config.js**
6. Add the following:
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

7. Under **index.html**, paste in the **<head>** section the link of the Montserrat font from *www.fonts-google.com*
    ```html
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,700;0,900;1,400&display=swap" rel="stylesheet">
    ```
 
8. Under the **index.css**, write the following:
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
 
9. Open the **App.jsx** and delete everything and leave the following codes:
    ```js
      function App() {
          return (
              <div>
              </div>
          )
      }

      export default App
    ```

10. To open the live server, write in the terminal: 
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

11. Open the live server in: `http://localhost:3000/`

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- ReactJS
- Tailwind CSS

---
 
## Author

- Twitter - [@julfinch](https://www.twitter.com/julfinch)
