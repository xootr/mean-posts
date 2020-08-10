# mean-posts

## Prepare

1. install node.js
2. sudo npm install -g @angular/cli
3. ng new mean-posts
4. ng add @angular/material
5. npm install —save express
6. npm install —save-dev nodemon
    1. register in scripts section of the package.json - start:server: “nodemon server.js"
    2. npm run start:server
    3. make sure to add 'const debug = require(“debug”)(“node-angular);' to server.js
7. npm install —save mongoose
8. npm install —save mongoose-unique-validator
9. npm install —save bcryptjs
10. npm install —save jsonwebtoken
11. npm install —save mutler

## Setup the Mongo db connection string using Mongoose in app.js in the backend folder

```javascript
mongoose
    .connect(
        "mongodb+srv://muggles:" +
        process.env.MONGO_ATLAS_PW +
        "@cluster0.3fdhj.mongodb.net/test?retryWrites=true&w=majority"
    )    
    .then(() => {
        console.log("Connected to database!");
    })
    .catch(() => {
        console.log("Connection failed!");
    });
```
    
# Setup configuration for Node.js application in nodemon.js:

{
    "env": {
        "MONGO_ATLAS_PW": "",
        "JWT_KEY": "secret_this_should_be_longer"
    }
}
