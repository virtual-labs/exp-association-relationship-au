### Procedure

Consider a use case of the car rental application as follows:

-  **Use Case Name:** Release a Vehicle (to a customer)

- **Description:** A customer arrives to acquire the vehicle and depart for desired destination. The vehicle reservation contract is signed and the vehicle is released to the customer.

- **Actors:** Front-Desk Office Executive, Customer

  Basic Flow ("Sunny Day Scenario"):

    1. A customer comes to the office to acquire a vehicle.

    2. The Office Executive locates the vehicle reservation contract by means of the reservation number and/or customer name. [Exception: Required vehicle type is not available due to late arrivals.]

    3. The customer signs the contract and the Office Executive gives the keys to the vehicle.

    4. The Office Executive then marks the contract active by entering the vehicle release date (today's date) onto the vehicle reservation contract. The use case terminates at this point.

-  **Exceptions ("Rainy Day Scenario"):**

    1. Required vehicle type is not available due to late arrivals:

    2. Raised when the reserved vehicle is not available due to late returns. The customer is informed of the situation and told about the other vehicle types that are available. The customer is offered an incentive to accept another vehicle type. If the customer is not satisfied, the reservation is cancelled without penalty charges. The customer either accepts another vehicle type or cancels the reservation.

- **Postconditions:** The customer departs with the vehicle and the reservation contract is marked active, or the reservation is cancelled.

-  **Stakeholder:** Reservation department

Experiment 1 recap: Use case was completed. Noun phrases and conceptual classes were identified, and the domain object model was constructed.

Experiment 2 recap: The verb phrases were identified and the method invocation between the objects were ordered to construct the time sequence model.

Experiment 3 recap: The datatype of attributes and the signature of the methods were identified for every class. The relationship between classes was defined to construct the class diagram.

Experiment 4 recap: The class Customer was implemented in Java following the constraints given on the attributes and its accessor and mutator functions.

Now, the steps to implement the aggregation and composition relationship of the class Customer and class Vehicle with class Reservation is as follows:

Step 1: Implement the class Vehicle based on the following rules.

    1.  The regNum is set with a value at the time of object creation, and it is a mandatory field.

    2.  The keystatus is set to “available” on vehicle creation.

    3.  Also complete the constructor, access and mutator methods in the class diagram.

    4.  The updateKeyStatus method always sets the keyStatus to “not available”.

Step 2: The reservationID is set by the default constructor as the reservation count and it is mandatory field. It cannot be set by the user.

    1. The current reservation mandatorily sets the customerObj with an existing customer object who books a vehicle.

    2. The current reservation mandatorily sets the vehicleObj with an existing vehicle object.

    3. The bookingDate indicates the date of booking of the vehicle by a customer otherwise it is set to null.

    4.. The releaseDate indicates the date of handing over of the vehicle to customer otherwise it is set to null.

    5. The contractStatus indicates the booking or hand over process of the reservation. Reservation incomplete makes this field null.

    6. Also complete the constructor, access and mutator methods in the class diagram.

    7. The releaseContract method checks if the bookingDate matches releaseDate and the keystatus is “available” then update keyStatus or prints an error.

Step 3: Aggregation relationship: Write a demo class to create a customer array with 3 objects. Customer objects are created with the availability of only email, then only phone and last customer with both email and phone number. Assign the city of the first two customers is Coimbatore and remaining customers is Chennai. Create a vehicle object with a registration number. A customer in Coimbatore does a reservation of the vehicle for current date. Also release the vehicle.

Step 4: Composition relationship: Implement a modified Reservation class with customer construction possible directly by it. Also Write a demo class that creates a vehicle object with a registration number. Create a reservation object that does a reservation of the vehicle for current date by providing **customerName**, **email** and/or **phone number**. Later set the city as Coimbatore. Also release the vehicle.

Output: Execution of the **TestDriver** code is shown as stack-heap view for both aggregation and composition code.

> **Note:** Work on the experiments sequentially.