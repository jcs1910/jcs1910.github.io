---
title: "[React] Create-react-app-settings"
date: "2019-08-10T18:25:42.199Z"
template: "post"
draft: false
slug: "/posts/create-react-app-settings/"
category: "React"
tags:
  - "React"
  - "create-react-app"
  - "npx"

description: "npx create-react-app <your foldername>"
---

<figure>
    <img src="/media/20190810-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

### Enter following commands line in Terminal

    yarn global add npx
    npm i npx -g
    npx create-react-app koflix  //>>koflix is my folder name. Create your own file.

    cd koflix

    code .   // open VS Code Editor

## If you have issues installing npx, take a look at [here.](https://www.notion.so/bpratings/JS-Unable-to-install-npx-eae73dc6edab485c843d789ff519494a)

### 1. Delete unnecessary files

- `src/App.js`
- `src/App.css`
- `src/index.css`
- `src/App.test.js`
- `src/logo.svg`

### 2. Prepare for basic settings of **Components** files by removing unnecessary stuff in "App.js" and "index.js".

```javascript
//index.js

import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));

import React from "react";

function App() {
  return <div className="App" />;
}

export default App;
```

### 3. Create a new file called`.env` next to `.gitignore` and add `NODE_PATH=src` inside `.env` folder. .env helps src(source folder) to look at files separated between folders. Later, you're going to create a new `Components` file inside `src` and put `index.js` so that you can handle all the components with ease.

Don't forget to add prop-types in Terminal.

`yarn add prop-types`

Once installed, let's begin.

## `yarn start`

---

> **We are creating wealth every time we write a code**
