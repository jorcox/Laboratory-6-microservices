## 1- ACCOUNTS-SERVICE and WEB-SERVICE running
### Account Microservice
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot%20_port_2222.png)
### WebService Microservice
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot%20_port_3333.png)

## 2- The dasboard with the both microservices registered
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot%20_dashboard.png)

## 3- The second ACCOUNTS-SERVICErunning on port 4444
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot%20_port_4444.png

##4.- A brief report describing what happens when you kill the microservice on 2222
When you kill the microservice with port 2222, the Web service Microservice, when you try to do an operation, first shows "Refused connection" errores. A few seconds after this, it shows "No instances available for ACCOUNTS-SERVICE". Finally, twenty or thirty seconds after this, it starts working again.

What actually happens is that, when the Account Microservice in port 2222 is shutted down, the WebService Microservice tries to communicate with it and fails. The Webservice Microservice got the Account Microservice address and port from the Service Registration, but now it is down. It takes the WebService Microservice a little time to realize that it is actually down, and then it asks the Service Registration for another Microservice that provides the ACCOUNTS-SERVICE service. The Service Registration asks it with the port of the another Microservice (4444), and then it starts working again.
