# Spring Boot "Microservice" Exercise Tracker 

## Description
This is an exercise tracker app built with a postgresql database, using java spring boot. The goal of the app is to create a simple, minimalist, tracker for logging 
user's daily workouts. A user can simply input their username, exercise, sets/reps, weights, muscle, and notes for that given day. 

## How to Run
The application is packaged as a war which has Tomcat 8 embedded. No Tomcat or JBoss installation is necessary. You can run it using java -jar.


- Clone this repository
- Make sure you are uding JDK 1.8 and Maven 3.x
- Once successfully built, you can run the service by

```
java -jar demo-0.0.1-SNAPSHOT.jar
```
Once the application runs you should see something like this
```
2021-06-24 14:15:37.202  INFO 21501 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2021-06-24 14:15:37.224  INFO 21501 --- [           main] com.amyzhao3969.demo.DemoApplication     : Started DemoApplication in 22.286 seconds (JVM running for 25.155)
```
#### Create A Exercise Log
```
Location header: http://localhost:8080/api/v1/user
Content-Type: application/json

{
"id": 2,
"userName": "alexa",
"exercise": "squat",
"sets": 2,
"weights": 50,
"workoutDate": "2021-06-20",
"muscle": "gluteus maximus, quadriceps",
"note": "first squat"
}

```

#### Retrieve Exercise Logs 
```
Location header: http://localhost:8080/api/v1/user
Response:
{
"id": 2,
"userName": "alexa",
"exercise": "squat",
"sets": 2,
"weights": 50,
"workoutDate": "2021-06-20",
"muscle": "gluteus maximus, quadriceps",
"note": "first squat"
}
```
#### Update Exercise Log
```
Location header: http://localhost:8080/api/v1/user/{userId}?exercise=pushup&sets=3
{
"exercise": "pushup",
"sets": 3
}
RESPONSE: HTTP 204 (No Content)
```
#### Delete Exercise Log
```
Location header: http://localhost:8080/api/v1/user/{userId}
RESPONSE: HTTP 204 (No Content)
```
