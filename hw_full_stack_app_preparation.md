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
server.js Line: 19 and create_router.js

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
There is a folder called services that is new. The client is responsible for rendering the app and getting information from the server. The server holds the routes to access data and the database.

3. What are the the responsibilities of server.js?
To setup the connections between all the files within the server folder.

4. What are the responsibilities of the `gamesRouter`?
It holds the routes to access the data from the database.

5. What process does the the client (front-end) use to communicate with the server?
It uses mounted functions in GamesGrid.vue that access GamesService.js where the requests to the server are stored with fetch requests for the different type of methods e.g. post, delete.

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
It can take an object that contains data on the type of request to the server.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
It uses the get("/"), post("/"), delete("/:id") requests.

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
To take full advantage of ES6 but it also has backwards compatibility with most older versions. It also allows asynchronous interaction between the client and and the server. It does all the work that was done in the terminal in the code.
## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

Because that is a unique id that is saved with each data entry to allow access and to update and delete a specify entry. 



Add to your diagram the dataflow for removing a game.
