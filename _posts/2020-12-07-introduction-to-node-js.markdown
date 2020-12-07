---
layout: post
title:  "Introduction to Node Js"
# date:   2020-12-07 00:48:17 +0530
categories: full stack
---

Hi Everyone,

Hope Everyone Is Doing Well !!

Today's blog is on `Introduction to Node Js`. So we will proceed in following manner.
 Oh! sorry I just wanted to make some prerequisite clear that You should have some basic concept clear about NodeJs not on advanced level but yes just like a begineer. Some prerequiste concepts like `JAVASCRIPT, ES6 features, REQUEST AND RESPONSE, HTTP and HTTPS etc.` (**A blog is comming soon on these concepts too... will update the link here itself.**)
 
 Hope you have installed the Node Js in your system from [Official website of NodeJs](https://nodejs.org/en/ "Official website of NodeJs").

 **We are moving forward on the part of blogs concept !!**
- What is `Node Js` ?
- Working with `NodeJs` 

<hr>
### What is NODE JS ?
Let's go with wikipedia link for [NodeJs Link](https://en.wikipedia.org/wiki/Node.js "NodeJs Link")  so According to Wikipedia, 
> Node.js is an open-source, cross-platform, back-end, JavaScript runtime environment that executes JavaScript code outside a web browser.

OK !! so here we got some new word they are as follows :-
1. open-source :- open source software which are free to use is mostly developed by community developer.
1. cross-platform : - Here cross-platform means it can be used on various cross platform such as `windows, Linux and MacOS`.
1. back-end :- Back-end is mostly defined as the server which interact with database server and also front-end User Interface for communication in Web Application.
1. JavaScript runtime enviornment :- Here runtime enviornment  is Javascript which provided the runtime state for node Js Code base to run over browser with the help of Javascript engine.

So by going through this one thing is clear `NodeJs` can be used freely along with that it's a cross platform which can be used all various platforms OS as well as mostly used to develop backend server inside a Javascript run time enviornment.

By now It is clear Node Js is used to create backend server. Lets dive into the coding part.

[![Enough Theory Code Pls](https://www.meme-arsenal.com/memes/71ddbfec6c9c22cc556d896f66deecfb.jpg "Enough Theory Code Pls")](https://www.meme-arsenal.com/memes/71ddbfec6c9c22cc556d896f66deecfb.jpg "Enough Theory Code Pls")

Oook let's dive into code :-
Just follow along me ....

`Grab your self a IDE` any IDE `atom` / `VScode` there are hell no of IDE one you preffer. `I will use Vscode for myself`.  That's my magic wand [WHERE ALL MAGIC HAPPENS].

-----------------
Open your terminal `I am using windows so mine is cmd you can use the default terminal of you OS`
Follow along me
- `mkdir nodeSimpleServer` // make a directory command
- `cd nodeSimpleServer` // change  your directory
- `npm init -y` // create package.json file for your very first nodeJs project
- Open the directory of your project in any of your fav browser.` I will open that in VScode`
- If your package.json file is created you will be able to see following content their.

```json
{
  "name": "nodeSimpleServer",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

```

Ok let's go line by line :
there exist some property of Json value which we are going to discuss here

| Property  | What does that means  |
| :------------: | :------------: |
| name  | Name of the backend application server  |
| version  | Here the default version of the server is stated  |
| description  | Any description the developer wants to give for the server  |
| main  |  Most Important and also the entry point of the server. Will discuss about this a bit later. |
| scripts  | All the terminal commands are written here. Will discuss about this a bit later.  |
| keywords  | Array of string which is used for SEO (not compulsory to state)  |
| author | Author of the code base. You can give your name but not compulsory.  |
| license | Licence for the code base for programming community.  |

- Ok lets again move to our IDE and create a new file inside the root directory with name `index.js`
So now just go back to the package.json file you are able to see `index.js` filename is written in a property named as `main` which depict that any code execution for your node server will start from this file.
----
NOTE : -
If you are creating a new folder and then add the `index.js` file in that scenerio you need to pass the relative path of that file inside the `main` property of `package.json` file. For example If realtive path of `index.js file` is `start\index.js` you need to add path as `"main" : 'start\index.js'`

----
Now we will code `index.js` to create a very basic `Hello World` server.
Inside the `index.js` file add following code.

```javascript
// STEP : 1 : : get a http package from default node package
var http = require('http');

// STEP : 2 : : create a server with http package.
http.createServer(function (req, res) {
    // STEP : 3 : : response to the client
    res.write('Hello World!');
    // STEP : 4 : : End response
    res.end();
}).listen(8080); // STEP : 5 :: Enter which port to listen so now on 8080 you can hit your server to get the result.
```
---
[![Simple node Server with http](https://res.cloudinary.com/dxbshzleh/image/upload/v1607361217/webobite.blog/7_dec_2020/basic_server_code_gbpi4k.png "Simple node Server with http")](https://res.cloudinary.com/dxbshzleh/image/upload/v1607361217/webobite.blog/7_dec_2020/basic_server_code_gbpi4k.png "Simple node Server with http")
Once you are done with the code base lets move on the step how to run this server. The very easy way to run a the node server is by this command
`node index.js` 
Type this command in your terminal and press enter. You can see your terminal hang's up. No worry dude !! We made it Congratulations !! Now your server is live at http://localhost:8080/. You can click on this link and view the result as `Hello World` on the browser.
-----

[![Output of Hello World Server](https://res.cloudinary.com/dxbshzleh/image/upload/v1607362775/webobite.blog/7_dec_2020/output_ki3jeh.png "Output of Hello World Server")](https://res.cloudinary.com/dxbshzleh/image/upload/v1607362775/webobite.blog/7_dec_2020/output_ki3jeh.png "Output of Hello World Server")

-----
For closing your server you can go to terminal and do `crtl + c` . your server will close.
Let's go to package.json code once again. This time we will edit  the `scripts` property in package.json.
For running any script from the terminal inside any node project we add a custom script with its respective command and we will be able to run that scpecific script accordingly.

Inside `scripts` property we already have a `test` script. Now we will add one more script here. 

```json
{
  "name": "nodeSimpleServer",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

```
so now we have added `start` server script and now when we type in our terminal `npm run start` it will internally run the command as `node index.js` in the terminal.
(It is not compulsory but it's a good practise to add the same in your code base and then use your code base with the help of scripts defined in `package.json`)
<hr>

There are lot many thing to cover in Node and NPM.  You can follow the Official docs of [Latest NodeJs Version 13](https://nodejs.org/docs/latest-v13.x/api/ "Latest NodeJs Version 13") at the time I am writing this blog.

Thank You !!

Will be back with some other blog.

Kindly give your feedback over my mail or on my instagram
Will be happy connect with you on twitter too.

With Regards
Subham

