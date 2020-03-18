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
