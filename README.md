# Web Portfolio

My web portfolio where the wireframe was based on Denis Ivanovs portfolio with lots of changes and done in Nuxt.js ,Vuetify and Vue.js <br> 
I wanted to showcase my projects instead of just sending github links which i know would be bothersome for people. <br><br>
At the bottom right are controls for page navigation and email (upon clicking it the user must have a default mail client installed) <br>
At the same time i learned how to use localStorage and change css root with Vue.js.


![](https://github.com/littlenines/WebPortfolio/blob/f8e0fff1e511e5051cf2a53adaa172da9a610a9c/portfoliogif.gif)

## Deploy and Note 

This repository is not the deployed one , the reason being with few complications with heroku. For some reason i couldn't deploy this repository , the problem was most likely the usage of `Yarn` , the moment i switched to `npm` everything worked fine and for that reason i suggest choosing npm package when creating `nuxt-app`. <br><br>

#### Deploy on Heroku

1. Make a free account on Heroku 
2. Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)
3. Add `"heroku-postbuild": "npm run build"` in `package.json`
``` javascript
"scripts": {
  "dev": "nuxt",
  "build": "nuxt build",
  "start": "nuxt start",
  "heroku-postbuild": "npm run build"
}
```
4. Create the Procfile <br>
<i>This special file specifies the commands that are executed by the app on startup.
Create a file and name it Procfile with no file extension, then inside it write:</i>
``` javascript
web: npm run start
```
5. Finally, we can build our app running into the terminal the command:
``` javascript
npm run build
```
<br>
6. <b>Initialize a local Git repository</b> <br> <br>

``` javascript
> git init

Initialized empty Git repository in .git/

> git add .
> git commit -m "My commit message"

Created initial commit 5df2d09: My commit message
 44 files changed, 8393 insertions(+), 0 deletions(-)
 create mode 100644 README
 create mode 100644 Procfile
...
```
7. Create a Heroku app <br>
<i> The heroku create CLI command creates a new empty application on Heroku, along with an associated empty Git repository. If you run this command from your app’s root directory, the empty Heroku Git repository is automatically set as a remote for your local repository. </i> <br>

```
> heroku create your-random-app-name
```
> Now, we have to tell Heroku to install the devDependencies of our project (to be able to launch `npm run build`):

```
> heroku config:set NPM_CONFIG_PRODUCTION=false
```

> Also, we want our application to listen on the `host 0.0.0.0` and run in production mode:
```
> heroku config:set HOST=0.0.0.0
> heroku config:set NODE_ENV=production
```
8. Finally, we can push the app on Heroku with:
```
> git push heroku master
```
