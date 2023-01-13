# HopTwit

## Built With
- ReactNative
- Express.js
- PostgreSQL

We chose React Native as it allows for the development of cross-platform mobile apps. This means that the same codebase can be used to build apps for both iOS and Android, which will save us time and effort. Express.js is a popular and powerful framework. It makes it easy to set up a backend server and handle HTTP requests and responses. Given that it's a popular framework it will allow for our app to be easily scalable, as well as it's easy to find developers with experience in Express. PostgreSQL is also widely used and is a robust relational database management system that can handle complex data structures and relationships. This will allow for even more scalability once our app becomes more complex. 

Both ReactNative and Express.js are javascript frameworks. 

## Architecture Diagram
<img width="654" alt="image" src="https://user-images.githubusercontent.com/59515786/212223420-7fb04e26-7899-415b-aad9-0b55b628d727.png">

## UML Diagram
<img width="749" alt="image" src="https://user-images.githubusercontent.com/59515786/212225103-2344ccb1-fdb1-499f-9497-63d837d7ff76.png">

Our application will have 3 main classes:
1. Passenger
2. Driver
3. Route

**Route** will use the Google Directions API to create the most efficient route that the car can take between the requested locations. This will be stored as a list of hash maps which will store the stops that the driver will take as well as the order of the stops. 

**Route** will also use the Google Distance Matrix API to find the best driver for the route. The Google Distance Matrix API is used to find the closest driver to the start location of the route. Using the list of close drivers, we will then offer the route to the driver with enough car seats. In cases where multiple drivers have enough seats, the route will be first offered to the driver with the highest rating.

**Driver** will store the driver's email, password, phone number, departure location, upcoming routes, rating and number of car seats.

**Passenger** will store their email, password, upcoming routes, whether or not they need an accessible car, and phone number. The phone number will be used if the passenger indicates that they would like to be called when the driver confirms the pickup. 

To increase security, passwords will only be stored after salt and peppering. 

## Authors

- Emily Chang
- Noah Cazabon
- Amy Ling

