# HopTwit

## Built With
- React Native
- Express.js
- PostgreSQL
- Firebase
- Google Maps API

We chose React Native as it allows for the development of cross-platform mobile apps. This means that the same codebase can be used to build apps for both iOS and Android, which will save us time and effort. Express.js is a popular and powerful framework. It makes it easy to set up a backend server and handle HTTP requests and responses. Given that it's a popular framework it will allow for our app to be easily scalable, as well as it's easy to find developers with experience in Express. PostgreSQL is also widely used and is a robust relational database management system that can handle complex data structures and relationships. This will allow for even more scalability once our app becomes more complex. 

Firebase was chosen for authentication and also for push notifications. 

Both ReactNative and Express.js are javascript frameworks. 

## Architecture Diagram
<img width="664" alt="image" src="https://user-images.githubusercontent.com/59515786/212243868-d0730db6-1362-4daa-8544-4481ddaafdf0.png">

The app has a client-server architecture, with React Native and Express.js. The server connects to a PostgreSQL database to store and retrieve data for the app.

The React Native app handles the user interface and user experience of the app, and communicates with the server through a RESTful API. The server handles the backend logic, such as handling ride requests and matching rides with drivers.

Firebase Authentication is used to handle user authentication and Firebase Cloud Messaging is used to send push notifications to users. Google Maps API and React Native Geolocation are used to handle maps and geolocation, and Stripe is used to handle payments.

## UML Diagram
<img width="692" alt="image" src="https://user-images.githubusercontent.com/59515786/212243997-b7eb5c89-73d5-47b2-85f0-4b0a68a3577c.png">

Our application will have 3 main classes:
1. Passenger
2. Driver
3. Ride

**Passenger** will store their email, password, upcoming rides, whether or not they need an accessible car, and phone number. The phone number will be used if the passenger indicates that they would like to be called when the driver confirms the pickup. **Passenger** also includes methods for logging in and out, and for updating user information.

**Ride** will use the Google Directions API to create the most efficient route that the car can take between the requested locations. This will be stored as a list of hash maps which will store the stops that the driver will take as well as the order of the stops. **Ride** will also use the Google Distance Matrix API to find the best driver for the ride. The Google Distance Matrix API is used to find the closest driver to the start location of the ride. Using the list of close drivers, we will then offer the ride to the driver with enough car seats. In cases where multiple drivers have enough seats, the ride will be first offered to the driver with the highest rating.

**Driver** will store the driver's email, password, phone number, departure location, upcoming rides, rating and number of car seats.


## Authors

- Emily Chang
- Noah Cazabon
- Amy Ling

