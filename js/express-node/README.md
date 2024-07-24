# Different type of web applications ( Frontend & Backend )

Web applications can be broadly classified into different types based on their architecture, functionality, and the technologies used for their frontend and backend development. Here’s an overview of the main types:

## Frontend Web Applications

### 1. Static Websites
- **Description**: Contain fixed content. Each page is coded in HTML and displays the same information to every visitor.
- **Technologies**: HTML, CSS, JavaScript.
- **Examples**: Personal blogs, portfolios, documentation sites.

### 2. Single Page Applications (SPAs)
- **Description**: Load a single HTML page and dynamically update the content as the user interacts with the app. They offer a more seamless and interactive user experience.
- **Technologies**: Frameworks like React, Angular, Vue.js.
- **Examples**: Gmail, Google Maps, Trello.

### 3. Progressive Web Apps (PWAs)
- **Description**: Combine the best of web and mobile apps. They are web apps that use modern web capabilities to deliver an app-like experience to users.
- **Technologies**: Service Workers, Web App Manifests, frameworks like React, Angular, Vue.js.
- **Examples**: Twitter Lite, Pinterest, Starbucks.

## Backend Web Applications

### 1. Server-Side Rendered (SSR) Applications
- **Description**: The server generates the full HTML for each page request. This can lead to better performance and SEO as the complete page is delivered to the browser.
- **Technologies**: Node.js (Express), Ruby on Rails, Django, Flask.
- **Examples**: Traditional websites, content-heavy websites like news sites.

### 2. RESTful APIs
- **Description**: Provide endpoints for different types of requests (GET, POST, PUT, DELETE) to interact with resources on the server. They are stateless and can be used by multiple clients.
- **Technologies**: Node.js (Express), Django, Flask, Ruby on Rails.
- **Examples**: Backend services for mobile apps, SPAs.

### 3. GraphQL APIs
- **Description**: Allow clients to request exactly the data they need, reducing the amount of data transferred over the network. It provides a more flexible and efficient alternative to REST.
- **Technologies**: Apollo Server, GraphQL Yoga, Relay.
- **Examples**: Data-driven applications, complex queries from multiple sources.

### 4. Microservices
- **Description**: An architectural style that structures an application as a collection of loosely coupled services. Each service is self-contained and should implement a single business capability.
- **Technologies**: Docker, Kubernetes, Spring Boot, Node.js.
- **Examples**: Large-scale applications like e-commerce platforms, cloud services.

### 5. Serverless Applications
- **Description**: Applications where the server management and capacity planning are handled by the cloud provider. The code runs in stateless compute containers that are event-triggered.
- **Technologies**: AWS Lambda, Google Cloud Functions, Azure Functions.
- **Examples**: Real-time data processing, chatbots, IoT backend services.

---

# What is HTTP

HTTP, or Hypertext Transfer Protocol, is the foundation of data communication on the World Wide Web. It's an application layer protocol used for transmitting hypermedia documents, such as HTML. Here’s an in-depth look at what HTTP is:

## What is HTTP?

### Definition
HTTP is a protocol used for transferring hypertext requests and information on the internet. It is the protocol used by web browsers and servers to communicate.

### Key Features
1. **Stateless**: Each HTTP request from a client to server is independent; the server does not retain any information about previous requests.
2. **Request-Response Model**: HTTP operates on a simple request-response cycle. The client sends a request, and the server sends back a response.
3. **Human-readable**: The protocol is designed to be simple and readable by humans. Requests and responses are structured in a way that can be easily understood.

### Components of an HTTP Request
1. **Request Line**: Contains the method (e.g., GET, POST), the resource URL, and the HTTP version.
   - Example: `GET /index.html HTTP/1.1`
2. **Headers**: Provide metadata about the request, such as content type, user agent, and host.
   - Example: `Host: www.example.com`
3. **Body**: Contains the data being sent to the server (used mainly in POST and PUT requests).

