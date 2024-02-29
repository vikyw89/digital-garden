---
{"dg-publish":true,"permalink":"/rpc-vs-rest/"}
---

src:https://aws.amazon.com/compare/the-difference-between-rpc-and-rest/

## What's the difference between RPC and REST?

Remote Procedure Call (RPC) and REST are two architectural styles in API design. APIs are mechanisms that enable two software components to communicate with each other using a set of definitions and protocols. Software developers use previously developed or third-party components to perform functions, so they don’t have to write everything from scratch. RPC APIs allow developers to call remote functions in external servers as if they were local to their software. For example, you can add chat functionality to your application by remotely calling messaging functions on another chat application. In contrast, REST APIs allow you to perform specific data operations on a remote server. For example, your application could insert or modify employee data on a remote server by using REST APIs.

## What are the similarities between RPC and REST?

Remote Procedure Call (RPC) and REST are both ways to design APIs. APIs are essential in modern web design and other distributed systems. They allow two separate, distributed applications or services to communicate without knowing the internals of how the other one works. These two applications or services may have little to do with one another except for a small data exchange. 

APIs are also a common mechanism for the backend of a program (the logic component) to communicate with the frontend of a program (the display component). When you design web pages and web applications with APIs instead of tightly coupled integration, you ensure they can scale and change with less code rewriting.

Next, we discuss other similarities between RPC and REST APIs.

### **Abstraction**

While network communications are the main aim of APIs, the lower-level communications themselves are abstracted away from API developers. This allows developers to focus on function rather than technical implementation.

### **Communication**

Both REST and RPC use HTTP as the underlying protocol. The most popular message formats in RPC and REST are JSON and XML. JSON is favored due to its readability and flexibility.

### **Cross-language compatibility**

Developers can implement a RESTful or RPC API in any language they choose. So long as the network communication element of the API conforms with the RESTful or RPC interface standard, you can write the rest of the code in any programming language.

## Architecture principles: RPC vs. REST

In Remote Procedure Call (RPC), the client makes a remote function (also known as method or procedure) call on a server. Typically, one or more data values are passed to the server during the call.

In contrast, the REST client requests the server to perform an action on a specific server resource. Actions are limited to create, read, update, and delete (CRUD) only and are conveyed as HTTP verbs or HTTP methods.

RPC focuses on functions or actions, while REST focuses on resources or objects.

### **RPC principles**

Next, we discuss some principles that RPC systems typically follow. However, these principles are not standardized like REST.

#### ****_Remote invocation_****

An RPC call is made by a client to a function on the remote server as if it were called locally to the client.

#### ****_Passing parameters_****

The client typically sends parameters to a server function, much the same as a local function.

#### ****_Stubs_****

Function stubs exist on both the client and the server. On the client side, it makes the function call. On the server, it invokes the actual function.

### **REST principles**

REST principles are standardized. A REST API must follow these principles to be classified as RESTful.

#### ****_Client-server_****

The client-server architecture of REST decouples clients and servers. It treats them each as independent systems.

#### ****_Stateless_****

The server keeps no record of the state of the client between client requests.

#### ****_Cacheable_**** 

The client or intermediary systems may cache server responses based on whether a client specifies that the response may be cached.

#### ****_Layered system_****

Intermediaries can exist between the client and the server. Both client and server have no knowledge of them and operate as if they were directly connected.

#### ****_Uniform interface_****

The client and server communicate via a standardized set of instructions and messaging formats with the REST API. Resources are identified by their URL, and this URL is known as a REST API endpoint.

## How they work: RPC vs. REST

In Remote Procedure Call (RPC), the client uses HTTP _POST_ to call a specific function by name. Client-side developers must know the function name and parameters in advance for RPC to work.

In REST, clients and servers use HTTP verbs like _GET_, _POST_, _PATCH_, _PUT_, _DELETE_, and _OPTIONS_ to perform options. Developers only need to know the server resource URLs and don't have to be concerned with individual function names.

The following table shows the type of code the client uses to perform similar actions in RPC and REST.

