# Tutorial: Deploying a basic Slim app on Jekyo

Demo app [here](https://slim-demo.jekyo.app/)

### Prerequisites

Make sure you have [NodeJS](https://nodejs.org/en/download/), [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) and [git](https://github.com/git-guides/install-git) installed.

If it's your first time using **Jekyo**, you can **install** it by running the following command in your terminal:

`npm install -g jekyo`

### Sign in to Jekyo

You can sign in to Jekyo by running `jekyo user:signin`

```
➜  ~ jekyo user:signin 
Your email?: **************
Your password?: **********
You have successfully signed in!
```
If you don't have a Jekyo account, you can create one in the terminal by running `jekyo user:signup`. 

## 1. Create a basic Slim app

You can start your Slim project by using `jekyo create`

Using the **arrows** on your keyboard, select **slim** and press **enter**.  
```
? Select template
  None Creates only the application
  expressjs A basic app skeleton using [Express](https://expressjs.com/)     
  nuxt-js A boilerplate SSR application using [Nuxt.js](https://nuxtjs.org/) 
❯ slim A basic starter app using [Slim](https://www.slimframework.com/)
```
When prompted, enter the desired name for your Slim app. 

`Application name?: slim-tutorial`

This will create a basic Slim app in the current directory by cloning this [Slim starter app](https://github.com/jekyo/slim-getting-started) repository.

```
Cloning source code... OK
Application created!
```

### Deploy the Slim app on Jekyo

To deploy the app, first navigate to the newly created directory:

`cd slim-tutorial`

Now you can deploy this app to Jekyo by running: 

`jekyo deploy`

After a while, you should see something like this:

```
➜  Fetching source code ... OK
➜  Building application, this might take a while ... OK
➜  Publishing application, this might take a while  ... OK
➜  Deploying application ... OK        
➜  Waiting for application to start ... OK
➜  Visit your app on: https://slim-tutorial.jekyo.app ... OK
```

You can now browse to your Slim app on https://slim-tutorial.jekyo.app (replace 'slim-tutorial' with your app name)

## 2. Deploying an existing Slim app

Navigate to your local Slim app directory

`cd my-slim-app`

Initialize a git repository if you haven't already done so by running `git init`. 

### Create a Procfile

In your app's root folder, make a file named **Procfile** (no extension) and add the following line:

```
web: php -S 0.0.0.0:4139 -t public public/index.php
```
This is necessary for starting the server and allowing connections from other computers. 

[Commit]((https://github.com/git-guides/git-commit)) the newly added file:

```
git add Procfile
git commit -m "added Procfile"
```

### Create an empty Jekyo app:

`jekyo create` 

Select 'none' using the **arrows** on your keyboard and press **enter**. This will create an app using your current directory. 

```
? Select template (Use arrow keys)
❯ None Creates an application from your current directory
```

Name your app: 

`Application name?: my-slim-app`

Run `jekyo link` to link your local app to the remote Jekyo app. Select 'my-slim-app' using the **arrows** on your keyboard and press **enter**.

```
? Select application (Use arrow keys)
❯ my-slim-app
```
### Now you can deploy this app to Jekyo by running: 

`jekyo deploy`

After a while, you should see something like this:

```
➜  Fetching source code ... OK
➜  Building application, this might take a while ... OK
➜  Publishing application, this might take a while  ... OK
➜  Deploying application ... OK        
➜  Waiting for application to start ... OK
➜  Visit your app on: https://my-slim-app.jekyo.app ... OK
```

You can now browse to your Slim app on https://my-slim-app.jekyo.app (replace 'my-slim-app' with your app name)

## Pushing local changes to Jekyo 

Add the newly modified file(s) to the git index by using [git add](https://www.atlassian.com/git/tutorials/saving-changes)

`git add filename`

Create a [git commit](https://github.com/git-guides/git-commit)

`git commit -m "your commit message"`

Now, simply deploy your app again:

`jekyo deploy`

You will see your changes on your live app after a short while. 