### Components of an HTTP Response
1. **Status Line**: Contains the HTTP version, a status code, and a reason phrase.
   - Example: `HTTP/1.1 200 OK`
2. **Headers**: Provide metadata about the response, such as content type, content length, and server type.
   - Example: `Content-Type: text/html`
3. **Body**: Contains the data being sent back to the client (e.g., HTML code of a webpage).

### Common HTTP Methods
1. **GET**: Requests a resource from the server.
2. **POST**: Sends data to the server to create a new resource.
3. **PUT**: Sends data to the server to update an existing resource.
4. **DELETE**: Requests the server to delete a resource.
5. **HEAD**: Similar to GET, but it transfers the status line and header section only.
6. **OPTIONS**: Describes the communication options for the target resource.
7. **PATCH**: Applies partial modifications to a resource.

### HTTP Status Codes
1. **1xx (Informational)**: Request received, continuing process.
   - Example: `100 Continue`
2. **2xx (Success)**: The action was successfully received, understood, and accepted.
   - Example: `200 OK`
3. **3xx (Redirection)**: Further action must be taken to complete the request.
   - Example: `301 Moved Permanently`
4. **4xx (Client Error)**: The request contains bad syntax or cannot be fulfilled.
   - Example: `404 Not Found`
5. **5xx (Server Error)**: The server failed to fulfill a valid request.
   - Example: `500 Internal Server Error`

---

# Differentiate parts of URL in the given example
`<https://localhost:5000/users/profile?username=mountblue>`

A URL (Uniform Resource Locator) consists of several parts that define the location and method for retrieving resources over the internet. Here’s a breakdown of the different parts of the given URL `https://localhost:5000/users/profile?username=mountblue`:

### Breakdown of the URL

1. **Scheme/Protocol**: `https`
   - **Description**: Specifies the protocol used to access the resource. In this case, HTTPS (Hypertext Transfer Protocol Secure) is used, which indicates that the communication is encrypted.
   - **Example**: `https`

2. **Hostname**: `localhost`
   - **Description**: Indicates the domain name or IP address of the server where the resource is hosted. `localhost` is a hostname that refers to the local machine.
   - **Example**: `localhost`

3. **Port**: `5000`
   - **Description**: Specifies the port number on the server to connect to. If omitted, the default port for the scheme is used (80 for HTTP and 443 for HTTPS).
   - **Example**: `5000`

4. **Path**: `/users/profile`
   - **Description**: Specifies the path to the resource on the server. This often represents directories and files on the server.
   - **Example**: `/users/profile`

5. **Query String**: `?username=mountblue`
   - **Description**: Contains data to be sent to the server, usually in key-value pairs. The query string follows a `?` and can include multiple parameters separated by `&`.
   - **Example**: `username=mountblue`

### Full URL Analysis
- **Scheme/Protocol**: `https`
  - This part tells the browser to use the HTTPS protocol for secure communication.
  
- **Hostname**: `localhost`
  - Indicates that the resource is on the local machine, often used during development and testing.

- **Port**: `5000`
  - Specifies that the web server is listening on port 5000. This is often used in development environments where servers run on non-default ports.

- **Path**: `/users/profile`
  - The specific endpoint on the server. It generally maps to a route in a web application that handles user profile data.

- **Query String**: `?username=mountblue`
  - Provides additional parameters for the request. Here, it includes a single parameter `username` with the value `mountblue`, which can be used by the server to filter or process the request.

### Diagram
Here's a visual representation of the URL components:

