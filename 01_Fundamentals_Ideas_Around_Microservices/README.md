
# [Stephen Grider] Microservices with Node JS and React

## 01. Fundamental Ideas around Microservices.
<br/>

### What is a Microservice?
A microservice contains all the code required to make one feature work correctly.

#### Monolithic Server

![Application](/img/pic_01_05.png?raw=true)

<br/>

![Application](/img/pic_01_06.png?raw=true)

#### Single Microservice

![Application](/img/pic_01_07.png?raw=true)

#### Microservices

![Application](/img/pic_01_07.png?raw=true)


### What is the big challenge with microservices?

Data management between services. 

<b>Data management has to do with:</b>

1) How data is stored inside a service -> Each service gets its own database (if it needs one)
2) How data is being communicated between services.


<b>Why Database-Per-Service?</b>

1) Every service runs independently of another service.
   </br>
   ![Application](/img/pic_01_08.png?raw=true)
   </br>
   ![Application](/img/pic_01_09.png?raw=true)
2) Database schema/structure might change unexpectedly.
   </br>
   ![Application](/img/pic_01_10.png?raw=true)
   </br>
   ![Application](/img/pic_01_11.png?raw=true)
3) Some services might function more efficiently with different types of DB's (sql vs nosql)
