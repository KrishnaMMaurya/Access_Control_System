# Access_Control_System
An access control system is a security system designed to control and restrict access to physical or logical resources such as buildings, rooms, computer networks,
or data. It typically uses authentication and authorization mechanisms to verify the identity of users and grant or deny them access based on their level of
authorization. Access control systems can help organizations maintain security, protect their assets, and ensure compliance with regulations by managing and tracking
access to sensitive areas or information.


The part of the access control system that I implemented in my project is USER MANAGEMENT. To manage access, we would typically need to have a database of user accounts that includes information such as their name, job title or role, contact information, and access level or permissions.

FLOW OF PROJECT:
STEP-1
The "check_and_create_database.ipynb" file contains a function called "CreateDatabase". This function is designed to check whether a database already exists and, if it does not, to create a new database.

To run this function, you would need to open the "check_and_create_database.ipynb" file and execute the "CreateDatabase" function. The function will then perform the necessary checks and, if a database does not exist, it will create a new database.

By running this function, you can ensure that the necessary database is available for your project to function correctly. This is important because without a database, your project may not be able to store and retrieve data, which could result in errors or unexpected behavior.

Overall, the "CreateDatabase" function provides a convenient and automated way to check for and create a database, helping to ensure the smooth operation of your project.


STEP-2
The "CreateTable" function is a Python script that is designed to create two tables in a database, "emp_details" and "card_details".

The function first connects to the database using the "connect" function from the "mysql.connector" library, which requires the host name, user name, password, and database name as parameters. It then creates a cursor object, which allows it to execute SQL queries on the database.

The function then attempts to create the "emp_details" table by executing a "create table" SQL query. This table contains several columns, including "BADGE_NUMBER", "FIRST_NAME", "LAST_NAME", "EMPLOYEE_ID", "GLOBAL_ID", "LOCATION", "OPERATORS_COMMENTS", and "CARD_NUMBER". The "CARD_NUMBER" column is designated as the primary key for this table, which ensures that each row in the table has a unique identifier. If the table already exists, the function will catch the ProgrammingError exception and print a message indicating that the table already exists.

The function then attempts to create the "card_details" table by executing another "create table" SQL query. This table contains several columns, including "CARD_NUMBER", "date_of_issue", "End_date", "Last_change", "project_clearance", and "card_status". The "CARD_NUMBER" column is designated as a foreign key that references the "CARD_NUMBER" column in the "emp_details" table. This creates a relationship between the two tables, allowing data to be retrieved from both tables using SQL joins. If the table already exists, the function will catch the ProgrammingError exception and print a message indicating that the table already exists.

Once the tables have been created or their existence has been verified, the function closes the cursor object.

Overall, this script is useful for creating the necessary tables in a MySQL database for an access control system, which is an important component of managing user access and security.

At the end of this file I am calling both functions - CreateDatabase() and CreateTables() 


STEP-3
These are two functions used to insert data into the tables "emp_details" and "card_details" respectively. The "emp_details" function takes input from the user and inserts it into the database table. The "card_details" function also takes input from the user and inserts it into the "card_details" table along with default values for the date fields. Both functions use SQL queries to insert the data and commit the changes to the database. They also print out a success message once the data is inserted.


STEP_4
The Edit() function updates the value of a specified field for a given card number in both the emp_details and card_details tables of a MySQL database. It takes three arguments: card_number (int), field_name (str), and new_value (str), representing the card number to be edited, the name of the field to be edited, and the new value to be assigned to that field, respectively. The function connects to the database, constructs SQL statements to update the tables, executes those statements, and then closes the database connection. If there is an error, the function rolls back the changes and prints an error message. The function returns nothing.

STEP-5
The delete function takes a card_number parameter and deletes all corresponding details from the card_details and emp_details tables in the MySQL database. It first establishes a connection to the database, executes the delete queries, and commits the changes. Any errors that occur during the process are handled and the database connection is closed. The function outputs a message indicating the success or failure of the delete operation.

STEP-6
This is a main function that provides a menu of options for the user to select from. The user can choose to add new data, search for data, edit existing data, or delete data. Depending on the user's choice, the corresponding function will be called with the necessary parameters. If the user enters an incorrect choice, a message will be displayed indicating the incorrect input.
