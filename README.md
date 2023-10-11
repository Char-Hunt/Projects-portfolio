## Project Portfolio - Auditing security incidents using SQL
## Project description

In this project, the goal is to obtain specific information about employees, their machines, and the departments they belong to from the database. As a security analyst, you’ll likely need to analyze data. Finding the specific data you’ll need often depends on more several factors. We will use SQL to retrieve specific pieces of information from the database and filter for multiple conditions. In addition, we will use the AND, OR and NOT operators to create more filters for SQL queries.

The security team needs data to audit potential security incidents and also update computers. As an analyst, we are responsible for filtering the following required information from the database:

1. Retrieve failed login attempts taking place oustide business hours. 
2. Obtain login attempts on specific dates.
3. Determine login attempts occuring outide of Mexico.
4. Collect information about some employees in the Marketing department.
5. Gather information about specific employees in the Finance or Sales departments. 
6. Identify information about non-Information Technology department employees,

  >_Note: This project works with an organization database and the tables it contained in the MariaDB shell._

## Task 1. Retrieve after hours failed login attempts

Your team's on a mission to uncover those failed login attempts that decided to act up after business hours. To get the scoop, you're going to dive into the login activity data, specifically targeting unsuccessful attempts after the clock strikes 6:00 PM.

The login_time column in the log_in_attempts table contains information revealing when these login attempts took place. Just remember, '18:00' marks the end of regular office hours. So, your SQL query would look something like this:

   >_NOTE: The success column in the log_in_attempts table contains values of TRUE or FALSE to indicate whether the login was successful. MySQL stores Boolean values as 1 for TRUE, and 0 for FALSE. This means that TRUE is represented as 1, and FALSE represented as 0 in the success column._

![7184y9843yt084htp21_1](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/7db91d7c-eb05-4b45-8b82-025fbabaceb5)

This query tells the database, "Show me all those login attempts that dared to misbehave after 6:00 PM." It's a savvy way to pinpoint those after-hours culprits in the login activity data. If you need to dig even deeper or get more specific, we can user SQL to dig deeper! We've already established that normal operating hours were before that time. Gathering the evidence helps an analyst put the pieces together when assessing an incident. For instance, we now have a list of IP addresses, countries, and usernames that were used in these attempts. The goal is to discern whether these attempts were legitmate or not.

## How many failed login attempts occurred after 18:00?

  -  20
  -  44
  - [x] 19
  -  39

## Task 2. Retrieve login attempts on specific dates

So, we've got this mysterious event on May 9, 2022, and we're all set to get to the bottom of it. To do that, you want to pull up all the login attempts from not just that day but also the one before it. The secret sauce here is a nice SQL query with the right filters.

Here's what that SQL query looks like, as you've noted in your screenshot (The date of the login attempt is found in the login_date column):

As noted below, we used the OR operator to retrieve the failed login attempts on the specified days. Our query identified multiple attempts on both days, successful and unsuccessful. We can still dig a bit deeper, if necessary, and filter from more parameters.

![7184f8rihpih3rgr4484_2](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/e81d84ca-23e7-40cd-9bc5-4b01d5668ff9)

How many login attempts were made on these two days?

  - 44
  - [x] 75
  - 89
  - 67

## Task 3. Retrieve login attempts outside of Mexico

So, now we've got some suspicious login activity on our hands, but you've ruled out Mexico as the source. Now, the mission is to dig into login attempts that took place outside of the Mexican borders, we need to use SQL filters and tools for the task.

Here's the SQL query that'll help you spot these elusive login attempts. But before we dive into it, remember that the 'country' column contains both 'MEX' and 'MEXICO' to represent Mexico. In this instance, we can use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico specifically.

Additionally, we must make sure that the query makes an accommodation for the country column. (When referring to Mexico, the country column contains values of both MEX and MEXICO).

>_NOTE: The following SQL query retrieves login attempts by using the NOT and LIKE keywords. Also, the matching pattern -- MEX% -- includes the wildcard % to represent a string of any length. This wildcard may be placed both before and after the targeted substring._

![7184ryg778h780-4848_3](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/58cd7695-7b2c-4b6e-80f0-24a890567544)

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
![7184547657952932569_4](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/a0388c20-3565-4a94-bfc4-287a89296f5a)

What is the username of the first employee in the Marketing department in the East building?

  - [x] elarson
  - alevitsk
  - jclark
  - fbautist

## Task 5. Retrieve employees in Finance or Sales

Now, our team needs to perform a different update to the computers of all employees in the Finance or the Sales department. Similarly, we'll locate and filter information on these employees as the previous result.

The WHERE and OR keywords are implemented within this query below:

   >_Note: Even though both conditions are based on the same column, you need to write out both full conditions. This means that you must specify department as the column in both conditions._
![7174b456fy4175894d0_5](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/d7dc4b5c-b994-4617-a36d-ec9ffe0b3d45)

What is the username of the first employee in the Sales department returned by the query?

  - bisles
  - [x] lrodriqu
  - sgilmore
  - tbarnes

## Task 6. Retrieve all employees not in IT

Our team needs to make one more update. This update was already made to employee computers in the Information Technology department. The team needs information about employees who are not in that department. We'll use the NOT operator to identify these employees as shown below.
![71844d4y798ugef037_6](https://github.com/Char-Hunt/Projects-portfolio/assets/138831832/9f2aeaf5-323d-4273-bed5-fdc0baa67b60)

How many employees are not in the Information Technology department?

  - 188
  - [x] 161
  - 122
  - 170

## Summary

When assessing a security event, it is extremely important to determine whether an incident is a serious event that requires action, or a false positive. Gathering the necessary evidence is critical and understanding how to retrieve data efficiently will determine how an analyst will move forward with the incident.

In this project, we essentially used SQL as a tool for data gathering and to suit our specific needs. Our goal was to obtain specific information about employees, their machines, and the departments they belong to from the database. We used SQL to do the following:

  - Run queries to retrieve information from a database and
  - Apply <code>AND</code>, <code>OR</code>, and <code>NOT</code> operators to filter SQL queries.
