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
### Variables in Postman
Postman allows you to save values as variables to reuse them and easily hide sensitive information like API Keys. 
We will use a variable to replace our base URL so that we don't have to type that repeatedly. Once a variable is defined, you can access its value using double curly brace syntax like this: {{variableName}}
STEPS----
1. Go to the "get books" request in your collection.
2. With your cursor, select the entire base URL of the API (https://library-api.postmanlabs.com). Do not include the slash / after .com.
3. Click "Set as variable" to save the base URL to a variable.
![image](https://github.com/user-attachments/assets/df14ab7e-19b0-4f4f-9a9c-d420d2f4e247)

![image](https://github.com/user-attachments/assets/4247adea-40c8-4f75-91be-6af03eaee054)

Initial Value - the value initially set when someone forks or imports your collection. Note that if you share your collection with others, they will see this value, so don't put any secrets here!

Current Value - Postman always resolves the variable to this value. This is local to your Postman account, and not public. It is good to keep secrets like API Keys ONLY in this column and not include them in the Initial Value column.

### Query parameters
Remember that the minimum ingredients you need to make a request are:

a request method (GET/POST/PUT/PATCH/DELETE, etc)
a request URL
#### Some APIs allow you to refine your request further with key-value pairs called query parameters
#### Query parameter syntax
Query parameters are added to the end of the path. They start with a question mark ?, followed by the key-value pairs in the format: <key>=<value>. For example, this request might fetch all photos that have landscape orientation:
GET https://some-api.com/photos?orientation=landscape

If there are multiple query parameters, each is separated by an ampersand &. Below two query parameters to specify the orientation and size of the photos to be returned:
GET https://some-api.com/photos?orientation=landscape&size=500x400
Search Google - with query parameters!
Try pasting this URL into your browser or as a GET request in Postman to make a Google search for "Postman". (If you use Postman, click the "Preview" tab in the response to view the rendered HTML!)

https://www.google.com/search?q=postman


## Path Variable
Another way of passing request data to an API is via path variables (a.k.a. "path parameters"). A path variable is a dynamic section of a path and is often used for IDs and entity names such as usernames. 


This request adds a search term as a query parameter q=postman ("q" refers to "query" here) to the GET /search path on Google's server.
Because this parameter is in our request, the server returns an HTML document that is a search results page with hits for "Postman". The search bar is pre-populated with our query "Postman".

Sometimes, query parameters are optional and allow you to add filters or extra data to your responses. Sometimes, they are required in order for the server to process your request. APIs are implemented differently to fulfill different needs.     

[![WATCH THIS VIDEO](https://github.com/user-attachments/assets/44f52bc8-23ff-4dff-97cb-46285665b87c)

## Request Response Pattern   
An API is the interface that lets us know what kind of response to expect when we make certain calls to a server.     
You made an HTTP GET request to https://library-api.postmanlabs.com/books and received a response from the server.   
![image](https://github.com/user-attachments/assets/0ed383fe-87c5-497d-a91e-01b687df7041)    

The client is the agent making a request. A client could be a browser or an application you have coded, for example. In our case Postman is the client because that's how we sent the request.     
The request is sent over a network to some server. In our case, we made a request over the public internet to a server located at the address https://library-api.postmanlabs.com   
The server interpreted the request (GET /books) and sent the appropriate response over the network back to the Postman client: a list of books.    
### Path Variable syntax
The path variable comes immediately after a slash in the path. For example, the GitHub API allows you to search for GitHub users by providing a username in the path in place of {username} below: 
### Path vs Query parameters


![image](https://github.com/user-attachments/assets/9a703491-7d8d-4997-ae1e-abdf04f42bd4)

### Get a book by id

[![WATCH THIS VIDEO TO know how to get books using its id using a path variable](
https://github.com/user-attachments/assets/66952c08-122c-4744-9471-506618ca66ce)

## Sending a POST Request   
Task: Add a book   
A new bestseller book arrived! As a librarian, you wish to add that book to the library.
In this lesson, we will learn how to add a book via POST request with a JSON Body to submit book data to our Postman Library API database.    
But what is the Body?    
You will need to send body data with requests whenever you need to add or update structured data. For example, if you're sending a request to add a new customer to a database, you might include the customer details in JSON data format. Typically, you will use body data with PUT, POST, and PATCH requests.     
The Body tab in Postman enables you to specify the data you need to send with a request. You can send different types of body data to suit your API.

You can use raw body data to send anything you can enter as text. Use the raw tab, and the type dropdown list to indicate the format of your data (Text, JavaScript, JSON, HTML, or XML), and Postman will enable syntax-highlighting and appending the relevant headers to your request.   

[![WATCH THIS VIDEO TO know how to make a post request or how to add a book](https://github.com/user-attachments/assets/bc463fe5-d858-4993-8561-30b5995c9715)

😱 Uh-oh!
The response from the server came back with a status 401 Unauthorized. Remember that 400-level errors are client errors, meaning we made a mistake in our request as below:
![image](https://github.com/user-attachments/assets/37438a2a-2568-4422-be57-c5bc6510982f)
 Reason for the above error it that  
Some APIs require Authorization (aka Auth) for certain endpoints in order to permit a request.
-> Authorization is the process of verifying that a user or application has the right permissions to access a particular resource or perform a specific action. It typically follows authentication, which is the process of verifying the identity of the user or application.

#### Common Authorization Methods
1) API Keys:

A simple string that is passed with the request to identify the client. API keys are often used for simple scenarios but lack fine-grained control.
Example: api_key=your_api_key
2)Bearer Tokens (OAuth 2.0):
A more secure and flexible method where an access token is obtained after authentication and included in the request headers.
Example: Authorization: Bearer your_access_token
3)Basic Auth:
Encodes the username and password in base64 and sends it in the request header.
Example: Authorization: Basic base64encodedusername:password
4)JWT (JSON Web Tokens):
Tokens that are signed and can include user information and permissions. They are included in the request header.
Example: Authorization: Bearer your_jwt_token
Let us look into this    
## Authorization
Think about why you might not want an API to have completely open endpoints that anyone can access publicly. It would allow unauthorized people to access data they shouldn't see, or allow bots to flood an API with thousands of calls per second and shut it down. 
There are multiple methods for authorizing a request. Some examples are Basic Auth (username and password), OAuth (delegated authorization), and API Keys (secret strings registered to a developer from an API portal).    
#### Getting an API Key
APIs that use API Key auth usually allow developers to sign up in a developer portal, where they will receive a random API Key that can be used to authorize their requests to the API. The API Key allows the API to track who is making calls and how often.  
The Postman Library API v2 uses very light protection and does not require you to register for an API Key. You simply have to know it:

Header name: api-key
Header value: postmanrulz
## Headers
Headers are how we can add metadata about our requests, such as authorization information or specify the data type we want to receive in a response. This is different than the actual payload data we send in the body of a request, such as our new book information.

You can think of headers like the outside of an envelope when you send a letter. The envelope has information about delivering the letter, like proof that you've paid for postage. The actual data "payload" is the letter inside the envelope.
As the documentation shows, the Postman Library API v2 requires adding this header to any requests for adding, updating and deleting books, since these operations change data in the database instead of simply reading them.
[![WATCH THIS VIDEO TO know how to add headers to a request](https://github.com/user-attachments/assets/121adc9b-4b98-4f8d-bf79-dbc340461479)

🚀 Success!
Your book was added! Now that your request is properly authorized in the header, you should get a 201 Created response with a response body that is an object representing your newly added book!
Your new book has been assigned a random, unique id, and has extra information now, such as it's checkedOut status and when it was added to the library (createdAt)

### There is an easier way by which we can add , api-key to postman by adding auth to the collection
Before we use the Postman Auth helper, let's remove the hard-coded header we just added on the "add a book" request.Hover over the api-key header in the Headers tab and click the "x" icon at the right to delete the header. Save your request.
## Add Auth to the Collection
The Postman Auth helper can help you add authorization at the request, folder or collection level. Let's add the api-key to our entire collection so that all requests will send the key. 
[![WATCH THIS VIDEO TO know how to addauthorisation](https://github.com/user-attachments/assets/6ff7e081-e8ef-4493-b98a-c895fa820b72)

## Variable scopes

You can set variables that live at various scopes. Postman will resolve to the value at the nearest and narrowest scope.
From broadest to narrowest, these scopes are global, collection, environment, data, and local.
![image](https://github.com/user-attachments/assets/5310e004-2228-4c75-b598-0db8b57f5d80)
## Setting variables programmatically
### Scripting in Postman
Postman allows you to add automation and dynamic behaviors to your collections with scripting.

Postman will automatically execute any provided scripts during two events in the request flow:

Immediately before a request is sent: pre-request script (Pre-request Script of Scripts tab).
Immediately after a response comes back: post-response script (Post-response of Scripts tab).
In this lesson, we will focus on writing scripts in the Post-response tab, which are executed when a response comes back from an API.

### The pm object
Postman has a helper object named pm that gives you access to data about your Postman environment, requests, responses, variables and testing utilities. 

For example, you can access the JSON response body from an API with: 

##### pm.response.json()

You can also programmatically get collection variables like the value of baseUrl with:

##### pm.collectionVariables.get(“baseUrl”)

In addition to getting variables, you can also set them with pm.collectionVariables.set("variableName", "variableValue") like this:

##### pm.collectionVariables.set(“myVar”, “foo”)

Get ready!

In the next task, we will use scripting and the pm object to set a new book's automatically id as a collection variable so we can use the id in other requests.

### Setting and getting collection variables
The pm object allows you to set and get collection variables.

To set a collection variable, use the .set() method with two parameters: the variable name and the variable value

pm.collectionVariables.set("variableName", value)

To get a collection variable use the .get() method and specify the name of the variable you want to retrieve:

pm.collectionVariables.get("variableName")
##### Set the new book id as a variable 
[![WATCH THIS VIDEO TO know how to set variable](https://github.com/user-attachments/assets/b63fcb3f-7a32-4b37-9280-68d0e6e0df61
)
