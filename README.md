# Bank Statement Generation
NodeJs and RabbitMQ based Microservice architechture to retrieve bank account statement from a Database and send it over email in PDF format.
---
## Technical Information
- Backend Environment - Node v14 <br/>
- Framework - Express(NodeJS) <br/>
- Architecture - MicroService Based <br/>
- Tech Stack & Technologies Used <br/>
  * JavaScript(NodeJS)
  * RabbitMQ
  * Postman

### Why NodeJS over other Backend Development Technologies?
I would like to answer it in two points.
- Scalability: If the project requires high scalability, Node.js has an advantage due to its non-blocking, event-driven architecture. It's known for its ability to handle a large number of concurrent connections efficiently.

- Performance: Depending on the workload and the specific use case, one technology might have a performance advantage over the other. Node.js is often praised for its speed and efficiency, especially in I/O-bound applications.

### Why is RabbitMQ in picture rather than normal HTTP based APIs?
We can accept requests in a RESTful format instead of using a message queue like RabbitMQ. Using RESTful APIs for communication between services is a valid approach in microservices architecture. It simplifies some aspects of communication and might be more straightforward to set up, but it does introduce potential limitations, such as potential scalability issues in a high-traffic scenario.

**********
## How to access the project
1. Spin Up the RabbitMQ, use the following docker command
```shell
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.9-management
```
2. Install packages for all services one by one
```shell
cd dbService && npm install
cd emailService && npm install
cd pdfService && npm install
```
3. To run each service, execute:
```shell
npm run dev
```
--------------------
### Examples
![image](https://github.com/palnikhil/inhibit-action/assets/85008177/ac79112f-2bcf-4f48-a73e-7b5c49c3d3bd)
![image](https://github.com/palnikhil/inhibit-action/assets/85008177/7fd42c00-8d6a-42d7-ad72-54bac7e62d9d)
![image](https://github.com/palnikhil/inhibit-action/assets/85008177/7a971706-d389-40d8-ba47-51ac949f2f80)

---------------------
### Future Scope
**Adding Authorization and Authentication into the APIs** 
We can add authorization and authentication as well to secure the endpoints and requests. We can do this by generating jwt token. We can follow the following steps.<br/>
Steps: <br/>
* Authorization using Email and Password to generate AccessToken.
* We can store this AccessToken in redis
* At first, the request would go through a middleware to check the validity of accessToken, then only the other methods would work.