|   |   |   |   |
|---|---|---|---|
|**Action**|**RPC**|**REST**|**Comment**|
|Adding a new product to a product list|POST /addProduct HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"name": "T-Shirt", "price": "22.00", "category": "Clothes"}|POST /products HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"name": "T-Shirt", "price": "22.00", "category": "Clothes"}|RPC uses _POST_ on function, and REST uses _POST_ on URL.|
|Retrieving a product’s details|POST /getProduct HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"productID": "123”}|GET /products/123 HTTP/1.1<br><br>HOST: api.example.com|RPC uses _POST_ on function and passes parameter as JSON object. REST uses _GET_ on URL and passes parameter in URL.|
|Updating a product’s price|POST /updateProductPrice HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"productId": "123", "newPrice": "20.00"}|PUT /products/123 HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"price": "20.00"}|RPC uses _POST_ on function and passes parameter as JSON object. REST uses _PUT_ on URL and passes parameter in URL and as JSON object.|
|Deleting a product|POST /deleteProduct HTTP/1.1<br><br>HOST: api.example.com<br><br>Content-Type: application/json<br><br>{"productId": "123""}|DELETE /products/123 HTTP/1.1<br><br>HOST: api.example.com|RPC uses _POST_ on function and passes parameter as JSON object. REST uses _DELETE_ on URL and passes parameter in URL.|

## Key differences: vs. REST

Remote Procedure Call (RPC) and REST are both ways to design corresponding client and server system interfaces for communication over the internet. However, the structure, implementation, and underlying principles differ. Systems designed with REST are known as RESTful APIs, whereas systems designed with RPC are simply RPC APIs.

Next, we give some more differences.

### **Time of development**

RPC was developed in the late 1970s and early 1980s, while REST was a term first coined by computer scientist Roy Fielding in 2000.

### **Operational format**

A REST API has a standardized set of server operations because of HTTP methods, but RPC APIs don’t. Some RPC implementations provide a framework for standardized operations.

### **Data passing format**

REST can pass any data format and multiple formats, like JSON and XML, within the same API.

However, with RPC APIs, the data format is selected by the server and fixed during implementation. You can have specific JSON RPC or XML RPC implementations, and the client has no flexibility.

### **State**

In the context of APIs, _stateless_ refers to a design principle where the server does not store any information about the client's previous interactions. Each API request is treated independently, and the server does not rely on any stored client state to process the request.

REST systems must always be stateless, but RPC systems can be stateful or stateless, depending on design.

## When to use: RPC vs. REST

Remote Procedure Call (RPC) is typically used to call remote functions on a server that require an action result. You can use it when you require complex calculations or want to trigger a remote procedure on the server, with the process hidden from the client.

Here are actions where RPC is a good option:

- Take a picture with a remote device’s camera
- Use a machine learning algorithm on the server to identify fraud
- Transfer money from one account to another on a remote banking system
- Restart a server remotely

A REST API is typically used to perform create, read, update, and delete (CRUD) operations on a data object on a server. This makes REST APIs a good fit for cases when server data and data structures need to be exposed uniformly.

Here are actions where a REST API is a good option:

- Add a product to a database
- Retrieve the contents of a music playlist
- Update a person’s address
- Delete a blog post

## Why did REST replace RPC?

While REST web APIs are the norm today, Remote Procedure Call (RPC) hasn’t disappeared. A REST API is typically used in applications as it is easier for developers to understand and implement. However, RPC still exists and is used when it suits the use case better.

Modern implementations of RPC, such as gRPC, are now more popular. For some use cases, gRPC performs better than RPC and REST. It allows streaming client-server communications rather than the request-and-respond data exchange pattern.

## Summary of differences: RPC vs. REST

|   |   |   |
|---|---|---|
||**RPC**|**REST**|
|What is it?|A system allows a remote client to call a procedure on a server as if it were local.|A set of rules that defines structured data exchange between a client and a server.|
|Used for|Performing actions on a remote server.|Create, read, update, and delete (CRUD) operations on remote objects.|
|Best fit|When requiring complex calculations or triggering a remote process on the server.|When server data and data structures need to be exposed uniformly.|
|Statefulness|Stateless or stateful.|Stateless.|
|Data passing format|In a consistent structure defined by the server and enforced on the client.|In a structure determined independently by the server. Multiple different formats can be passed within the same API.|