# Task  
This comprehensive task integrates knowledge from various modules of the course.  

## Your Goal  
Create a web application that interacts with a server via sockets and can store information in a MongoDB database.  

### In this practical task, you will solidify these skills:  

**1. Working with an HTTP Server:**  
- Build a web application in Python without using web frameworks.  
- Handle routing and manage static resources.  

**2. Working with Sockets:**  
- Implement a basic Socket server to process data.  
- Use either UDP or TCP protocol for communication between the web app and the server.  

**3. Using Docker:**  
- Create a Docker container for the web app and the Socket server.  
- Write a Dockerfile and docker-compose.yaml to automate deployment.  

**4. Working with MongoDB:**  
- Save data to a MongoDB database.  
- Create records in a format that has real-world application value.  

---

## Technical Task  

You must create the simplest web application without using a web framework.  

### Instructions and Requirements:  

- Create a web app with routing for two HTML pages: `index.html` and `message.html`.  
- Handle static resources: `style.css`, `logo.png`.  
- Process the form on the `message.html` page.  
- Return an `error.html` page for `404 Not Found` errors.  
- The HTTP server must run on port `3000`.  

---

### Working with the Form and Socket Server  

1. Enter data into the form.  
2. The data is sent to the web app, which forwards it to the Socket server for processing using either the **UDP** or **TCP** protocol.  
3. The Socket server converts the received byte string into a dictionary and stores it in the MongoDB database.  

### MongoDB Document Format:  

```json
{
  "date": "2022-10-29 20:20:58.020261",
  "username": "krabaton",
  "message": "First message"
},
{
  "date": "2022-10-29 20:21:11.812177",
  "username": "Krabat",
  "message": "Second message"
}
```

The **"date"** key for each message is the time the message was received: `datetime.now()`.  
Each new message from the web application must be added to the database with the time of receipt.  

## Acceptance Criteria:

- The web application is created in a single file `main.py`. The HTTP server and Socket server are launched in separate processes.  
- A `Dockerfile` is created, and the application is launched as a Docker container.  
- A `docker-compose.yaml` file is written with configurations for the application and MongoDB.  
- Docker Compose is used to build the environment, and the `docker-compose up` command is used to start it.  
- Data is saved outside the container using the `volumes` mechanism.  
- Static resources (`style.css`, `logo.png`) are processed.  
- A 404 Not Found error returns the `error.html` page.  
- The form is handled as per the above requirements.  
- The MongoDB document format meets the specified criteria.  

