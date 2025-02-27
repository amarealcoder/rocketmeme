<div align="center">
<a href="https://rocketmeme.netlify.app"><img src="https://user-images.githubusercontent.com/62628408/156283195-028f807e-633f-479f-9244-4cdd795a3183.svg" width="80px"></a>  
</div>

<div align="center">
<h1>Rocketmeme</h1>
<p>A multipurpose meme marketplace and editor for creating and downloading memes. View meme collection, browse different meme categories, like share and save memes.</p> 
</div>

<p align="center">
<a href="https://reactjs.org/">
    <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB">
</a>
<a href="https://styled-components.com/">
 <img src="https://img.shields.io/badge/styled--components-DB7093?style=flat-square&logo=styled-components&logoColor=white">
</a>
    
<a href="https://prettier.io/">
    <img src="https://img.shields.io/badge/prettier-1A2C34?style=flat-square&logo=prettier&logoColor=F7BA3E">
</a>
    
<a href="https://github.com/evavic44/rocketmeme/labels/help%20wanted"> 
<img src="https://img.shields.io/github/labels/evavic44/rocketmeme/help%20wanted">
</a>
    
<a href="https://github.com/evavic44/rocketmeme/labels/enhancement"> 
<img src="https://img.shields.io/github/labels/evavic44/rocketmeme/enhancement">
</a> 
    
<a href="https://analytics.google.com/analytics/web/?utm_campaign=2021q1-onboarding-ga&utm_source=google-growth&utm_medium=email&utm_content=gold-welcome-0#/p303972922/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-engagement-overview&ruid=lifecycle-engagement-overview,life-cycle,engagement&collectionId=life-cycle">
<img src="https://img.shields.io/badge/Google%20Analytics-E37400?style=flat-square&logo=google%20analytics&logoColor=white">
</a>
    
<a href="https://hashnode.com">
<img alt="code style: prettier" src="https://img.shields.io/badge/Hashnode-2962FF?style=flat-square&logo=hashnode&logoColor=white">
</a> 
    
<a href="fontawesome.com/">
<img src="https://img.shields.io/badge/Font_Awesome-339AF0?style=flat-squaree&logo=fontawesome&logoColor=white">
</a>
    
<a href="vitejs.dev/">
<img src="https://img.shields.io/badge/Vite-B73BFE?style=flat-square&logo=vite&logoColor=FFD62E">
</a>

<a href="https://app.netlify.com/sites/rocketmeme/deploys">
    <img src="https://api.netlify.com/api/v1/badges/6a4fdf68-75a7-458f-87aa-36fbe5f31a7a/deploy-status">
</a>  
</p>

<p align="center">
<img src="https://forthebadge.com/images/badges/built-with-love.svg">
<img src="https://forthebadge.com/images/badges/open-source.svg"><br><br>
<a href="https://www.producthunt.com/posts/rocketmeme?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-rocketmeme" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=338739&theme=light" alt="Rocketmeme - Create&#0044;&#0032;share&#0032;&#0038;&#0032;download&#0032;memes&#0032;or&#0032;use&#0032;our&#0032;powerful&#0032;API | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>
</p>



# 👀 Preview

Click this link to view <a href="https://rocketmeme.com">rocketmeme</a>

<a href="https://rocketmeme.com">
<img src="https://user-images.githubusercontent.com/62628408/156625869-36fc5d11-ed4b-45bb-85d8-4d601c19505e.png" alt="Rocketmeme Preview">
</a>

<div align="left">
    <h1>How to run locally ✨</h1>
    <p>Follow these steps below to run rocketmeme locally in your machine. We are using <a href="https://vitejs.dev/">vite.js</a> to bootstrap this application. You can read their <a href="https://vitejs.dev/guide/">docs</a> for more info. </p>
</div>

## 🧩 Prerequisites

In other to run our react app, make sure you have the following installed locally.

- <a href="https://nodejs.org/en/">Node.js</a> - vite requires node at least version 10.16.0

### Clone this repository

Clone this repository to your local machine.

```shell
git clone https://github.com/Evavic44/rocketmeme.git
```

### Cd client

Change directory into the client folder. This is where the frontend code lives.

```shell
cd client
```

### Install NPM

```shell
npm install
```

### Run

Run the development server to view the app.

```shell
npm run dev
```

