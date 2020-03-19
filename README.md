# VS Online meets Heroku

## Create a new repository

https://github.com/new
![Create a new repository](images/01_create-a-new-repository.png)

## Sign in to VS Online

https://online.visualstudio.com/login
![Sign in to VS Online](images/02_sign-in-to-vsonline.png)

## Create Environment

![Create Environment A](images/03a_create-environment.png)
![Create Environment B](images/03b_create-environment.png)
![Create Environment C](images/03c_create-environment.png)

## Push code from VS Online

![New Terminal](images/04a_new-terminal.png)
![Git commands](images/04b_git-commands.png)

## Fix Node version to use

```bash
$ nvm install 12
```

## Implement web server

```bash
$ npm init
$ npm install express --save
```

app.js
```js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => res.send('The app is running!'));

app.listen(port, () => console.log(`Example app listening on port ${port}!`));
```

package.json
```json
  "scripts": {
    "start": "node app"
  }
```

Run the server
```bash
$ npm start
```

## Test web server running on VS Online environment

![TCP port forward](images/07a_tcp-port-forward.png)
![TCP port forward](images/07b_tcp-port-forward.png)
![TCP port forward](images/07c_connecting-to-the-forwarded-port.png)
![TCP port forward](images/07d_the-app-is-running.png)

## Make the webapp runnable on Heroku

app.js
```js
const port = process.env.PORT || 3000;
```

package.json
```json
  "engines": {
    "node": "12.x",
    "npm": "6.x"
  },
```

package.json (optional)
```json
  "scripts": {
    "start": "node app",
    "build": "echo What you need to run before starting the server such as webpack.",
    "heroku-postbuild": "echo Alternative of build. If specified, build won't be called.",
    "heroku-prebuild": "echo This runs before dependency installation.",
    "heroku-postbuild": "echo This runs after Heroku dependency installation."
  },
```

## Deploy the webapp on Heroku

![Create a new app](images/09a_create-a-new-app.png)
![Create a new app](images/09b_create-a-new-app.png)
![Connect to GitHub](images/09c_connect-to-github.png)
![Connect to GitHub](images/09d_connect-to-github.png)
![Connect to GitHub](images/09e_connect-to-github.png)
![Connect to GitHub](images/09f_connect-to-github.png)
![Manual deploy](images/09g_manual-deploy.png)
![Manual deploy](images/09h_manual-deploy.png)
![Manual deploy](images/09i_manual-deploy.png)
![Manual deploy](images/09j_the-app-is-running.png)

## Automatic deploys

![Automatic deploys](images/10a_automatic-deploys.png)

app.js
```js
app.get('/', (req, res) => res.send('The app is running on Heroku!'));
```

```bash
$ git add app.js
$ git commit -m "Update app.js"
$ git push
```

![Automatic deploys](images/10b_activity.png)

https://vsonline-meets-heroku.herokuapp.com/
![Automatic deploys](images/10c_the-app-is-running-on-heroku.png)
