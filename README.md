<h1>SQL Queries for Digital Forensics</h1>

In this project, I will show you how to use filters in SQL queries to find the data you need. SQL databases contain massive amounts of data which would make it very inefficient to search through manually. Fortunately we can use filters to automate the process. 

<h2>Unusual activity after-hours</h2>

![1](https://github.com/nicknava1/SQL/blob/main/1.png)

The team detected unusual login activity after normal business hours. There should be no attempts being made after 6:00PM, so I selected all data FROM log_in_attempts WHERE login_time > ‘18:00’ and success = FALSE.

This query displayed login attempts after hours that were unsuccessful. These events can now be further investigated.


<h2>Obtain activity on specific dates</h2>

![2](https://github.com/nicknava1/SQL/blob/main/2.png)

In this exercise, I needed to find all login attempts made on certain days. Once again I decided to SELECT all data FROM log_in_attempts. This time, however, I used WHERE login_date = ‘2022-05-09’ OR  log_in_date = ‘2022-05-08’.

This query displayed only login attempts made on 5/8/22 or 5/9/22.

<h2>Obtain attempts outside of Mexico</h2>

![3](https://github.com/nicknava1/SQL/blob/main/3.png)

In this scenario, I was tasked with finding all attempts that were made outside of Mexico. To do this I needed to use the NOT operator. Once again I decided to SELECT all data FROM log_in_attempts. Then, I specified WHERE NOT country LIKE = ‘MEX%’

The % wildcard was necessary because the database was not properly normalized. It contained both MEX and MEXICO within the country table. This properly filtered out all instances of Mexico from the results.
Updating marketing devices

<h2>Performing an Asset Inventory for Vulnerability Management</h2>

![4](https://github.com/nicknava1/SQL/blob/main/4.png)

In this scenario, the organization wanted to update specific company devices. I was asked to obtain the device information of all employees that are in the marketing department and located in the East office building. This time I selected FROM employees. Then I filtered WHERE department = ‘Marketing’ and office LIKE ‘East%’. 
 
Since the office column also contained office numbers, I needed to include the % wildcard in my query. With this query, I obtained the requested information.