Now you can navigate to [http://localhost:3000](http://localhost:3000/) to view the app.

<div align="left">
    <h1>Adittional Commands ✨</h1>
</div>

### Build

```
npm run build
```

This is a preview of your dev server.

### Serve

```
npm run serve
```

This is a preview of your build

## Rocketmeme API

```css
/* API Endpoint */
https://rocketmeme-user.hasura.app/v1/graphql
```

With Hasura, we were able to create a serverless API using Hasura cloud. The API exists for two types of requests: The meme template and the uploaded memes. If you're interested, you can start exploring the API docs to get an idea of everything possible with the rocketmeme API.💛  

[API Docs](https://victor-eke.gitbook.io/rocketmeme-api/)

```js
async function fetchGraphQL(operationsDoc, operationName, variables) {
  const result = await fetch(
    "undefined",
    {
      method: "POST",
      body: JSON.stringify({
        query: operationsDoc,
        variables: variables,
        operationName: operationName
      })
    }
  );

  return await result.json();
}

const operationsDoc = `
  query MyQuery {
    meme_templates(order_by: {id: asc, image_link: asc, title: asc}) {
      id
      image_link
      title
    }
  }
`;

function fetchMyQuery() {
  return fetchGraphQL(
    operationsDoc,
    "MyQuery",
    {}
  );
}

async function startFetchMyQuery() {
  const { errors, data } = await fetchMyQuery();

  if (errors) {
    // handle those errors like a pro
    console.error(errors);
  }

  // do something great with this precious data
  console.log(data);
}

startFetchMyQuery();
```

## 🎨 Styling
Styling is done using **styled-components** and **css3**

![Style Guide](https://user-images.githubusercontent.com/62628408/159381509-13ebf539-5382-451d-9b20-4ac53626e6cf.png)
A preview of the style guide.
## 🤝🏾 Contribution

Are you contributing to this project, please ensure all pull requests and contributions comply with our <a href="https://github.com/Evavic44/rocketmeme/blob/main/CONTRIBUTING.md">guidelines</a>. Before making any changes, ensure you have raised an issue here, unless it is a minimal change.

## 📁 Folder Structure

```bash
├── client
│   ├── public
│   │   ├── images
│   │   │   ├── ../
│   │   ├── Robots.txt
│   │   ├── _redirects
│   ├── src
│   │   ├── Components
│   │   │   ├── ../
│   │   ├── pages
│   │   │   ├── ../
│   │   ├── App.jsx
│   │   ├── index.css
│   │   ├── main.jsx
├── src
│   ├── controllers
│   ├── middlewares
│   ├── models
│   ├── routes
│   ├── services
│   ├── utils
│   ├── index.js
├── .env.example
├── .gitignore
├── .gitpod.yml8
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── package.json
```

_This structure is completely flexible and bound to change. Updates to this tree is done manually till we find a suitable generator 😿_

## 🔐 License

This project is protected by <a href="https://github.com/Evavic44/rocketmeme/blob/main/LICENSE">MIT License</a>.

## 💵 Sponsor

Consider supporting us buy buying us a coffee or two. We appreciate every donation.

<div>
  <a href="https://www.buymeacoffee.com/evavic44">
    <img width="150px" alt="bmc-button" src="https://user-images.githubusercontent.com/62628408/127788747-8850d386-fc61-4fff-b18f-8c5ee597be34.png">
  </a>
<img width="150px" height="100%" src="https://img.shields.io/badge/sponsor-30363D?style=for-the-badge&logo=GitHub-Sponsors&logoColor=#white">
</div>

If you like this project, kindly star ⭐ and share this project. It means the world to us.

## Contributors ✨

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://spiffgreen.pages.dev/"><img src="https://avatars.githubusercontent.com/u/73044138?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Spiff Jekey-Green</b></sub></a><br /><a href="https://github.com/Evavic44/rocketmeme/issues?q=author%3ASpiffGreen" title="Bug reports">🐛</a> <a href="https://github.com/Evavic44/rocketmeme/commits?author=SpiffGreen" title="Code">💻</a> <a href="#ideas-SpiffGreen" title="Ideas, Planning, & Feedback">🤔</a> <a href="https://github.com/Evavic44/rocketmeme/pulls?q=is%3Apr+reviewed-by%3ASpiffGreen" title="Reviewed Pull Requests">👀</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