```
https://localhost:5000/users/profile?username=mountblue
|     |        |      |           |         |
|     |        |      |           |         `- Query string: ?username=mountblue
|     |        |      |           |
|     |        |      |           `- Path: /users/profile
|     |        |      |
|     |        |      `- Port: 5000
|     |        |
|     |        `- Hostname: localhost
|     |
`- Scheme/Protocol: https
```

---

# What are few commonly used HTTP request methods?

HTTP request methods are used to perform various actions on the resources identified by URLs. Here are a few commonly used HTTP request methods:

## Commonly Used HTTP Request Methods

### 1. GET
- **Purpose**: Retrieve data from the server.
- **Usage**: When you want to fetch data without making any changes to it.
- **Characteristics**:
  - Can be cached.
  - Remains in the browser history.
  - Can be bookmarked.
  - Should not be used for sensitive data as it is exposed in the URL.
- **Example**: Retrieving a webpage or an image.
  - `GET /index.html HTTP/1.1`

### 2. POST
- **Purpose**: Send data to the server to create a new resource.
- **Usage**: When submitting form data or uploading a file.
- **Characteristics**:
  - Cannot be cached.
  - Does not remain in the browser history.
  - Cannot be bookmarked.
  - Data is sent in the body of the request.
- **Example**: Submitting a registration form.
  - `POST /users/register HTTP/1.1`

### 3. PUT
- **Purpose**: Send data to the server to update an existing resource.
- **Usage**: When updating user details or modifying data on the server.
- **Characteristics**:
  - Idempotent (multiple identical requests have the same effect as a single request).
  - Data is sent in the body of the request.
- **Example**: Updating user profile information.
  - `PUT /users/123 HTTP/1.1`

### 4. DELETE
- **Purpose**: Remove a resource from the server.
- **Usage**: When deleting a user or a specific data entry.
- **Characteristics**:
  - Idempotent.
  - Can be used to delete a specific resource identified by the URL.
- **Example**: Deleting a user account.
  - `DELETE /users/123 HTTP/1.1`

### 5. PATCH
- **Purpose**: Apply partial modifications to a resource.
- **Usage**: When updating only specific fields of a resource.
- **Characteristics**:
  - Not idempotent by default, but can be designed to be idempotent.
  - Data is sent in the body of the request, specifying the changes.
- **Example**: Updating the email address of a user.
  - `PATCH /users/123 HTTP/1.1`

### 6. HEAD
- **Purpose**: Retrieve the headers for a resource, without the body.
- **Usage**: When checking what a GET request will return before actually making the GET request.
- **Characteristics**:
  - Used to obtain metadata about the resource.
  - No response body is returned.
- **Example**: Checking the last-modified date of a resource.
  - `HEAD /index.html HTTP/1.1`

### 7. OPTIONS
- **Purpose**: Describe the communication options for the target resource.
- **Usage**: Used by clients to determine the capabilities of a server, such as allowed HTTP methods.
- **Characteristics**:
  - Returns information about the communication options available.
  - Can be used to check CORS (Cross-Origin Resource Sharing) permissions.
- **Example**: Checking which HTTP methods are supported by a server.
  - `OPTIONS /users HTTP/1.1`

---

# What are different HTTP status codes & why do we use them?

HTTP status codes are issued by a server in response to a client's request made to the server. They are grouped into five categories based on their first digit, and each category conveys a different meaning about the response. Here’s an overview of the different HTTP status codes and why they are used:

## Categories of HTTP Status Codes

### 1. 1xx: Informational
- **Purpose**: Indicate that the request has been received and understood, and that the process is continuing.
- **Common Codes**:
  - **100 Continue**: The client should continue with its request.
  - **101 Switching Protocols**: The server is switching protocols as requested by the client.

### 2. 2xx: Success
- **Purpose**: Indicate that the request was successfully received, understood, and accepted.
- **Common Codes**:
  - **200 OK**: The request was successful, and the server has returned the requested data.
  - **201 Created**: The request was successful, and a new resource was created.
  - **202 Accepted**: The request has been accepted for processing, but the processing is not complete.
  - **204 No Content**: The request was successful, but there is no content to send in the response.

### 3. 3xx: Redirection
- **Purpose**: Indicate that further action needs to be taken by the user agent to fulfill the request.
- **Common Codes**:
  - **301 Moved Permanently**: The requested resource has been permanently moved to a new URL.
  - **302 Found**: The requested resource has been temporarily moved to a different URL.
  - **304 Not Modified**: The resource has not been modified since the last request, so the client can use its cached version.

### 4. 4xx: Client Errors
- **Purpose**: Indicate that there was a problem with the request made by the client.
- **Common Codes**:
  - **400 Bad Request**: The server could not understand the request due to invalid syntax.
  - **401 Unauthorized**: Authentication is required, and the client must authenticate itself to get the requested response.
  - **403 Forbidden**: The client does not have access rights to the content, so the server is refusing to give the requested resource.
  - **404 Not Found**: The server cannot find the requested resource.
  - **405 Method Not Allowed**: The request method is not supported for the requested resource.

### 5. 5xx: Server Errors
- **Purpose**: Indicate that the server failed to fulfill a valid request.
- **Common Codes**:
  - **500 Internal Server Error**: The server encountered a situation it doesn’t know how to handle.
  - **501 Not Implemented**: The server does not support the functionality required to fulfill the request.
  - **502 Bad Gateway**: The server, while acting as a gateway or proxy, received an invalid response from an inbound server.
  - **503 Service Unavailable**: The server is not ready to handle the request, often due to temporary overloading or maintenance.
  - **504 Gateway Timeout**: The server, while acting as a gateway or proxy, did not receive a timely response from an upstream server.

## Why We Use HTTP Status Codes

### 1. Communication
- **Description**: Status codes provide a standardized way for the server to communicate the outcome of a client's request. They inform the client whether the request was successful, if further action is needed, or if an error occurred.

### 2. Debugging and Monitoring
- **Description**: Status codes help developers and system administrators identify and troubleshoot issues with web applications. For example, a `404 Not Found` error indicates that the requested resource does not exist, while a `500 Internal Server Error` points to a problem on the server side.

### 3. Automation
- **Description**: Automated systems, such as web crawlers and APIs, rely on status codes to determine how to handle responses. For example, a `301 Moved Permanently` response will prompt a crawler to update its records with the new URL.

### 4. User Experience
- **Description**: Status codes can be used to provide meaningful error messages to users. For instance, a `401 Unauthorized` response can prompt a user to log in, while a `403 Forbidden` message can inform them of access restrictions.

---

# What are the different ways  of passing information over HTTP?

There are several ways to pass information over HTTP, depending on the requirements of the application and the type of data being transmitted. Here are the most common methods:

### 1. **Query Parameters**
   - **Description**: Data is appended to the URL as a query string.
   - **Example**: `GET /search?query=example`
   - **Usage**: Ideal for non-sensitive data, pagination, and search parameters.
   - **Limitations**: Limited length and not suitable for sensitive information.

### 2. **Request Body**
   - **Description**: Data is included in the body of the HTTP request.
   - **Types**:
     - **Form Data**: Commonly used in HTML forms.
       - **Content-Type**: `application/x-www-form-urlencoded`
       - **Example**:
         ```http
         POST /submit
         Content-Type: application/x-www-form-urlencoded

         name=John&age=30
         ```
     - **Multipart Form Data**: Used for file uploads.
       - **Content-Type**: `multipart/form-data`
       - **Example**:
         ```http
         POST /upload
         Content-Type: multipart/form-data; boundary=----WebKitFormBoundary

         ------WebKitFormBoundary
         Content-Disposition: form-data; name="file"; filename="example.txt"
         Content-Type: text/plain

         (file content)
         ------WebKitFormBoundary--
         ```
     - **JSON**: Commonly used in APIs.
       - **Content-Type**: `application/json`
       - **Example**:
         ```http
         POST /api/data
         Content-Type: application/json

         {
           "name": "John",
           "age": 30
         }
         ```
     - **XML**: Less common but still used in some APIs.
       - **Content-Type**: `application/xml`
       - **Example**:
         ```http
         POST /api/data
         Content-Type: application/xml

         <person>
           <name>John</name>
           <age>30</age>
         </person>
         ```

### 3. **Headers**
   - **Description**: Custom headers can be used to pass information.
   - **Example**:
     ```http
     GET /resource
     Custom-Header: value
     ```
   - **Usage**: Often used for authentication tokens, content negotiation, and custom application data.

### 4. **Cookies**
   - **Description**: Data is stored in cookies and sent with each HTTP request to the server.
   - **Example**:
     ```http
     GET /resource
     Cookie: sessionId=abc123
     ```
   - **Usage**: Session management, user preferences, and tracking.

### 5. **Path Parameters**
   - **Description**: Data is included as part of the URL path.
   - **Example**: `GET /users/123`
   - **Usage**: Used for identifying resources, such as user IDs, product IDs, etc.

### 6. **WebSockets**
   - **Description**: Provides full-duplex communication channels over a single TCP connection.
   - **Usage**: Real-time applications such as chat, live updates, and notifications.
   - **Example**:
     ```javascript
     const socket = new WebSocket('ws://example.com/socket');
     socket.onmessage = function(event) {
       console.log('Message from server ', event.data);
     };
     ```

### 7. **Server-Sent Events (SSE)**
   - **Description**: Allows servers to push data to web clients over a single HTTP connection.
   - **Usage**: Real-time updates like news feeds, stock prices, and notifications.
   - **Example**:
     ```javascript
     const eventSource = new EventSource('/events');
     eventSource.onmessage = function(event) {
       console.log('New event: ', event.data);
     };
     ```
---

# What is the default status code sent with each response?

##200

---

# What is content-length property in response headers?

The `Content-Length` property in response headers is an HTTP header field that indicates the size of the body of the response, in bytes. This header is important for both the client and the server because it tells the client how much data to expect from the server.

### Key Points About `Content-Length`:

1. **Exact Size**:
   - The value of `Content-Length` is the exact number of bytes in the body of the response.
   - For example, if a server sends a response body that is 1234 bytes long, the header will look like this:
     ```http
     Content-Length: 1234
     ```

2. **Usage**:
   - It helps the client know when the response has been fully received.
   - It allows clients to allocate the correct amount of memory for the response body.
   - It enables clients to detect and handle incomplete responses or potential issues during transmission.

3. **Chunked Transfer Encoding**:
   - When the server uses chunked transfer encoding, the `Content-Length` header is not used. Instead, the response body is sent in chunks, and each chunk is preceded by its size in bytes.
   - Example of a chunked response:
     ```http
     Transfer-Encoding: chunked

     4
     Wiki
     5
     pedia
     0
     ```

4. **Examples**:
   - **Text Response**:
     ```http
     HTTP/1.1 200 OK
     Content-Type: text/plain
     Content-Length: 13

     Hello, world!
     ```
   - **JSON Response**:
     ```http
     HTTP/1.1 200 OK
     Content-Type: application/json
     Content-Length: 27

     {"name":"John","age":30}
     ```

5. **Importance for Persistent Connections**:
   - In HTTP/1.1, persistent connections (or keep-alive connections) allow the same TCP connection to be used for multiple requests/responses.
   - Knowing the length of the response helps in determining the end of the current response and the beginning of the next one.

### Handling Content-Length:

- **Server-Side**:
  - The server is responsible for calculating and setting the `Content-Length` header.
  - In many server frameworks, this is done automatically, but it can also be set manually if needed.
- **Client-Side**:
  - The client reads the `Content-Length` header to understand how much data it should read from the connection.
  - This is crucial for proper handling of the response and for determining if the entire response has been received.

---

# What is  the difference between path and pathname in requested URL?

The terms "path" and "pathname" in the context of a requested URL often refer to similar concepts, but they can have slightly different meanings depending on the context in which they're used. Let's break down each term and their typical usage:

### Path
- **Definition**: The "path" typically refers to the part of the URL that comes after the domain name and before any query parameters or fragment identifiers.
- **Example**: In the URL `https://example.com/products/view?id=123#section`, the path is `/products/view`.
- **Usage**: The path is used by the server to determine which resource is being requested.

