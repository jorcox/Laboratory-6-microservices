## 1- ACCOUNTS-SERVICE and WEB-SERVICE running
### Account Microservice
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot_port_2222.png)
### WebService Microservice
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot_port_3333.png)

## 2- The dasboard with both microservices registered
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot_dashboard.png)

## 3- The second ACCOUNTS-SERVICE running on port 4444
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/screenshot_port_4444.png)

## 4- Report describing what happens when you kill the microservice on 2222
Once the service running on port 2222 is killed, trying to do a search or an operation results on a fail.
![](https://github.com/jorcox/Laboratory-6-microservices/blob/master/error_report.png)

The WEB-SERVCICE tries to do requests to the original ACCOUNTS-SERVICE but it's down. Service Registration have to handle this situation providing the other ACCOUNTS-SERVICE to the WEB_SERVCICE.

After waiting a few seconds the WEB-SERVICE gets the new ACCOUNTS-SERVICE host and port from the Service Registration and starts working correctly ahain.

