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

