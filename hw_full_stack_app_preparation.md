# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using Vue, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
**A. create_router.js is responsible for defining the routes which would then be created in server.js by calling createRouter method.**

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
**A. Client is responsible for holding all files relating to the front end of the app. Server is the back end files of the app.**

3. What are the the responsibilities of server.js?
**A. The responsibilities are to listen to a port for the back end to pass information to, call the collection in the db we are trying to create routes for and finally call the create_router.js file so it can create the routes and use them.**

4. What are the responsibilities of the `gamesRouter`?
**A. This is the variable that stores the function createRouter which takes the db collection as an argument. This variable is referenced when calling app.use to use the routes.**

5. What process does the the client (front-end) use to communicate with the server?
**A. The front end uses a fetch method to communicate with server.**

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
**A. The second argument the fetch method takes is an object that initialises options such as the type of the request method you are trying to use. In this app it is used to define the request method, what file type we want the body parsed into (JSON) and to set the headers for the request.**

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
**A. 'http://localhost:3000/api/games/'**

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
**A. The driver provides call-back and promise-based interaction with MongoDB so that ES6 js features can be used.**

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?
**A. the ObjectId class creates a string representation of a db item id, which then has a variety of methods you can call on it. In this app it is being used to compare an id that is passed in with by params and find that id in the db.**


Add to your diagram the dataflow for removing a game.
