## 1- ACCOUNTS-SERVICE and WEB-SERVICE running
### Account Microservice
![Account Microservice running and registered](https://raw.github.com/ismaro3/Laboratory-6-microservices/master/accounts-2222.png)
### WebService Microservice
![WebService Microservice running and registered](https://raw.github.com/ismaro3/Laboratory-6-microservices/master/web-3333.png)

##2.- The service registration service has the two microservices registered
![Dashboard showing registered services](https://raw.github.com/ismaro3/Laboratory-6-microservices/master/dashboard.png)

##3.- A second account microservice is running on port 4444 and is registered
![Account Microservice running on port 4444](https://raw.github.com/ismaro3/Laboratory-6-microservices/master/accounts-4444.png)

##4.- A brief report describing what happens when you kill the microservice on 2222
When you kill the microservice with port 2222, the Web service Microservice, when you try to do an operation, first shows "Refused connection" errores. A few seconds after this, it shows "No instances available for ACCOUNTS-SERVICE". Finally, twenty or thirty seconds after this, it starts working again.

What actually happens is that, when the Account Microservice in port 2222 is shutted down, the WebService Microservice tries to communicate with it and fails. The Webservice Microservice got the Account Microservice address and port from the Service Registration, but now it is down. It takes the WebService Microservice a little time to realize that it is actually down, and then it asks the Service Registration for another Microservice that provides the ACCOUNTS-SERVICE service. The Service Registration asks it with the port of the another Microservice (4444), and then it starts working again.
