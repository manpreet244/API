# Application Programming Interfaces
 An Application Programming Interface (API) is a contract that allows code to talk to other code. APIs are the building blocks of modern software because they allow for sharing of resources and services across applications, organizations, and devices   
 Have you ever made a payment on a website? Checked the weather on a mobile app? Listened to Spotify on both your desktop and your phone? Used Google Maps inside another app? Whether you know it or not, you are using APIs every day. 
 ## Why are APIs important?
APIs help developers integrate exciting features and build automation without reinventing the wheel
ex: using a Weather API instead of launching your weather balloons

APIs allow enterprises to open up their product for faster innovation
ex: apps that interact with Twitter or Meta APIs by posting on your behalf or reading tweets

APIs can be products themselves
ex: Software as a Service (SaaS) products like Stripe's payment APIs or Twilio's text messaging and email APIs
### API use is not limited to the tech and IT industries. Survey responses in the same report show that while tech, business, IT, and banking sectors represent the bulk of API use, any industry can benefit from the convenience provided by APIs. 

## APIs - A Digital Restaurant
You can think of APIs as being like a waiter at a restaurant, serving as a go-between for the customer and the kitchen.    
A customer who wants soup doesn't go into the kitchen to cook. They don't even have to know how to make soup! They only have to know how to ask the waiter for soup, expecting the waiter to bring back soup.
![image](https://github.com/user-attachments/assets/6368e318-761e-4b6b-92d1-708feed73c9c)

APIs work the same way, but there are different names for the players involved. Instead of soup, the requester might ask for data or execution of a service.    
![image](https://github.com/user-attachments/assets/998f7c9b-c9de-48ea-8371-54eb45f0b973)
### Types of APIs
### Hardware APIs
Interface for software to talk to hardware.
Example: How your phone's camera talks to the operating system. 

### Software Library APIs
Interface for directly consuming code from another code base.
Example: Using methods from a library you import into your application.

### Web APIs
Interface for communicating across code bases over a network.
Example: Fetching current stock prices from a finance API over the internet.
## Multiple API types may be used to achieve a task. For example, uploading a photo to Instagram makes use of various APIs:

-> Hardware API for the app to talk to your camera

-> Software library API for the image to be processed with filters

-> Web API for sending your image to Instagram's servers so your friends can like it!

## There is more than one way to build and consume APIs. Some architecture types you may come across are:

REST (Representational State Transfer)
GraphQL
WebSockets
webhooks
SOAP (Simple Object Access Protocol)
gRPC (Google Remote Procedure Call)
MQTT (MQ Telemetry Transport)
## REST APIs
Some traits of REST APIs include not storing session state between requests, the ability to cache, and the ability to send and receive various data types. Still confused?  

Don't worry; we will learn hands-on very soon in this course!

Access
APIs also vary in the scope of who can access them.

Public APIs (aka Open APIs)
Consumed by anyone who discovers the API

Private APIs
Consumed only within an organization and not made public

Partner APIs
Consumed between one or more organizations that have an established relationship
The API we will use in this course will be a Public, REST, Web API 👀.   

## Postman : An API platform
Postman is an API platform for building and using APIs. Postman simplifies each step of the API lifecycle and streamlines collaboration so you can create better APIs faster and consume them with ease.    
### Task: Create a collection
Collections are places to organize your API requests in Postman. They serve as executable documentation of API endpoints. 

Let's create a new Collection in our workspace to keep our requests to the Postman Library API v2. 
1. From the left pane, either click the plus ("+") icon or Create a collection.
2.  Select Blank collection
3. Name your new Collection “Postman Library API v2”
 #### Now we are ready to make a API request
 ##### Task: Get books from the Library API
   First things first: a librarian must know how to view all the books in the library catalog.

According to the API documentation, you can get all the books in the library by making a request to GET https://library-api.postmanlabs.com/books. Here, GET is the request method, and the request URL indicates where the request is sent. We'll cover what that means soon - but first, let's get our hands dirty with our first request!   
1.  Create a new request by either clicking Add a request inside your new Collection or hovering on your Collection, then click the three dots icon and "Add request"  
![image](https://github.com/user-attachments/assets/e41bedb1-dc37-4cd5-9743-1030f38efa3b)
2. Name your request "get books". Set the request method to GET, and the request URL to GET https://library-api.postmanlabs.com/books
3. 3. Send your request by clicking the Send button
       ![image](https://github.com/user-attachments/assets/81adbcd9-6f8a-4641-8bda-6c6820684f9f)
      
4. #### View the response
If everything goes well, you will see a response from the server in the lower half of Postman.

It should look like this: a JSON (JavaScript Object Notation) response body with an array of book objects.


### Request methods
When we make an HTTP call to a server, we specify a request method that indicates the type of operation we are about to perform. 
Some common HTTP request methods correspond to the CRUD operations mentioned earlier. You can see a list of more methods here.      
![image](https://github.com/user-attachments/assets/a2d5bc0f-523b-4393-960d-8e527cc387e7)  

-> Since we are "getting" books and not modifying any data, it makes sense that we are making a GET request. 
These are just conventions - it all depends on how the API is coded. To know which method to use, always read the documentation for the API you're working with!    

### Request URL
In addition to a request method, a request must include a request URL that indicates where to make the API call. A request URL has three parts: a protocol (such as http:// or https://), host (location of the server), and path (route on the server). In REST APIs, the path often points to a reference entity, like "books".   
![image](https://github.com/user-attachments/assets/bf9729a4-30b1-4d9e-ae7d-c10bd55b4bb6)    
### Response status codes
The Postman Library API v2 has returned a response status code of "200 OK". Status codes are indicators of whether a request failed or succeeded.

Status codes have conventions. For example, any status code starting with a "2xx" (a "200-level response") represents a successful call. Get familiar with other status code categories:
![image](https://github.com/user-attachments/assets/9054497e-7ee9-402c-ada1-2a63ac59780e)   
### Request-Response pattern
Now you can understand the request response pattern, which represents how computers communicate over a network. An API is the interface that lets us know what kind of response to expect when we make certain calls to a server. 
You made an HTTP GET request to https://library-api.postmanlabs.com/books and received a response from the server.
The client is the agent making a request. A client could be a browser or an application you have coded, for example. In our case Postman is the client because that's how we sent the request. 
The request is sent over a network to some server. In our case, we made a request over the public internet to a server located at the address https://library-api.postmanlabs.com. 
The server interpreted the request (GET /books) and sent the appropriate response over the network back to the Postman client: a list of books.
That's it!









