# 🌐 REST Architecture

![rest_api](https://github.com/rajkamble21/concepts/assets/70090963/bb6b3c5b-7b26-46d4-acb8-ef8ac4b385ee)

## 📘 Introduction

Representational State Transfer (REST) is a style of software architecture for distributed systems like the web. Restfull apis provide a way to access database resources through server in a secure and easy way. This document will discuss the principles, components, and advantages of REST architecture in detail.

## 📚 Principles of REST


<img src="https://github.com/rajkamble21/concepts/assets/70090963/41b5d5fd-c576-4a4c-9b27-285f229f56ac" alt="RESTAPI" style="width:500px; height:300px;" />

REST is defined by several key principles:

### 1. Client-Server Architecture

In REST, the client and server are separate entities. This separation allows each part to be developed and updated independently. The client handles the user interface, while the server manages the data.

### 2. Statelessness

Each request from a client to a server must contain all the information needed to understand and process the request. The server does not store any client context between requests. This means each request is independent.

### 3. Cacheability

Responses from the server must indicate whether they can be cached by the client. Caching improves performance by reducing the number of interactions between the client and server.

### 4. Layered System

A client cannot tell whether it is connected directly to the end server or to an intermediary along the way. Intermediaries can improve scalability by enabling load balancing and caching.

### 5. Uniform Interface

The uniform interface simplifies and decouples the architecture, allowing each part to evolve independently. It includes the use of standard methods like GET, POST, PUT, DELETE, and a consistent way to access resources.

### 6. Code on Demand (Optional)

Servers can temporarily extend or customize the functionality of a client by transferring executable code. This is an optional constraint in REST.

## 🛠️ Components of REST

<img src="https://github.com/rajkamble21/concepts/assets/70090963/ddea3e6e-d148-446f-9d18-3180b99b24de" alt="RESTAPI" style="width:300%; height:300px;" />

### 1. Resources

Resources are the key abstraction in REST. Each resource is identified by a unique URI. Resources can be documents, images, collections, or non-virtual objects.

### 2. URIs (Uniform Resource Identifiers)

URIs identify resources. Each resource has a unique URI which acts as its address.

### 3. HTTP Methods

RESTful systems use standard HTTP methods to perform operations on resources:
- **GET**: Retrieve a resource.
- **POST**: Create a new resource.
- **PUT**: Update an existing resource.
- **DELETE**: Remove a resource.
- **PATCH**: Apply partial modifications to a resource.
- **HEAD**: Retrieve headers for a resource, without the body.
- **OPTIONS**: Describe the communication options for the resource.
- **CONNECT**: Establish a tunnel to the server identified by the target resource.
- **TRACE**: Perform a message loop-back test along the path to the target resource.


### 4. Representations

Resources are represented in various formats like JSON, XML, HTML, or plain text. Clients interact with resources through these representations.

### 5. Status Codes

HTTP status codes indicate the result of an HTTP request:
- **200 OK**: The request was successful.
- **201 Created**: The resource was successfully created.
- **204 No Content**: The request was successful, but there is no representation to return.
- **400 Bad Request**: The request could not be understood or was missing required parameters.
- **401 Unauthorized**: Authentication failed or user does not have permissions for the requested operation.
- **404 Not Found**: The requested resource could not be found.
- **500 Internal Server Error**: An error occurred on the server.



## 🚀 Example RESTful API

```http
GET /users
POST /users
GET /users/{id}
PUT /users/{id}
DELETE /users/{id}
PATCH /users/{id}
```

## ✅ Advantages of REST

- **Scalability**: Statelessness and the layered system improve scalability.
- **Flexibility**: The uniform interface allows different parts of the system to evolve independently.
- **Performance**: Caching reduces the number of interactions between client and server.
- **Simplicity**: RESTful APIs are easy to understand and use due to their reliance on standard HTTP methods and status codes.

## 📊 REST vs. Other Architectural Styles

REST API is flexible and widely used for web services. GraphQL allows clients to request specific data, and SOAP is highly secure, suitable for enterprise-level applications.

| 🛠️ **Aspect**           | 🌐 **REST API**                  | 🌀 **GraphQL**                        | 🏢 **SOAP**                           |
|-------------------------|-----------------------------------|---------------------------------------|---------------------------------------|
| **Protocol**            | HTTP                              | HTTP                                  | HTTP, SMTP, TCP, more                 |
| **Data Format**         | JSON, XML, etc.                   | JSON                                  | XML                                   |
| **Flexibility**         | Flexible                          | Highly flexible, client specifies     | Less flexible, server-driven          |
| **Complexity**          | Moderate                          | Moderate to high                      | High                                  |
| **Performance**         | Good (over-fetching/under-fetching issues) | High (fetch only needed data)       | Moderate (larger payloads)            |
| **Caching**             | Yes                               | No                                    | No                                    |
| **Versioning**          | URL versioning                    | No versioning, single endpoint        | Uses different services for versions  |
| **Error Handling**      | HTTP status codes                 | Custom error codes                    | SOAP faults                           |
| **Security**            | OAuth, JWT                        | OAuth, JWT                            | WS-Security                           |
| **Use Case**            | Web services, microservices       | Mobile and web applications needing specific data | Enterprise-level applications requiring high security and transactional reliability |



## 📝 Conclusion

RESTful architecture is a powerful and flexible way to design web services. By following its principles and constraints, developers can create scalable, high-performance, and easy-to-maintain systems. Understanding REST is essential for building modern web applications and APIs.

## 📚 References

* [What is REST?](https://www.geeksforgeeks.org/rest-api-introduction/)
* [REST API Introduction](https://restfulapi.net/)
* [REST API vs GraphQL vs SOAP](https://www.geeksforgeeks.org/rest-api-vs-graphql-vs-soap/)
* [REST (REpresentational State Transfer)](https://www.techtarget.com/searchapparchitecture/definition/REST-REpresentational-State-Transfer)


