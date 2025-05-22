### Procedure

Consider a use case of the car rental application as follows:

-   **Use Case Name:** Release a Vehicle (to a customer)

-   **Description:** A customer arrives to acquire the vehicle and depart for desired destination. The vehicle reservation contract is signed and the vehicle is released to the customer.

-   **Actors:** Front-Desk Office Executive, Customer

    Basic Flow ("Sunny Day Scenario"):

    1. A customer comes to the office to acquire a vehicle.

    2. The Office Executive locates the vehicle reservation contract by means of the reservation number and/or customer name. [Exception: Required vehicle type is not available due to late arrivals.]

    3. The customer signs the contract and the Office Executive gives the keys to the vehicle.

    4. The Office Executive then marks the contract active by entering the vehicle release date (today's date) onto the vehicle reservation contract. The use case terminates at this point.

-   **Exceptions ("Rainy Day Scenario"):**

    1. Required vehicle type is not available due to late arrivals:

    2. Raised when the reserved vehicle is not available due to late returns. The customer is informed of the situation and told about the other vehicle types that are available. The customer is offered an incentive to accept another vehicle type. If the customer is not satisfied, the reservation is cancelled without penalty charges. The customer either accepts another vehicle type or cancels the reservation.

-   **Postconditions:** The customer departs with the vehicle and the reservation contract is marked active, or the reservation is cancelled.

-   **Stakeholder:** Reservation department

Experiment 1 recap: Use case was completed. Noun phrases and conceptual classes were identified, and the domain object model was constructed.

Experiment 2 recap: The verb phrases were identified and the method invocation between the objects were ordered to construct the time sequence model.

Experiment 3 recap: The datatype of attributes and the signature of the methods were identified for every class. The relationship between classes was defined to construct the class diagram.

Experiment 4 recap: The class Customer was implemented in Java following the constraints given on the attributes and its accessor and mutator functions.

---

## Implementation Steps (as per simulation code)

### Step 1: Implement the Vehicle Class

-   The Vehicle class has a mandatory registration number set at creation and a key status field initialized to "available".
-   It includes a constructor to set the registration number and methods to update the key status to "not available" and retrieve the registration number.

### Step 2: Implement the Customer Class

-   The Customer class includes fields for customer ID (auto-incremented), email, name, phone, and city.
-   It provides constructors to create customers with email, phone, or both, along with methods to access and modify these fields.

### Step 3: Implement the Reservation Class

-   The Reservation class manages a reservation ID (auto-incremented), customer and vehicle objects, contract status, booking date, and release date.
-   It offers constructors to create reservations using customer details and vehicle objects, along with methods to manage contract status, booking dates, and release dates.

### Step 4: Aggregation Relationship Demo

-   Write a demo class to create a customer array with 3 objects.
-   Customer objects are created with the availability of only email, then only phone and last customer with both email and phone number.
-   Assign the city of the first two customers as Coimbatore and that of the remaining customers as Chennai.
-   Create a Vehicle object with a registration number.
-   A customer in Coimbatore does a reservation of the vehicle for current date. Also release the vehicle.

### Step 5: Composition Relationship Demo

-   Create a Vehicle object with a registration number (e.g., 5678)
-   Create a Reservation object that:
    1. Creates a Customer object with email/phone
    2. Takes ownership of the Vehicle object
    3. Sets the customer's city (e.g., "Coimbatore")
    4. Sets the booking date to current date
    5. Updates the vehicle's key status

The composition relationship is enforced by:

-   The Reservation class creating and managing its Customer object
-   The Reservation class taking ownership of the Vehicle object
-   The lifecycle of Customer and Vehicle objects being tied to the Reservation object

### Output

Execution of the TestDriver code is shown as a stack-heap view for both aggregation and composition code, matching the simulation output.

> **Note:** Work on the experiments sequentially.
