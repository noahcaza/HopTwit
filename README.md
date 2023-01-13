# HopTwit


## Architecture Diagram
<img width="654" alt="image" src="https://user-images.githubusercontent.com/59515786/212223420-7fb04e26-7899-415b-aad9-0b55b628d727.png">
We will use ReactNative to create the application. This will allow us to launch on iOS and Android to maximize the amount of users that can access the app.

The server will handle interacting with the Google APIs and also the logic revolving around assigning a driver.

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

