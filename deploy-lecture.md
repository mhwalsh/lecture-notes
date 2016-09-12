## Intro to Deployment

### What are the properties of server code? How is it different from client code?

- Runs continuously, waiting for requests. Similar to event driven programming on the client side. 
- Often a good opportunity to bring up the different technologies that are used on the frontend vs the backend.

### Where can we run server code?
- locally - localhost, ip addresses, for development, the browser on our computer is talking to a local port that is running our server.
- someone's computer somewhere - within the local area network of prime we should be able to hit our cohortmates computers. Highlevel discussion of the internet can happen here. This won't succeed from home or elsewhere.
- a sever somewhere - on the internet, tools to do this, we will use heroku.
	- ‘in the cloud’ - I like to break down this phrase, since we hear it so frequently in society these days.

### What is a URL
If it fits, I have broken down what a URL is during this talk. Go to the googles for an example or pictograph. It comes up when we discuss the different between something on the internet and something running locally.

### What does deploy mean?
- deploy means literally put it out on the internet where is it available to anyone.
- https://www.heroku.com/ is one tool to do this. It is free for small apps, but even production code trusts heroku.

### But our code is all together?
- In the past I have found that students are confused because both the client side and server side code is stored in the same repository. This is an opportunity to break down the idea of '*full stack*' and carefully walk through how the server serves or hands the browser the code it should run. And outline how the browser requests any script tag files that the browser might need when it renders the html.
   
### How to install Heroku and use it?
- https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction
- install the heroku tool belt or cmd line tool. Now called heroku CLI.
- create a heroku account
- login via the cmd line
- check node, npm and git are installed and are the correct version
- cd into directory where code is
- make necessary code changes, noted below
- heroku create 
-  Show git remote -v after heroku create
- git push heroku master
- has to be a master branch 

##### Necessary Code Changes:
1. Port declaration 
2. npm start script must be declared

```
//Special code for heroku port assignment
var portDecision = process.env.PORT || 3000;

var server = app.listen(portDecision, function(){
       var port = server.address().port;
       console.log('Listening for requests on ports:', port);
});
```

### Walk through
- I do this on a project they have seen this week. Likely Dev's code forked from the intro to node/express lectures.
- Have a classmate spin up a project, find their ip address and try hitting their code. Only works because we are within the same network, but still helpful to illustrate the point.


### Corresponding Assignment
- Heroku Solo Challenge: [https://github.com/mhwalsh/heroku-deploy-solo](https://github.com/mhwalsh/heroku-deploy-solo)