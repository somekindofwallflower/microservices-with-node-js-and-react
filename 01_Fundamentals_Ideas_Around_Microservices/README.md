
# Fundamental ideas around Microservices.

## What is a Microservice?
> A microservice contains all the code required to make one feature work correctly.

**Monolithic Server**

![Application](/img/pic_01_04.png?raw=true)

**Monolithic Structure**

![Application](/img/pic_01_05.png?raw=true)

**Single Microservice**

![Application](/img/pic_01_06.png?raw=true)

**Microservices**

![Application](/img/pic_01_07.png?raw=true)


## What is the big challenge with microservices?

> Data management between services. 

**Data management has to do with:**

1) How data is stored inside a service - Each service gets its own database (if it needs one)
2) How data is being communicated between services.


## Why Database-Per-Service?

1) Every service runs independently of another service.
   
   ![Application](/img/pic_01_08.png?raw=true)
 
   ![Application](/img/pic_01_09.png?raw=true)
   
2) Database schema/structure might change unexpectedly.
  
   ![Application](/img/pic_01_10.png?raw=true)
 
   ![Application](/img/pic_01_11.png?raw=true)
   
3) Some services might function more efficiently with different types of DB's (sql vs nosql)


## Basic E-commerce Application

The app has three simple functions:
1) Sign up
2) List products
3) Buy products

   
![Application](/img/pic_01_13.png?raw=true)

**Monolithic overview**

![Application](/img/pic_01_14.png?raw=true)

**Adding new feature**

![Application](/img/pic_01_15.png?raw=true)

**Microservices overview**

![Application](/img/pic_01_16.png?raw=true)

**Adding new microservice**

![Application](/img/pic_01_17.png?raw=true)

### Communication Strategies Between Services
1) Sync
2) Async

***Attention: These words don't mean what they mean in JavaScript world!!!!***

![Application](/img/pic_01_18.png?raw=true)

### Applying sync communication strategy when adding Service D

![Application](/img/pic_01_19.png?raw=true)


**Pro and Cons of Sync Communication Strategy**

![Application](/img/pic_01_20.png?raw=true)


### Applying async communication strategy when adding Service D

***First form of async communication***

![Application](/img/pic_01_21.png?raw=true)


**Pro and Cons of Async Communication Strategy Method 1**

![Application](/img/pic_01_22.png?raw=true)


***Second form of async communication***

![Application](/img/pic_01_23.png?raw=true)

**Event Accours - product is created - event flows into the Event bus**

![Application](/img/pic_01_24.png?raw=true)

**Event bus takes the event and send it to any interested services**

![Application](/img/pic_01_25.png?raw=true)

**Service D takes the information and record that event by storing the product inside products table**

![Application](/img/pic_01_26.png?raw=true)

**User requests to sign up**

![Application](/img/pic_01_27.png?raw=true)

**Event bus takes the event and send to service D and service D takes the event and store user information in users table**

![Application](/img/pic_01_28.png?raw=true)

**Create order event**

![Application](/img/pic_01_29.png?raw=true)

**Event bus takes the event and send to service D and service D takes the event and store order information in users table**

![Application](/img/pic_01_30.png?raw=true)

**Pro and Cons of Async Communication Strategy Method 2**

![Application](/img/pic_01_31.png?raw=true)