### Pathname
- **Definition**: The "pathname" usually refers to the same part of the URL as the "path" and includes the path but excludes the domain, query parameters, and fragment identifiers. It is a property available in the `Location` interface of the Web API.
- **Example**: Using the same URL `https://example.com/products/view?id=123#section`, the pathname is also `/products/view`.
- **Usage**: The pathname is commonly used in client-side scripting (like JavaScript) to retrieve the path part of the current URL.

### Differences in Contexts:
1. **URL Parsing (General Use)**:
   - In general URL parsing, "path" and "pathname" are often used interchangeably and refer to the same part of the URL.

2. **Web APIs (JavaScript)**:
   - In the context of the Web APIs provided by browsers, `pathname` is a property of the `Location` object. For example, `window.location.pathname` gives you the path part of the current URL.
   - Example:
     ```javascript
     console.log(window.location.pathname); // Outputs: /products/view
     ```

3. **Terminology Consistency**:
   - While "path" is a broader term that can be used in various contexts (server-side routing, URL structure, etc.), "pathname" is more specific to the Web API context and is a standardized term in the JavaScript `Location` object.

### Summary
- **Path**: General term used in URLs to refer to the part after the domain and before any query parameters or fragment identifiers. Used broadly in both server-side and client-side contexts.
- **Pathname**: Specific term often used in client-side JavaScript to refer to the same part of the URL as the path, accessible via `window.location.pathname`.

