# Web Architectures

_This work is based on a session moderated by Brigitte Jellinek ([@bjelline](https://twitter.com/bjelline)) and Marco Emrich ([@marcoemrich](https://twitter.com/marcoemrich)) at jscraftcamp 2019_

See [the original repository](https://github.com/jscraftcamp/jscc19-sessions/tree/master/web-architectures) for 
the results of the session.


## Definition: what is Web Architecture?

Software architecture refers to the fundamental structures of a software system
[Wikipedia](https://en.wikipedia.org/wiki/Software_architecture). Some parts
of the software system may be built with Web technologies: HTTP, HTML, CSS, JavaScript, WebAssembly.

Under the heading "Web Architecture" we want to discuss the architecture
we use for code that runs in the browser itself, and for the parts of the
system that generate the HTML, CSS, JavaScript, WebAssembly. 


## Stacks

A [Solution Stack](https://en.wikipedia.org/wiki/Solution_stack) is not
an architecture.  But historically some stacks were 

* LAMP-Stack (Linux, Apache, MySQL, PHP)
  * available since ~1995
* MEAN-Stack (Mongo, Express, Angular, Node)
  * available since ~2010

## Design Patterns

* MVC Design Pattern (Model, View, Controller)
* MVVM Design Pattern (Model, View, View-Model)
* MVP Design Pattern (Model, View, Presenter)
* CQRS Design Pattern (Command Query Responsibility Separation)
* Eventsourcing Design Pattern 

## (How) do you distribute the Software?

* (Deployment) Monolith
  * all parts concerning the web are developed in one repository and deployed as one piece of software
* SOA (Service Oriented Architecture)
  * the software system is designed to consist of several services that can be developed and deployed independently of each other
* Micro-Services (defined by deployment)
  * the software system is designed to consist of many small services that can be developed and deployed independently of each other

## Who creates the HTML? and when?

* Static Webpage 
  * the developer writes HTML, saves it to a file and deploys it to a webserver (no backend programming needed)
* JAM-Stack
  * the developer writes a program,
  * and compiles it.  the result of this step is either a static webpage or a SPA
  * in both cases it can be deployed to a simple webserver with no "backend capabilities"
* SPA (Single Page App)
  * the developer writes a "frontend" program (in JavaScript (+ optionally WebAssembly))
  * when the user requests a webpage for the first time this frontend program is loaded in the browser
  * the user can interact with the app and will see different "pages" that are created in the webserver by this program "on the fly"
* Server-Side-Includes
  * the developer writes static webpages,
  * instead of a backend language a very simle "include statement" is used
  * when the user requests a webpage it will be created on the webserver by combining 2 or 3 pages
  * (but there is no turing complete programming language involved)
* Edge-Side-Includes
  * same as server-side-includes, but it happens on a CDN, not a normal webserver
* Server-Side-Rendering
  * the developer writes a "backend" program,
  * and deploys it to a webserver.
  * when the user requests a webpage it will be created on the webserver by this program "on the fly"

## Misc Vocabulary

* PWA (Progressive Web App)
* Serverless
* Isomorphic App
* Universal

## Protocols

* (plain) HTTP - every request is initiated by the client, stateless, 
* WebRTC - Browser to Browser, Peer to Peer Audio/Video/Data Streaming
* WebSockets
* Server Push

## Where is the "one true source" of state?  How is it communicated to the parts of the system?

* ROCA (Resource Oriented Client Architecture)
* Synchronizing App (e.g. PouchDB/CouchDB)
* Live-View (Elixir/Phoenix)
