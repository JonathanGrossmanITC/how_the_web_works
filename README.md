# How the web works

The material in this file contains basic information and links about how the web works. 

The purpose of this lesson is to introduce to you some of the overarching concepts of web development. These overarching concepts each play an important role in influencing how to structure your applications. After this lesson, you'll have a better idea of how fullstack applications are structured and how the data flows once a user visits a webpage.

After this lesson, you will know:

- How a [**browser**](#browser) knows which files to display to the user     
- What a [**server**](#server) is and how a browser communicates with it  
- How [**databases**](#database) fit into a web application  
- What [**HTTP**](#http) is and why the web needs it  

By understanding how the web works, you can write more efficient, secure, and sophistacted web applications. Plus, the more you know about the overarching concepts, the faster you'll become at building projects, and it will become easier for you to maintain and debug your work.  

## [Browser](#browser)  

A browser is software that displays source code to users in a way that is easy for humans to view and understand. It is the frontend of web applications. Browsers read HTML, CSS, JavaScript and other files in order to know what to display to the user. Chrome, Firefox, and Safari are examples of browsers.  

Browsers have an address bar where users can input an address for the website that they want the browser to display. The address a user enters into the address bar is called a **domain name**. A [domain name](https://en.wikipedia.org/wiki/Domain_name) is a series of letters and numbers that is easy to remember, usually prefixed with `www` and suffixed with one of several options, like `.com`. For instance, the domain name for ITC's website is `www.itc.tech`.  

Each domain name has a corresponding [IP Address](https://en.wikipedia.org/wiki/IP_address). The IP address is a series of numbers and letters and is how your website is identified on the web. IP addresses can be in IPv4 or IPv6 format and are too hard for humans to remember, which is a reason why domain names serve as a proxy for the IP address in the browser's address bar. 

```
Sidenote:
IP address can be in either IPv4 or IPv6 format. 

The IPv4 address is a unique 32-bit number. It is four decimal numbers separated by dots, each ranging from 0 to 255. Here is an example: 

172.16.254.1 

The IPv6 address is a unique 128-bit number. It is more complex than IPv4. Here is an example: 

2001:0db8:85a3:0000:0000:8a2e:0370:7334
```      

It's not only domains that have IP addresses. Anything connected to the web has an IP address, including your computer. **Want to know your device's [public IP address](https://www.whatismyip.com/dns-lookup/)**? How about its **[private IP address](https://www.howtogeek.com/117371/how-to-find-your-computers-private-public-ip-addresses/)**? 

When a user enters a domain name in the browser, the browser uses the domain name to get the domain's IP address. The browser sends a request to a Domain Name System ([DNS Server](https://en.wikipedia.org/wiki/Domain_Name_System)) asking for the domain name's IP address. The DNS Server matches the domain name to its corresponding IP address and responds to the browser with the IP address.

With the domain's IP address, the browser can retrieve the website source code. Website source code is stored with a [hosting provider](https://en.wikipedia.org/wiki/Web_hosting_service). AWS and GoDaddy are examples of hosting providers. The browser sends the IP address to the hosting provider asking for the website source code files for that IP address. The hosting provider responds with the files, and the browser uses them to assemble the webpage. 

Ultimately, when a user visits the domain name, the browser uses that domain name to request your website's files from the hosting provider using the IP address. The source code, typically HTML, CSS, JavaScript and media files, instructs the browser on how to display the information     

Some browsers have developer tools. Look at the inspector in your browser to explore behind the scenes.  

## [Server](#server)   

A server is software that runs on a [machine](https://media.geeksforgeeks.org/wp-content/uploads/20200429161002/server-image-1.png) and listens for incoming requests. It is part of the backend of web applications. Instead of using browsers to read server-side code, you use HTTP to communicate with servers. For instance, you can send HTTP requests **to** servers from browsers, and you can send HTTP requests **from** servers to other servers and databases. You can write servers in many different programming languages. [Express.js](https://expressjs.com/en/starter/hello-world.html) is an example of a JavaScript-based server framework.   

Like the frontend, a server has a domain name and IP address. You can use your server's domain name in your server-side code to write routes for others to send requests to. A route is a string that extends the domain name, like in `www.api.com/get-all-users/` the domain is `www.api.com` and the route is `/get-all-users/`.

In a server, a route directs an incoming request to a specific function. Unlike a route on the frontend that tells the browser which information to display, a [server route](https://expressjs.com/en/starter/basic-routing.html) tells the server what information to process and how to do it. In other words, a server has some functionality associated with it. This difference between frontend and server-side routes is an important concept to understand.  

You can customize your routes in many ways. For instance, you can declare what type of HTTP requests the route accepts. Plus, the route's functionality can be many different things. For instance, upon receiving a request, some of the things a route function can do are send a response to the requesting party, send a request to a database, or receive incoming information, process it and return a result.  

Here is an example flow of a web application. A user clicks a button displayed by the browser. The browser [sends a request](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) to a server route asking for a user's profile information. The request triggers the server route's function. That function sends a request to a database asking for the data that the browser asked for. 

The database responds to the server route with the data. The server route receives the data from the database and sends it in a response to the browser's request. Finally, the browser [receives the response](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch#checking_that_the_fetch_was_successful) and displays it to the user.  
    
When a server communicates with a database, it is for the purpose of either creating, updating, reading, or deleting data from the database. More about databases below.   

## [Database](#database)  
    -- A database stores electronic information  
    -- Databases live on a machine  
    -- Many [types of databases](https://www.guru99.com/introduction-to-database-sql.html) exist  
    -- Databases communicate with servers  
    -- Then servers send the data to browsers or servers  
    -- A common sequence: Browser sends a request to the server, which triggers the server to request data from the database; upon receiving the data from the database, the server responds to the browser's request with the data   
    -- In the ITC Fullstack bootcamp, you work with relational databases (SQL) and NoSQL (MongoDB)  
    -- In this program, you will not work with databases directly  
 
 ## [HTTP](#http)  
   - A protocol for sending and receiving messages over the web  
   - [Request methods](https://www.w3schools.com/tags/ref_httpmethods.asp) distinguish between they type of request you are sending  
   - [Response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) help you know the status of a response  
   - [JSON](https://www.w3schools.com/whatis/whatis_json.asp) is the data format you use to send and receive data via HTTP  
   - You will work with requests, responses, and JSON in this course and the ITC Fullstack Program  
  

+++++ MORE MATERIAL +++++


Clients, servers, hosting servers, domain names, IP addresses, mobile devices -- any interaction between computers / machines. Use requests and responses to exchange data packages containing the information necessary to show a webpage on a screen (desktop, laptop, mobile, etc.). HTTP communication is one-way, request, then response. In web development, this usually means that a client sends a request to a server (or one server to another server), and then the server responds to the client (or server).  . . . As opposed to HTTP requests, other ways exist for machines to communicate with on another. For instance, web sockets and related technologies enable real-time communication where 



===



# [HTTP](#http)

Hyper-text transfer protocol (HTTP) is the language that standardizes how clients and servers communicate with one another across the web. According to HTTP, a client sends a request, which is a data packet containing a body and meta data, to a server. The server responds to the request. The response is a data packet containing a response to the request body and meta data. HTTPS is the same as HTTP except the communication between clients and servers is encrypted for security. 

Like how it's essential that a spoken language have rules for people to understand one another, having a standarized way for clients and servers to communicate is essential. A client has to know how to format a request in a way that the receiving server can interpret in order to provide a coherent response. Same goes for responses. The server has to know how to respond in a way that the client will understand. This is what HTTP and HTTPS are for.

Using HTTP and HTTPS is how a browser uses a domain name to request an IP address and an IP addresss to request a website's source code, such as HTML, CSS, and JavaScript files. Visit the domain name for a website you like. In the browser, open the inspector and visit the Network tab. In the Name column, do you see anythng? What file types do you see? In the Network tab, look at the other tabs, like Headers, Preview, and Response, for different file types. What do you see? Do any of them contain source code when viewed in the response tab?



