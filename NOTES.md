# Lecture 1 Notes


### What do java backend engineers do?
- Build java backends using java to talk to databases.
- Supplying apis for people to consume. Mostly other devs.

### What is the Three tier architecture?

The three tier architecture is way to organize work.  
Front end tier, mid tier (you), database.

### What is the CDN (content delivery network) ?
- A CDN is a group of distributed servers that delivers content based on geographic location. 
- There is an origin server that has the original content and edge servers that has a copy of the content. 

### How does a DNS request work? 
- A browser sends a request to the DNS server to resolve the domain name of the url to the corresponding IP address. DNS is an alias converting URL to an IP. 
- DNS server returns the IP address of the closest CDN edge server to user’s location.

Browser talks to the backend server and that talks to the database

Microservices

Now there is an api gateway with services underneath it.
Every service has its own database (best practice)

How does a web request work?

(content delivery network) - distributed servers that delivers content based on geographic location. Edge server has a copy of the content from the origin server. 

A browser sends a request to the DNS server to resolve the domain name of the url to the corresponding IP address. DNS is an alias converting URL to an IP. 

DNS server returns the IP address of the closest CDN edge server to user’s location.

CDN edge server checks its cache. If found, then CDN edge server returns the cached version. If not then the request is sent to the origin server. CDN edge server saves it.

CDN only contains static content - HTML page, css asserts, images, js assets, fonts. 
We need to know it because it might contain an outdated API that calls our backend. 

REST request
We are responsible for this.
-JS constructs an HTTP request object. 
-Adds endpoint API URL and HTTP method
-includes necessary parameters or data
- server gets request and returns a response - our job
- JS receives the response and processes it
- reponse manifests as a UI change


A capable backend:
Intercepts requests
Extract data from requests. 
Process the request
Pull necessary data from database
Process the data and prepare response
Return the response

Handling requests
HTTP - hypertext transfer protocol
A typical http request is a message sent bya client (like browser)to a server to request specific information

Every HTTP request (from the client) has 
-A request line (`GET /index.html HTTP/1.1`)
-Headers: meta info about the request
Ex. key: value 
-body: data to be sent with the request
- expects an HTTP response

HTTP response
-status line: First line Eg: `HTTP/1.1 200 OK`
- header: meta infromation about the response
-Body: actual data being sent
Ends when it times out

HTTP
Stateless protocol. 

Cookies - mechanism allows multiple http requests to be tied together
Server creates a cookie and sents it to the clients machine in a header called Set-Cookie
The client sends the cookie back in the cookie header in every subsequent requests
Useful with server sessions
Login flow
User enters login credentials intoa web form
Form data is submitted using HTTP POST
Sever verifies the credentials
Server generates a new session for the user
Server cresates a unique token (session ID)
Server sendsa r seponse with a set-cookie header
Browser stores the cookie on the user’s device
Browser sends the cookie back to the server in the cookie header
Server looks up session info based on session iD
Server generates a personalized response
This process is automatic

That was the cookie approach, which is automatic.
Also browser memory 
Local and session storage


Make a request and look at the network tab.

What we need 
A good programming language 
A server runtime (Tomcat, java EE, jakarta EE)
A framework to handle common concerns (Spring/SpringBoot)
A framework to interact with the database
A framework to handle security (Spring Security)
A framework to manage infrastructure (microservices) (Spring Cloud)

Source Control

Git - a version control system for tracking changes in files and coordinating work among multiple people, built for collaboration
Keeps track of different versions of your code
Collaborate with others
Revert back to previous versions if needed
Resolve conflicts when multiple peopel are working on the same codebase. 

GitHub - a web based platform that provides hosting for Git repositories

Git manages versions of your code locally or on a remote server

Github is the potential “main” remote server. Has PR, issues, wikis, project management, discussions, actions

Github workflow
PR workflow
Fork the repository, makes a copy under your name
Clone the repository locally
Create a new branch locally
Make changes
Push the changes to the repository
Create a pull request (if accepted then changes are make to the original)
review and discuss
Merge or decline
Update and delete the branch

Rebase - puts your change aside, pull the changes and puts your change back in.
