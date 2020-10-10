# Week 1 - Hands on Lab 

To write and execute the following SQL statements in this lab, I will need to launch the SQL editor (Run SQL) in your Db2 database instance on IBM Cloud that I created.

**NOTE: Some users have reported issues performing this lab using Microsoft Edge. It is recommended using Google Chrome or Mozilla Firefox as your web browser to complete these labs.**

First you will launch the SQL editor in the Db2 console using the following steps:

- [x] Go to your IBM Cloud dashboard (you may need to log into IBM Cloud in the process):

https://cloud.ibm.com/resources

- [x] Expand the Services and locate and click on your instance of Db2 you provisioned in the previous lab (the name typically starts with Db2-xx for example Db2-fk, Db2-50, etc.)

## Tasks list 
- Drop table INSTRUCTOR in case it already exists
  ```
  drop table INSTRUCTOR ; 
  ```
1. Create table INSTRUCTOR
     ```
    CREATE TABLE INSTRUCTOR
    (ins_id INTEGER PRIMARY KEY NOT NULL, 
   lastname VARCHAR(15) NOT NULL, 
   firstname VARCHAR(15) NOT NULL, 
   city VARCHAR(15), 
   country CHAR(2)
    )
    ```
2.  - Insert single row for Rav Ahuja
    ```
    INSERT INTO INSTRUCTOR
    (ins_id, lastname, firstname, city, country)
    VALUES 
    (1, 'Ahuja', 'Rav', 'Toronto', 'CA');
    ```
    - Insert the two rows for Raul and Hima
    ```
    INSERT INTO INSTRUCTOR
        VALUES
        (2, 'Chong', 'Raul', 'Toronto', 'CA'),
        (3, 'Vasudevan', 'Hima', 'Chicago', 'US');

    ```
3.  Select all rows in the table
    ```
    SELECT * from INSTRUCTOR;

    ```
    - Select firstname, lastname and country where city is Toronto
    ```
    SELECT firstname, lastname, country from INSTRUCTOR where city='Toronto';

    ```
4.  Change the city for Rav to Markham
    ```
    UPDATE INSTRUCTOR SET city='Markham' where ins_id=1
    ```
5.  - Delete the row for Raul Chong
    ```
    DELETE FROM INSTRUCTOR where ins_id=2;
    ```
    -  Retrieve all rows from the table
    ```
    SELECT * FROM INSTRUCTOR;
    ```
