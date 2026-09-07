What I learnt In My SQL Journey -: 

* DAY 1 :-

Data :
Any sort of information that is stored is called as data.
                                     OR 
Data is the collection of raw facts,figures,calculations,observations or symbols that can be proceed to generate a meaningful information.

Database :
The organised collection of data is called as database.The main purpose of database is to operate a large amount of information by storing , retriving and managing a data.

Database Management system(DBMS):
A software that is used to easily store and access data from database in secure way is called as database management system.DBMS is a software that manages,store and retrive data efficiently in a structured format.

Types of Database :
1. Relational Database - The data stored and organise in a specific format i.e in realational format (Rows & Columns) is called 'Relational Database'.
2. Non-Relational Database - The data is stored and organise in non-specific format i.e it does not follow a specific format is called as Non-Relational Database.


* DAY 2 :-

What is SQL ? 
1.SQL stands for structured Query Language
2.SQL is used to perform operations on a relational DBMS i.e; RDBMS
3.SQL is declarative , hence easy to learn 
4.Declarative means , user specifies what should be done rather than how should it be done 

SQL is not a database.It is a language used to interact with relational database.It allow a user to store, retrive, update and manage data efficiently through simple commands

SQL Clauses :

        Operations                        SQL Clauses
         1.Create                            INSERT
         2.Read                              SELECT
         3.Update                            UPDATE
         4.Delete                            DELETE

CRUD Operation:

        1.Create (C) - To create database , tables and to insert record
        2.Read (R) - To read the data present in database
        3.Update (U) - To modify already inserted data 
        4.DELETE (D) - To delete database , tables , rows & columns 

Rules for Writing SQL Queries -
        1.End an sql statements with semi-colon 
        2.Case insensitive
        3.Space & new line are allow for better readability
        4.Don't use sql keyword or name 
        5.Use data constraints to ensure data accuracy 
        6.String values must be enrolls is single/double quotes
                        

commonly used datatypes in SQL :
        1.CHAR
        2.VARCHAR
        3.INT
        4.FLOAT
        5.BIGINT
        6.DOUBLE
        7.BOOLEAN
        8.DATE
        9.TIME
        10.YEAR

Keys & constraints used in SQL :
        1.NOT NULL - Ensure that no records can have null values 
        2.PRIMARY KEY - A primary key is a key that uniquely identified every record in each row.Each table can have only one primary key
        3.FOREIGN KEY - Foreign key is a key that refers to the primary key of another table.It is used for creating relationship between two tables.

Other Keys - Candidate key , Super key , Alternate Key


* DAY 3 :- 
                        ---- WRITING SQL QUERIES ---- 

- creating a new table 

        CREATE TABLE table_name (
                column_name_1           data_type,
                Column_name_2           data_type,
                column_name_3           data_type,
                .                     .
                .                     .
                column_name_n           data_type
        );

        Ex; suppose we want to create a table 'Student' with attributes (student_name,student_id,department,city)

        CREATE TABLE Student (
                student_name            VARCHAR(50),
                student_id              INT PRIMARY KEY,
                department              VARCHAR(30),
                city                    VARCHAR(30)
        );

- Inserting new data

        INSERT INTO table_name VALUES 
        (Value11,value12,.....),
        (value21,value22,.....),
        (value31,value32,.....),
                .
                .
        (value_n1,value_n2,...);

        Ex; suppose we want to insert values in the Student table  (student_name,student_id,department,city)

        INSERT INTO Student VALUES
        ('Morgan',01,'AI/ML','Canada'),
        ('Henry',02,'MBA','London'),
        ('Mathew',03,'IT','Canada'),
        ('Robert',04,'CSE','Europe');

- Retriving the data 

        SELECT * FROM table_name;

        Ex; suppose we want to retrive data from Student table 
        SELECT * FROM Student;

        retriving specific columns in a table 

        SELECT (C1,C2,C3...,Cn)
        FROM table_name;

        Ex; suppose we want to retrive the department and student id in Student table
        SELECT (department,student_id)
        FROM Student;

* DAY 4 :-

WHERE clause : WHERE clause specifies a condition that has to be satisfied for retriving data 

- Retriving data from selected row 

        SELECT * 
        FROM table_name 
        WHERE condition;

        Ex;suppose we want to retrive the data of Henry from Student table

        SELECT *
        FROM Student 
        WHERE student_name = "Henry";


- Updating data for all rows 

        UPDATE table_name 
        SET column_name=value;

        Ex;Suppose we want to update the department of all students to IT

        UPDATE Student
        SET department="IT";


- Updating data for specific row

        UPDATE table_name
        SET column_name=value
        WHERE condition;

        Ex;Suppose we want to update the department of student whose name is Henry to IT

        UPDATE Student
        SET department="IT"
        WHERE student_name="Henry";


- Deleting specific data from table 

        DELETE FROM table_name
        WHERE condition;

        Ex;suppose we want to delete the data of student whose name is Henry

        DELETE FROM Student
        WHERE student_name="Henry";


- Deleting all data from existing table 

        DELETE FROM table_name;

        Ex;Suppose we want to delete all data from Student table
        DELETE FROM Student;


- Deleting the table 

        DELETE TABLE table_name;

        Ex;Suppose we want to delete the table Student
        DELETE TABLE Student;


* DAY 5 :-

