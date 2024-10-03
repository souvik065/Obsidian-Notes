
- It uses a multi tier model

## Multi-Tiered Application
- Functionality of Application is separated into isolated functional areas 
	- Client Tier
	- Middle Tier
	- Data Tier (Enterprise Information System Tier)

- Client Makes requests to the middle tier
- Middle tier has the business functions, handles the client requests and processes it.
- Store the application data in permanent data storage in the data tier
- Mainly concentrate on middle tier to make enterprise application easier, robust and secure. 


## Client Tier 
- Acts as front end for an application
- Acts a user interface for applications
- Get the input from user and them convert into requests that are forwarded to middle tier (Server).
- Get the input from user and then convert into requests that are forwarded to middle tier (server).
- It translates the server's response into text and presented to the user.
- A web browser, a stand-alone application, or other servers.


## Middle Tier 

- Consists of one or more sub-tiers
- It process the request, generates the response and gives it to the client tier.
- Application Server or Web Server
- Various containers for processing the request
	- Web Container (Web tier)
	- EJB container (EJB tier)

## Web Container 
- Used for deploying web applications
- Provides internet functionality for J2EE application
- Components -- Servlet, JSP, HTML or XML

## EJB Container 
- Used to deploy business applications
- Contains the collection of Enterprise Java Beans (EJB)
- Enterprise Java Beans Contains business logic of applications.
- Responsible for low-level system services required to implement business logic of an Enterprise Java Beans.
- System services
	- resource pooling
	- Distributed Object Protocols



Resource :-
[Java Beans -CoderX Ankit](https://www.youtube.com/watch?v=4SBsP42j6Xw)