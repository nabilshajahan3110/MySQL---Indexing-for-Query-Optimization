# MySQL---Indexing-for-Query-Optimization

# DAY 21 - Challenge 21

# INDEXING FOR QUERY OPTIMIZATION

As part of a 75-day data analysis challenge, this work on MySQL covers indexing for query optimization

USE Challenge;

# (1) List the distinct country names from the Persons table.

SELECT DISTINCT(Country_Name) FROM Persons;

# (2)Select first names and last names from the Persons table with aliases.

SELECT Fname AS First_Name, Lname AS Last_Name FROM Persons;

# (3)Find all persons with a rating greater than 4.0.

SELECT ID, CONCAT(Fname,' ',Lname) AS Full_Name, 
Rating FROM Persons 
WHERE Rating > 4.0;
 
# (4)Find countries with a population greater than 225M.

SELECT Country_Name, Population FROM Country 
WHERE Population > 225000000;

CREATE INDEX idx_population ON Country(Population);

# (5)Find persons who are from 'USA' or have a rating greater than 4.0.

SELECT CONCAT(Fname,' ',Lname) AS Full_Name, 
Country_Name, Rating FROM Persons 
WHERE Country_Name = 'USA' OR Rating > 4.0;

# (6)Find all persons where the country name is NULL.

SELECT CONCAT(Fname,' ',Lname) AS Full_Name, 
Country_Name FROM Persons 
WHERE Country_Name IS NULL;

# (7)Find all persons from the countries 'USA', 'Canada', and 'UK'.

SELECT CONCAT(Fname,' ',Lname) AS Full_Name, 
CountryID, Country_Name FROM Persons 
WHERE Country_Name IN ('USA' , 'Canada' , 'UK');



![Day 21 I](https://github.com/user-attachments/assets/e9b133de-ecba-457a-84d3-04f0669f60e3)



# (8)Find all persons not from the countries 'India' and 'USA'.

SELECT CONCAT(Fname,' ',Lname) AS Full_Name, 
CountryID, Country_Name FROM Persons 
WHERE Country_Name NOT IN ('India' , 'USA');

# (9)Find all countries with a population between 200M and 400M.

SELECT Country_Name, Population FROM Country 
WHERE Population BETWEEN 200000000 AND 400000000;


![Day 21](https://github.com/user-attachments/assets/b8604199-1283-470d-b950-a396e0719b03)



# (10)Find all countries whose names do not start with 'C'.

SELECT Country_ID, Country_Name FROM Country
WHERE Country_Name NOT LIKE 'C%';



https://github.com/user-attachments/assets/7f61d242-b9cf-49dc-bbe8-f9661f64dd38

