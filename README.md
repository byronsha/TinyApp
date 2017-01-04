# TinyApp
For a friend learning React, who complained about the initial setup.

And for those who sometimes feel like doing some coding on their Windows machine
between matches in Dota 2, League, Overwatch, etc.

## Install Node.js for Windows
Download the latest version of Node.js from https://nodejs.org/en/

Once it's installed, open up the Node.js command prompt.

![alt text](images/node_command_prompt.png)

### Create your project directory
In your command prompt:

`cd Desktop`  
`mkdir TinyApp`  
`cd TinyApp`  

Open up the project in your favorite IDE.

## Setup your package.json file
Initialize using the the command:

`npm init --yes`

You will need the following packages:
* react
* react-dom
* babel-core
* babel-loader
* babel-preset-react
* babel-preset-es2015
* babel-preset-stage-0
* webpack
* webpack-dev-server

`npm i -S react react-dom babel-core babel-loader babel-preset-react babel-preset-es2015 babel-preset-stage-0 webpack webpack-dev-server`

Also add the following line to your `package.json` "scripts":

`"dev": "webpack-dev-server --inline"`

The file should look like this now:

![alt text](images/package.json.png)

```
{
  "name": "TinyApp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "webpack-dev-server --inline"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "babel-core": "^6.21.0",
    "babel-loader": "^6.2.10",
    "babel-preset-es2015": "^6.18.0",
    "babel-preset-react": "^6.16.0",
    "babel-preset-stage-0": "^6.16.0",
    "react": "^15.4.1",
    "react-dom": "^15.4.1",
    "webpack": "^1.14.0",
    "webpack-dev-server": "^1.16.2"
  }
}
```

## Create webpack.config.js file
In your root directory, create a file named `webpack.config.js`, and copy the following code:

![alt text](images/node_command_prompt.png)

There's a ton of different things you're allowed to configure here, depending on what packages you want to include in your project. This is the most simple version I could come up with.

## Create index.html file
In your root directory, create a file named `index.html`, and copy the following code:

![alt text](images/node_command_prompt.png)

`<div id="root"></div>` is the root DOM element that your React app will be attached to.

`assets/bundle.js` is the bundled file created by webpack-dev-server that includes live-reloading. This should only be used for development. You'll notice that no file is created in your project directory.

webpack-dev-server is a little Node.js Express server, which uses webpack-dev-middleware to serve a webpack bundle. You can read more about it in the official docs: https://webpack.github.io/docs/webpack-dev-server.html

If you want to create `bundle.js`, just run `webpack` in your terminal and, in this example, you should see it in `build/bundle.js`.

## Create app/entry.js file
Create a new folder inside your project called `app`. Inside `app` create a file named `entry.js`. This is the entry point for webpack, where you'll start writing your React app.
