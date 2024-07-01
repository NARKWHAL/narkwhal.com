# Summary
Node.js is the way to run Javascript on the backend. Below is the barebones of a web server

```javascript
//require the HTTP Server
const http = require('http');

// Build the server and have it log on console the request coming in
const server = http.createServer((req, res) => {
	console.log(req)
});

// Keep the server listening on port 3000 on localhost
server.listen(3000);
```

Node runs on a single javascript thread that delegates tasks to a worker pool to make sure that there is no blocking. The loop of the thread is essentially like a train that goes around in a circle and picks up the worker nodes when their tasks are done.

