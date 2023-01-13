# HopTwit

We will use ReactNative to create the application. This will allow us to launch on ios and Android to maximize the amount of users that can access the app.

## Architecture Diagram

## UML Diagram
<img width="683" alt="image" src="https://user-images.githubusercontent.com/59515786/212210016-24df1da4-edb9-4432-a624-f4362427eadc.png">

Our application will have 3 main classes:
1. Passenger
2. Driver
3. Route

Route will use the Google Directions API to create the most efficient route that the car can take between the requested locations. This will be stored as a list of hash maps which will store the stops that the driver will take as well as the order of the stops. 

Route will also use the Google Distance Matrix API to find the best driver for the route. The Google Distance Matrix API is used to find the closest driver to the start location of the route. Using the list of close drivers, we will then offer the route to the driver with enough car seats. In cases where multiple drivers have enough seats, the route will be first offered to the driver with the highest rating.