---

# what is Node.js ?

Node.js is an open-source, cross-platform, JavaScript runtime environment that allows developers to run JavaScript code outside of a web browser. It was created by Ryan Dahl in 2009, and it has become a popular choice for building server-side and networking applications. Here are some key points about Node.js:

### Key Features of Node.js:

1. **Event-Driven and Non-Blocking I/O**:
   - Node.js uses an event-driven, non-blocking I/O model, making it efficient and suitable for real-time applications. This means it can handle many operations simultaneously without waiting for any single operation to complete.

2. **JavaScript Everywhere**:
   - With Node.js, developers can use JavaScript for both client-side and server-side scripting, allowing for a more consistent and unified development stack.

3. **Built on V8**:
   - Node.js is built on Google's V8 JavaScript engine, which compiles JavaScript into native machine code, offering high performance.

4. **NPM (Node Package Manager)**:
   - Node.js comes with NPM, the largest ecosystem of open-source libraries and modules, making it easy to include and manage dependencies in projects.

5. **Single-Threaded but Highly Scalable**:
   - Node.js operates on a single-threaded event loop but can handle many concurrent connections efficiently due to its non-blocking I/O operations.

### Common Uses of Node.js:

1. **Web Servers and APIs**:
   - Node.js is widely used for building web servers and RESTful APIs. Its non-blocking nature allows it to handle multiple requests efficiently.

2. **Real-Time Applications**:
   - Applications that require real-time communication, such as chat applications, live streaming, and online gaming, benefit from Node.js's event-driven architecture.

3. **Microservices**:
   - Node.js is often used to develop microservices architectures due to its lightweight and modular nature.

4. **Command-Line Tools**:
   - Many command-line tools and utilities are built with Node.js because of its fast execution and the vast ecosystem of packages available through NPM.

### Example of a Simple Node.js Server:

```javascript
// Load the http module to create an HTTP server
const http = require('http');

// Configure the HTTP server to respond with "Hello World" to all requests
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

// Listen on port 3000
const PORT = 3000;
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`);
});
```

### Popular Frameworks and Libraries for Node.js:

1. **Express.js**: A minimal and flexible Node.js web application framework that provides a robust set of features for building web and mobile applications.
2. **Koa.js**: Created by the same team behind Express, Koa aims to be a smaller, more expressive, and more robust foundation for web applications and APIs.
3. **Socket.io**: Enables real-time, bidirectional, and event-based communication between web clients and servers.
4. **NestJS**: A framework for building efficient, reliable, and scalable server-side applications, heavily inspired by Angular.

---

# explain how Node.js executes asynchrounous I/O operations?