- Adding column to a existing table 

        ALTER TABLE table_name
        ADD column_name data_type;

        Ex;Suppose we want to to add column 'E-mail' to Student table 

        ALTER TABLE Student
        ADD COLUMN E_mail VARCHAR(50);


- Renaming column in a existing table 

        ALTER TABLE table_name 
        RENAME COLUMN column_name_1 TO column_name_2;

        Ex;Suppose we want to rename the column name 'E_mail' to 'Mail_id'

        ALTER TABLE table_name 
        RENAME COLUMN E_mail TO Mail_id;


- Deleting column in a existing table 

        ALTER TABLE table_name 
        DROP COLUMN column_name;

        Ex;Suppose we want to delete the column Mail_id from student table 

        ALTER TABLE Student
        DROP COLUMN Mail_id;


- SQL Operators

        SQL provides various operators to perform wide range of queries on Database
        1.Comparision Operators
        2.String Operators
        3.Logical Operators
        4.Special Operators

1.Comparision operators :

                Operator                        description
                   =                            Equal To
                   !=                           Not Equal To
                   >                            Greater Than
                   <                            Less Than
                   >=                           Greater Than Equal To
                   <=                           Less Than Equal To


* DAY 6 :-


2.String Operators :

        syntax: SELECCT
                FROM table_name 
                WHERE column_1 LIKE pattern;

Rules:

.To write pattern use wild card character(%,-)
. % represents zero character
. - represents only one direction 


        Ex;Suppose we want to reterive the info of all students whose name starts with 'M' 

        SELECT
        FROM Student
        WHERE 
        student_name 'M%';


3.Logical Operators :

        *AND Operator - Retrive all rows which satisfy both condition 1 and condition 2

                SELECT * FROM table_name 
                WHERE c1 AND c2;

                Ex;Suppose we want to retrive the students whose dept id IT and city is canada

                SELECT FROM Student
                WHERE dept='IT' AND city='canada';

        *OR Operator - Retrive all the rows which satisfy atleast one of the given condition 

                SELECT FROM table_name 
                WHERE c1 OR c2;

                Ex;Suppose we want to retrive the students whose dept id IT or city is canada

                SELECT FROM Student
                WHERE dept='IT' OR city='canada';

        *NOT Operator - It is used to negate a condition in where clause 

                SELECT FROM tbale_name 
                WHERE NOT c1;

                Ex;Suppose we want to retrive all students where dept is not IT 

                SELECT FROM Student 
                WHERE NOT dept LIKE 'IT';


* DAY 7 :-

- IN & BETWEEN Operator :

        1.IN Operator :
        Retrives rows where values of column_1 is in the given values 

                Syntax:
                SELECT * 
                FROM table_name 
                WHERE c1 IN (v1,v2,....,n)

                Ex;Suppose we want to get students from IT and AIML branch 

                SELECT *
                FROM Student 
                WHERE dept IN ('IT','AIML')


        2.BETWEEN Operator :
        Retrive all the rows where value of c1 lies between v1 and v2 

                Syntax:
                SELECT * 
                FROM table_name 
                WHERE c1 BETWEEN v1 AND v2;

                Ex;suppose we want to retrive the students whose age is between 20 & 25 

                SELECT * 
                FROM Student 
                WHERE age BETWEEN 20 AND 25;



- ORDER BY : ORDER BY sorts row based on values of column c1.

  Ascending order --- ASC
  Descending order --- DESC

Syntax :
        
        SELECT *
        FROM table_name 
        ORDER BY c1 ASC;

Ex;Suppose we want to sort the students based on their age ; Highest to lowest

        SELECT *
        FROM Student 
        ORDER BY age DESC;


* DAY 8 :-

- LIMIT  & OFFSET clause 

1.LIMIT : It is used to specify number of rows
2.OFFSET : It is used to specify position from where the rows are to be selected 

        Ex; LIMIT:4
        OFFSET:2
        It means ,Leave the first two rows and select 4 rows after that 

        LIMIT:3
        OFFSET:0
        It means ,Without  leaving any row select first three rows 

- If OFFSET is not defined is taken as 0 as default value 

        syntax:
          SELECT * 
          FROM table_name 
          LIMIT L
          OFFSET 0;

        Ex;Suppose we want to retrive information of top 5 students who score good 
          SELECT *
          FROM Student 
          ORDER BY marks DESC
          LIMIT 5
          OFFSET 0;

- Distinct results (No duplication)

        Syntax:
          SELECT DISTINCT c1
          FROM tbale_name ;

        Ex;Retriving unique names of students 
          SELECT DISTINCT student_nanme 
          FROM Student ;

- Aggregations : Aggregations means combining multiple values into a single values 

        Aggregation Functions:
        1.SUM
        2.MIN
        3.MAX
        4.COUNT
        5.AVG 

        Syntax:
          SELECT 
          agg_fun (c1)
          FROM table_name ;

* DAY 9 :-

- Alias (AS) : You can provide an alternate temporary name to the given columns 

 Syntax :
    SELECT c1 AS a1 
    FROM table_name ;

- Group By : The group by clause in sql is used to group rows that have same values in one or more columns . It is commonly used with an aggregate functions .

 Syntax :
    SELECT column_name, AGGREGATE_FUNCTION(column_name)
    FROM table_name
    GROUP BY column_name;
    


