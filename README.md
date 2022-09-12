# Exercise (Instructions): Introduction to Express

In this exercise, you will make use of the Express framework to implement similar functionality as implemented by the HTTP module based servers in the previous exercise. At the end of this exercise, you will be able to:

- Implement a simple web server using Express framework

- Implement a web server that serves static content

### A Simple Server using Express

- Create a folder named node-express in the NodeJS folder and move to that folder.

- Copy the public folder from node-http to this folder.

- At the prompt, type the following to initialize a package.json file in the node-express folder:

> ``` npm init ```

- Accept the standard defaults suggested until you end up with a ``` package.json ```  file containing the following:

```{
  "name": "node-express",
  "version": "1.0.0",
  "description": "Node Express Examples",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node index"
  },
  "author": "Ajay Dhangar",
  "license": "ISC"
}
```

- Then, install the Express framework in the folder by typing the following at the prompt:

> ``` npm install express@4.16.3 --save ```

- Create a file named ```.gitignore ``` and add the following to it:

> ``` node_modules ```

- Create a file named ``` index.js ``` and add the following code to it:

```
const express = require('express'),
 http = require('http');

const hostname = 'localhost';
const port = 3000;

const app = express();

app.use((req, res, next) => {
  console.log(req.headers);
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/html');
  res.end('<html><body><h1>This is an Express Server</h1></body></html>');

});

const server = http.createServer(app);

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

```

- Start the server by typing the following at the prompt, and then interact with the server:

> ``` npm start ```

- Initialize a Git repository, add the files and do a Git commit with the message "Express Example".

### Serving Static Files

- Install morgan by typing the following at the prompt. Morgan is used for logging purposes:


>  ```    npm install morgan@1.9.0 --save   ```

- Update ``` index.js ``` as follows:

```
const morgan = require('morgan');

app.use(morgan('dev'));

app.use(express.static(__dirname + '/public'));
```

- Start the server and interact with it and observe the behavior.

- Do a Git commit with the message "Express Serve Static Files".

### Conclusions

In this exercise you learnt to use the Express framework to design and implement a web server.



