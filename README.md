# Description

In August 2000, version 1.0 of SQLite was released, with storage based on gdbm (GNU Database Manager). In September 2001, SQLite 2.0 replaced gdbm with a custom B-tree implementation, adding transaction capability. In June 2004, SQLite 3.0 added internationalization, manifest typing, and other major improvements, partially funded by America Online. In 2011, Hipp announced his plans to add a NoSQL interface to SQLite, as well as announcing UnQL, a functional superset of SQL designed for document-oriented databases. In 2018, SQLite adopted a Code of Conduct based on the Rule of Saint Benedict which caused some controversy and was later renamed as a Code of Ethics.

# Task

Constructor It will be prototyped:
def initialize

From Implement a from method which must be present on each request. From will take a parameter and it will be the name of the table. (technically a table_name is also a filename (.csv))
It will be prototyped:

def from(table_name)

Select Implement a where method which will take one argument a string OR an array of string. It will continue to build the request. During the run() you will collect on the result only the columns sent as parameters to select :-).
It will be prototyped:

def select(column_name) OR def select([column_name_a, column_name_b])

Where Implement a where method which will take 2 arguments: column_name and value. It will continue to build the request. During the run() you will filter the result which match the value.
It will be prototyped:

def where(column_name, criteria)

Join Implement a join method which will load another filename_db and will join both database on a on column.
It will be prototyped:

def join(column_on_db_a, filename_db_b, column_on_db_b)

Order Implement an order method which will received two parameters, order (:asc or :description) and column_name. It will sort depending on the order base on the column_name.
It will be prototyped:

def order(order, column_name)

Insert Implement a method to insert which will receive a table name (filename). It will continue to build the request.
def insert(table_name)

Values Implement a method to values which will receive data. (a hash of data on format (key => value)). It will continue to build the request. During the run() you do the insert.
def values(data)

Update Implement a method to update which will receive a table name (filename). It will continue to build the request. An update request might be associated with a where request.
def update(table_name)

Set Implement a method to update which will receive data (a hash of data on format (key => value)). It will perform the update of attributes on all matching row. An update request might be associated with a where request.
def set(data)

Delete Implement a delete method. It set the request to delete on all matching row. It will continue to build the request. An delete request might be associated with a where request.
def delete

Run Implement a run method and it will execute the request.
Part 01 Create a program which will be a Command Line Interface (CLI) to your MySqlite class. It will use readline and we will run it with ruby my_sqlite_cli.rb.

It will accept request with:

SELECT|INSERT|UPDATE|DELETE
FROM
WHERE (max 1 condition)
JOIN ON (max 1 condition) Note, you can have multiple WHERE. Yes, you should save and load the database from a file. :-)

# Install & Usage

$>ruby my_sqlite_cli.rb class.db
MySQLite version 0.1 20XX-XX-XX
my_sqlite_cli> SELECT * FROM students;
Jane|me@janedoe.com|A|http://blog.janedoe.com
my_sqlite_cli>INSERT INTO students VALUES (John, john@johndoe.com, A, https://blog.johndoe.com);
my_sqlite_cli>UPDATE students SET email = 'jane@janedoe.com', blog = 'https://blog.janedoe.com' WHERE name = 'Jane';
my_sqlite_cli>DELETE FROM students WHERE name = 'John';
my_sqlite_cli>quit