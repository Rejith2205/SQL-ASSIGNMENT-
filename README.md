##    QUERYING DATA

**Create a table named Country with fields: Id Country_name, Population, Area**.

l**Create another table named Persons with fields: Id Fname, Lname ,Population, Rating, Country_Id, Country_name**.

* (1) List the distinct country names from the Persons table 
* (2) Select first names and last names from the Persons table with aliases. 
*	(3)Find all persons with a rating greater than 4.0.
*	 (4)Find countries with a population greater than 10 lakhs. 
*	(5)Find persons who are from 'USA' or have a rating greater than 4.5.
*	(6)Find all persons where the country name is NULL.
*	(7)Find all persons from the countries 'USA', 'Canada', and 'UK'
*	(8)Find all persons not from the countries 'India' and 'Australia'.
*	 (9)Find all countries with a population between 5 lakhs and 20 MILLION. 
*	(10)Find all countries whose names do not start with 'C'.

### **SQL COMMANDS** 
#####  **CREATE TABLE**
Create table country(COUNTRY_NAME VARCHAR(50) ,
					POPULATION  INT,
					AREA INT);

Create table PERSONS(F_NAME VARCHAR(50),
					 L_NAME VARCHAR(50),
                    				 POPULATION INT,
              RATING INT,
                    				 COUNTRY_ID INT,                                
                   				  COUNTRY_NAME VARCHAR(50));


#####  **SPECIFY WHICH DATABASE TO BE USED FOR THE SUBSEQUENT ACTIVITY**

use entri_d41;

#####  **ADD DATA TO THE TABLE COUNTRY**
INSERT INTO COUNTRY VALUES('SINGAPORE',40000000,1000),('INDONESIA',100000000,2500);

INSERT INTO COUNTRY VALUES	('USA',6600000,4000),('ROME',200000,1000),
                        ('TANZANIA',5000000,1500),('KENYA',3000000,1000);
                        
INSERT INTO COUNTRY VALUES	('UK',6500000,2000),('CANADA',450000000,5500),
                        ('AUSTRALIA',80000000,6500),('INDIA',500000000,3000);



#####  **VIEW THE DETAILS OF THE TABLE**
SELECT * FROM COUNTRY;
;

#####  **ADD DATA TO THE TABLE PERSON**


INSERT INTO PERSONS VALUE ('TINU','TOM',40000000,5,10010,'SINGAPORE');
INSERT INTO PERSONS VALUES('KANNAN','RAVI',6600000,6,10001,'USA'),
('MANJU','NATH', 6600000,3,10001,''),
('SUKANYA','SURESH', 6500000,7,10002,'UK'),
('ANDREW','THOMPSON', 450000000,8,10003,'CANADA'),
('ANIL','CHOUDHARY', 500000000,4,10005,'INDIA'),
('SIMILY','MATHEW', 80000000,6,10004,'AUSTRALIA'),
('ABDUL','SALAM', 5000000,3,10225,'TANZANIA'),
('ROBERT','MOGAMBE', 5000000,4,10225,'TANZANIA'),
('SUKVINDER','SINGH', 6500000,6,10002,'UK');

#####  *VIEW THE DETAILS OF THE TABLE PERSON*

  SELECT * FROM PERSON;

#####  *List the distinct country names from the Persons table*

 SELECT DISTINCT COUNTRY_NAME FROM PERSONS;


#####  *Select first names and last names from the Persons table with aliases*

  SELECT F_NAME AS FIRST_NAME , L_NAME AS SECOND_NAME,CONCAT(F_NAME , L_NAME) AS FULLNAME FROM PERSONS;



#####  *Find all persons with a rating greater than 4.0*

SELECT CONCAT(F_NAME , L_NAME)
 AS FULLNAME, RATING FROM PERSONS
 WHERE RATING>4;


#####  *Find countries with a population greater than 10 lakhs*

SELECT DISTINCT COUNTRY_NAME,POPULATION
 FROM PERSONS
 WHERE POPULATION>1000000;


#####  *Find persons who are from 'USA' or have a rating greater than 4.5*

 SELECT CONCAT(F_NAME , L_NAME)
 AS FULLNAME,RATING FROM PERSONS
 WHERE RATING>4.5 
 AND COUNTRY_NAME LIKE 'USA%';

#####  *FFind all persons where the country name is NULL*

SELECT CONCAT(F_NAME , L_NAME)
  AS FULLNAME 
  FROM PERSONS
 WHERE COUNTRY_NAME ='';
 

#####  *Find all persons from the countries 'USA', 'Canada', and 'UK'**

 SELECT CONCAT(F_NAME , L_NAME)
 AS FULLNAME,COUNTRY_NAME  FROM PERSONS
 WHERE COUNTRY_NAME IN('CANADA','USA','UK');


#####  *Find all persons not from the countries 'India' and 'Australia'
 SELECT CONCAT(F_NAME , L_NAME)
 AS FULLNAME,COUNTRY_NAME  FROM PERSONS
 WHERE COUNTRY_NAME NOT IN
 ('INDIA' ,'AUSTRALIA');


#####  *Find all countries with a population between 5 lakhs and 20 MILLION*
SELECT COUNTRY_NAME,POPULATION FROM COUNTRY
  WHERE POPULATION BETWEEN 500000 AND 20000000;


#####  *Find all countries whose names do not start with 'C'*
  SELECT COUNTRY_NAME FROM
  COUNTRY WHERE COUNTRY_NAME NOT LIKE 'C%';




