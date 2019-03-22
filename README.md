# Introduction
This tutorial is meant to provide a gentle introduction to building a simple static website. This tutorial is very abbreviated, and other more thorough resources will be linked in the relevant sections. This tutorial will cover writing a basic server in express, writing a basic HTML file from scratch (with CSS and JS), and should provide a basic knowledge of key elements of a website. We will start by building a basic backend server and then discuss writing a frontend web page.

We will be using the following libraries/programs throughout this tutorial:
* [Node JS](https://nodejs.org/en/)- Javascript runtime environment designed for web applications
* [NPM (Node Package Manager)](https://www.npmjs.com/)- This should come with a Node JS installation, and is a tool used to install and manage Javacript libraries (such as Express and JQuery)
* [Express JS](http://expressjs.com/en/starter/installing.html)- Library for writing basic web servers
* [JQuery](https://jquery.com/)- Javascript library full of useful web goodies

# Express Back-End Server
A website is made up of a collection of files that can be displayed within your web browser. However, in order to display a website, you need to write a *server*, which is just a program that receives requests and sends responses. When the *server* receives an HTTP (Hyper-Text Transfer Protocol) it will have to do some processing and then send a response. Often, the server will send an HTML file as a response, which then gets displayed as a web page.

### Setting Up Node

First, [install Node](https://nodejs.org/en/). You should be able to run `node -v` in the terminal and it should print out your version of Node. You should also run `npm -v` to ensure that you properly installed the Node Package Manager.

We will begin creating a new project! Make a directory and call it `hello_world`. Inside `hello_world`, make a file called `app.js` with the following Javascript code [(From Node JS)](https://nodejs.org/en/about/):

```
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

Your project directory should look like this:
```
hello_world
  |--app.js
```

Next, while in the `hello_world` folder, run `node app.js`. It should print out a message saying your server is running! In your web browser, type in `http://localhost:3000/` and you should see the text "Hello World"


