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

