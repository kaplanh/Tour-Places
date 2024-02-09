# Tour Places 

[:point_right: Click here to see on browser](https://kaplanh.github.io/Tour-Places/)

[Tour Places](tour-project.gif)

---
 **What's used in this app ?** |  **Author** |
|----------|------------|
|React - component |[Take a look at my portfolio](https://kaplanh.github.io/Portfolio_with_CssFlex/)|
|React - props|[Visit me on Linkedin](https://www.linkedin.com/in/kaplan-h/)|
|React - sass||    
|Deploy with GitHub Pages | |   
  

---

## How To Run This Project 🚀

<br/>

### 💻 Install React 👇

```bash
yarn create react-app .  or npx create-react-app .
```
### 💻 Install Sass 👇

```bash
yarn add sass  or npm i sass
```

## 🔴 Delete these files and delete the imports👇

    - App.test.js
    - reportWebVitals.js
    - setupTests.js
    - favicon.ico
    - logo192.png
    - logo512.png
    - manifest.json
    - robots.txt

### 💻 Start the project 👇

```bash
yarn start or npm start
```
OR
- <strong>Clone the Repo</strong>

  ```sh
  git clone
  ```
  

- <strong>Install NPM packages</strong>

  ```sh
  npm install or yarn 
  ```

- <strong>Run the project</strong>

  ```sh
  npm start or yarn start
  ```

- <strong>Open the project on your browser</strong>

  ```sh
  http://localhost:3000/
  ```

- ### <strong>Enjoy! 🎉</strong>

---

## Project Skeleton 

```
Horoscope App(folder)
|
|----public (folder)
│     └── index.html
|----src (folder)
|    |--- components (folder)
|    |       |── header(folder)
│    │       |     ├── Header.jsx
│    │       |     ├── Header.scss
│    │       |     ├── Header.css
│    │       |
|    |       |── main(folder)
│    │       |     ├── Main.jsx
│    │       |     ├── Main.scss
│    │       |     ├── Main.css
│    │       |     ├── Card.jsx
│    │       |
|    |       |── navbar(folder)
│    │             ├── Navbar.jsx
│    │             ├── Navbar.scss
│    │             ├── Navbar.css
│    │
|    |--- helper (folder)
|    |       |── data.js
│    │       |── logo.png
│    │                      
│    |--- scss (folder)
|    |      ├── _reset.scss
|    |      ├── _mixins.scss
|    |      ├── _variables.scss
|    |      
|    |       
│    ├--- App.js
│    ├--- App.scss
│    ├--- App.css
│    │--- data.js
│    └--- index.js
│
│
|--- .gitignore
|── package-lock.json
├── package.json
|── README.md
|── yarn.lock

```
---
### At the end of the project, the following topics are to be covered;

- sass with react
  ```scss
   // src/scss/_reset.scss
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

   // src/scss/_variables.scss
       //? Colors
     $backgroundColor:#ace0f9;
     $cardNavBgColor: #171b20;
  
   // src/scss/_mixins.scss
    @mixin media-xsm {
    @media screen and (min-width: 0px) {
      @content;
    }
  }
  
  
  @mixin media-sm {
    @media screen and (min-width: 576px) {
      @content;
    }
  }



  
   // src/scss/app.scss
  
  @import './scss/reset', './scss/variables';

      @import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@700&display=swap');
      
      @import url('https://fonts.googleapis.com/css2?family=Hubballi&display=swap');
      
      body{
          background-color: $backgroundColor;
          font-family: 'Amatic SC', cursive;
      }
      
      p{
          font-family: 'Hubballi', cursive;
      }

  ```
   



- Parent Component icinde json datayi map() leme
   ```jsx
   // src/components/main/Main.jsx Parent component
   
         import { data } from "../../helpers/data";
        import "./Main.scss";
        import Card from "./Card";
        const Main = () => {
            // console.log(data);
            return (
                <div className="card-container">
                    {data.map((item, i) => (
                        // !props
                        // ?asagi data göndermenin 1.yolu
                        // <Card item={item} />
                        // böyle gönderirsek diger tarafta props.item.title seklinde yakalamaliyim
                        // ?asagi data göndermenin 2.yolu
                        <Card key={item.id} {...item} />
                        
                    ))}
                </div>
            );
        };
        export default Main;



   // src/components/main/Card.jsx Child component
   
       const Card = (data) => {
    // console.log("ne geliyo", data);
    const { id, title, image, desc } = data;
    return (
        <div key={id} className="cards">
            <div className="title">
                <h1>{title}</h1>
            </div>
            <img src={image} alt="" />

            <div className="card-over">
                <p>{desc}</p>
            </div>
        </div>
    );
  };
  
  export default Card;

  ```
   ---
- Deploy with GitHub Pages
  
-    ### 💻 write in Terminal 👇

```bash
// src
 npm i gh-pages or yarn add gh-pages
```

-    ### 💻  add this in scripts: "predeploy": "yarn run build",  "deploy": "gh-pages -d build" // if you use npm: "predeploy": "npm run build","deploy": "gh-pages -d build" 👇

  ```sh
// src/package.json

  "scripts": {
        "start": "react-scripts start",
        "build": "react-scripts build",
        "test": "react-scripts test",
        "eject": "react-scripts eject",
        "predeploy": "yarn run build", 
        "deploy": "gh-pages -d build"
    },
```
   
   ### 💻  add github.io link as homepage:  "homepage": "https://kaplanh.github.io/horoscope_app", 👇

```bash
// src/package.json
{
    "homepage": "https://kaplanh.github.io/horoscope_app",
    "name": "horoscope_app",
    "version": "0.1.0",
    "private": true,
    "dependencies": {
        "gh-pages": "^6.1.1",
        "react": "^18.2.0",
        "react-dom": "^18.2.0",
        "react-scripts": "5.0.1",
        "sass": "^1.70.0"
    },
```



-    ### 💻  write in Terminal 👇

  ```sh
    yarn run deploy  or npm run deploy
  ```

-    ### 💻  visit your page link 👇

  ```sh
  https://kaplanh.github.io/horoscope_app
 ```


- Image üzerine geldiginde alttan yukari dogru scrolsüz metin kaydirma

  ```jsx
   const Card = ({ title, date, image, desc }) => {
    // const { title, date, image, desc } = props;
    // console.log("ne geliyor", props);
    return (
        <div className="cards">
            <div className="title">
                <h1>{title}</h1>
            </div>
            <div className="date">
                <h2>{date}</h2>
            </div>
            <img src={image} alt="" />
            <div className="card-over">
                <p>{desc}</p>
            </div>
        </div>
    );
  };


  ```

  ~~~scss


  
    .cards {
        width: 500px;
        height: 350px;
        position: relative;
        overflow: hidden;        
        &:hover .card-over {
            transform: translate(0%);
        }
        &:hover img {
            opacity: 1;
        }

    .card-over {
        width: 500px;        
        position: absolute;
        bottom: 0;
        left: 0;
        background-color: rgba(0, 0, 0, 0.8);
        font-size: 1.5rem;
        z-index: 3;
        padding: 1rem;
        transform: translateY(100%);
        transition: transform 0.7s;
        max-height: 75%;
        overflow: auto;
        // ?scrollbari kaybetmek icin
        &::-webkit-scrollbar{
            display: none;
        }
  
    }
  ~~~

  
  
---
 

## Feedback and Collaboration
I value your feedback and suggestions. If you have any comments, questions, or ideas for improvement regarding this project or any of my other projects, please don't hesitate to reach out.
I'm always open to collaboration and welcome the opportunity to work on exciting projects together.
Thank you for visiting my project. I hope you have a wonderful experience exploring it, and I look forward to connecting with you soon!



<p align="center"> ⌛<strong> Happy Coding </strong> ✍ </p>







