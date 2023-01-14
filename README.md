# HopTwit

## Solution Details
	Our solution is a flexible, low-cost, and on-demand transit system that is aimed at creating public transit where it was once thought to be infeasible - rural communities and suburbs. Our solution is called HopTwit and is composed of two tiers:
	
### The Tadpole Network	
	This tier is meant to be a starting point for municipalities new to public transit, or used in conjunction to existing transit systems with gaps in service/demand. Rural governments are hesitant to establish rigid bus routes as ridership is unpredictable. As well, because of the large amount of land they would have to cover to service residents, it would be extremely costly. The only upfront cost would be 1-2 wheel-chair accessible vans (which can be covered by the Rural Transit Solutions Fund) to service trips that require them. Recurring costs would be paying the driver’s an hourly wage, as well as a service fee for the use of HopTwit (which can be offset with federal grants and/or a small, flat-rate fare) and includes the use of the technology, as well as the recruiting our team does, and digital/mail marketing campaigns.
	Users book their ride by 9 PM the night before their trip. This can be done with either the mobile app, through a website, or over the phone (although users may request to be added to trips after it is set if it does not alter the trip more than 10 minutes). Immediately after, an ideal driver is selected from the pool of registered drivers who have made themselves available during this time based on ratings from past trips, reliability (no missed trips), vehicle efficiency, seats available, and proximity to an accessible van pick-up point if required. They have 30 minutes to confirm the ride, or else it is offered to the next ideal driver. Once a driver is confirmed, the passengers are given their pick up time via the method they used to confirm. 	The Tadpole tier functions similarly to a ride-share app and carpooling service. Gig work is rare in rural/suburban towns, and earning additional spontaneous income is bound to be attractive.	
	Eventually, if/when municipality grows and becomes more dense and there is regular ridership, they establish a Frogger Network.

### The Frogger Network		
This solution is meant for municipalities that have used the Tadpole Network and are ready to expand, or for larger municipalities experiencing under-utilized bus lines.
	The Frogger Network works similarly to the tadpole network from the user end, but offers a smaller booking window, reliability, and the opportunity for a fully-electric fleet. Larger vans/buses (all-electric when possible) are purchased and pay-rolled employees are established. The Frogger Network is both significantly cheaper to run and more convenient for commuters than an under-utilized bus line that runs once to twice an hour on a rigid route with low ridership. 	
	Regular drivers are selected based on their record of driving in the Tadpole Network, as well as their proximity to popular routes and destinations identified from trip data if the Tadpole Network was previously used. Transit vehicles are placed in parking spots central to drivers and popular routes. 	When a ride request is sent, instead the pick-up window will be 30-60 minutes based on the user’s proximity to the nearest van cache. Drivers are on-call during operating hours; the one that is closest to the route required is selected and if a request is sent they commute to the nearby van pick-up point, use that vehicle, and pick up all users on a convenient route.	
	Having the two-tiers that build on each-other is a core part of our model. While other on-demand transit services exist, each one fills a different niche from another and is working towards a fully-connected Canada. We know that a rigid transit system is financially impossible for small municipalities. The Tadpole Network is so that communities can gauge and build interest in transit, and support those who critical need mobility. Many rural residents have no idea that there’s a way to get around besides a personal vehicle or think the idea of ride-sharing to be uncomfortable. The hope with the Tadpole Network is that as residents see their gas-bills and mileage plummet, grow up on commuting, establish the habit of not driving everywhere, and those who cannot drive experience the freedom of mobility, that a culture of commuting emerges. Once this is happens, the Frogger Network is added. The Tadpole can function in conjunction with the Frogger Network as well - when there are gaps in staffing needs, low-interest areas, providing late-night or 24/7 service, or in the case of large events or high demand.

## Accessibility
Our system provides both digital experience and a more traditional calling system. The digital experience is described below. In terms of the calling system, users can call our automated line which will then book the ride using the same server as described below. The passenger will then pay the driver with cash, and the fare will be deducted from the driver's payroll. 

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

