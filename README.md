## Project Portfolio - Auditing security incidents using SQL
## Project description

In this project, the goal is to obtain specific information about employees, their machines, and the departments they belong to from the database. As a security analyst, you’ll likely need to analyze data. Finding the specific data you’ll need often depends on more than one factor. We will use SQL to retrieve specific pieces of information from the database and filter for multiple conditions. In addition, we will use the AND, OR and NOT operators to create more filters for SQL queries.

The security team needs data to audit potential security incidents and to update computers. As an analyst, we are responsible for filtering the following required information from the database:

1. Retrieve failed login attempts taking place oustide business hours. 
2. Obtain login attempts on specific dates.
3. Determine login attempts occuring outide of Mexico.
4. Collect information about some employees in the Marketing department.
5. Gather information about specific employees in the Finance or Sales departments. 
6. Identify information about non-Information Technology department employees,

  >_Note: This project works with the organization database and the tables it contains in the MariaDB shell._

## Task 1. Retrieve after hours failed login attempts

Your team is investigating failed login attempts that were made after business hours. You want to retrieve this information from the login activity. You’ll identify all unsuccessful attempts after 18:00.

The login_time column in the log_in_attempts table contains information on when login attempts were made. Office hours end at '18:00'.

   >_NOTE: The success column in the log_in_attempts table contains values of TRUE or FALSE to indicate whether the login was successful. MySQL stores Boolean values as 1 for TRUE, and 0 for FALSE. This means that TRUE is represented as 1, and FALSE represented as 0 in the success column._

![7184547657952932569](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/dd0b1aeb-4c17-4909-bf9c-d020bc4c0a66)


This query is essentially selecting all columns from the log_in_attempts table where the login_time is greater than 18:00 and was unsuccessful. We've already established that normal operating hours were before that time. Gathering the evidence helps an analyst put the pieces together when assessing an incident. For instance, we now have a list of IP addresses, countries, and usernames that were used in these attempts. The goal is to discern whether these attempts were legit or not.

## How many failed login attempts occurred after 18:00?

  -  20
  -  44
  - [x] 19
  -  39

## Task 2. Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. To investigate this event, we want to review all login attempts which occurred on this day and the day before. This query must use the appropriate filters in SQL that will identify all login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of the login attempt is found in the login_date column.)

As noted in the screenshot below, we used the OR operator to retrieve the failed login attempts on the specified days. Our query identified multiple attempts on both days, successful and unsuccessful. We can dig a bit deeper if necessary and filter from more parameters.

xxx

How many login attempts were made on these two days?

  - 44
  - [x] 75
  - 89
  - 67

## Task 3. Retrieve login attempts outside of Mexico

There’s been suspicious activity with login attempts, but our team has determined that this activity didn't originate in Mexico. We need to investigate login attempts that occurred outside of Mexico. In this instance, we can use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico specifically.

Additionally, we must make sure that the query makes an accommodation for the country column. (When referring to Mexico, the country column contains values of both MEX and MEXICO).

The following SQL query retrieves login attempts by using the NOT and LIKE keywords. Also, the matching pattern -- MEX% -- includes the wildcard % to represent a string of any length. This wildcard may be placed both before and after the targeted substring.

xxx

Task 3. How many login attempts were made outside of Mexico?

  - 194
  - [x] 144
  - 73
  - 122

## Task 4. Retrieve employees in Marketing

As a security analyst, we are often employed to conduct security updates on endpoints and devices . In this case, the security team must identify specific employee machines in the Marketing department. Our queries in this scenario requires that we identify all employees of the Marketing department for all offices in the East building.

  The department of the employee is found in the department column, which contains values that include Marketing. The office is found in the office column. Some examples of values in this column are East-170, East-320, and North-434. We essentially need to use the LIKE keyword with % to filter for the East building.

Our goal is to update specific employee machines. We'll need to obtain the information about employees in the 'Marketing' department who are located in all offices in the East building (such as 'East-170' or 'East-320'). Keywords WHERE and the modifier LIKE will enable our query to filter out the results properly.

Please see the following results below from the SQL query to view the filtered columns and values in the employees table:

xxx

What is the username of the first employee in the Marketing department in the East building?

  - [x] elarson
  - alevitsk
  - jclark
  - fbautist

## Task 5. Retrieve employees in Finance or Sales

Now, our team needs to perform a different update to the computers of all employees in the Finance or the Sales department. Similarly, we'll locate and filter information on these employees as the previous result.

The WHERE and OR keywords are implemented within this query below:

   >_Note: Even though both conditions are based on the same column, you need to write out both full conditions. This means that you must specify department as the column in both conditions._

xxx

What is the username of the first employee in the Sales department returned by the query?

  - bisles
  - [x] lrodriqu
  - sgilmore
  - tbarnes

## Task 6. Retrieve all employees not in IT

Our team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. We'll use the NOT operator to identify these employees as shown below.

xxx

How many employees are not in the Information Technology department?

  - 188
  - [x] 161
  - 122
  - 170

## Summary

When assessing a security event, it is extremely important to determine whether an incident is serious or a false positive. Gathering the necessary evidence is critical and understanding how to retrieve data efficiently will determine how an analyst will move forward with the incident.

In this project, we essentially used SQL as a tool for data gathering our specific needs. Our goal was to obtain specific information about employees, their machines, and the departments they belong to from the database. We used SQL to do the following to:

  - Run queries to retrieve information from a database and
  - Apply <code>AND</code>, <code>OR</code>, and <code>NOT</code> operators to filter SQL queries.
