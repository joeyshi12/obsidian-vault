## Task 1: SQL DDL Creation

```SQL
CREATE TABLE Customer(
    customerID CHAR(11) PRIMARY KEY,
    streetAddress CHAR(20),
    email CHAR(20) UNIQUE,
    firstName CHAR(20) NOT NULL,
    lastName CHAR(20) NOT NULL
)


CREATE TABLE Reservation(
    confirmationNumber INT PRIMARY KEY,
    customerID CHAR(11) NOT NULL,
    -- customerID param in Customer not necessary since field names match
    FOREIGN KEY (customerID) REFERENCES Customer(customerID)
    ON DELETE CASCADE
)


CREATE TABLE Branch(
    branchName CHAR(20) PRIMARY KEY,
    streetAddress CHAR(20) NOT NULL,
    city CHAR(20) NOT NULL
)


CREATE TABLE VehicleType(
    typeName CHAR(20),
    rentalRate REAL SET DEFAULT 0,
    numberOfSeats INT
)


CREATE TABLE Reserves(
    branchName CHAR(20) DEFAULT "Scranton PA",
    confirmationNumber INT,
    typeName CHAR(20),
    startDate DATE NOT NULL,
    endDate DATE NOT NULL,
    PRIMARY KEY (confirmationNumber, branchName, typeName),
    FOREIGN KEY (confirmationNumber) REFERENCES
        Reservation ON DELETE CASCADE,
    FOREIGN KEY (branchName) REFERENCES
        Branch ON DELETE SET DEFAULT,
    FOREIGN KEY (typeName) REFERENCES
        VehicleType ON DELETE CASCADE
)
```


## Task 2

```SQL
-- Customer
INSERT
INTO Customer(customerID, streetAddress, email, firstName, lastName)
VALUES (101, "10 Watford St", "a@ubc.ca", "Kate", "Selvarajah")

INSERT
INTO Customer(customerID, streetAddress, firstName, lastName)
VALUES (102, "9 Jenner St", "Ming", "LEE")

-- Reserves
INSERT
INTO Reserves(branchName, confirmationNumber, typeName, startDate, endDate)
```


## Task 3

1. The customer tuple will get deleted because it can be uniquely identified from its primary key. This will cause the first row of the reservation table to be deleted which will cause the first row of the reserves table to be deleted.
2. This will throw an error because we require customer tuples to have firstName values that are not null.
3. Nothing references the reserves table, so only the first tuple in the Reserves table will be deleted
4. TODO