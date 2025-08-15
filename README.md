# PL-SQL-Project
PL/SQL Project based on a library's database management system.

This project implements a **Library Management System** in Oracle PL/SQL.  
It handles book & video rentals, customer & employee management, fines, and branch operations using a normalized relational database schema.

<img src="https://i.imgur.com/c0NVbry.png">

<h3>Normalization</h3>
<ul>
	<li><b>CARD</b> (<i>Number</i>, Fines, Status)</li>
	<li><b>CUSTOMER</b> (<i>ID</i>, Name, Address, Phone_number, Card_number [References CARD(Number)], Password, User_name, Date_sign_up)</li>
	<li><b>EMPLOYEE</b> (<i>ID</i>, Name, Address, Phone_number, Card_number [References CARD(Number)], Password, User_name, Paycheck, Branch_name [References BRANCH(Name)])</li>
	<li><b>BRANCH</b> (<i>Name</i>, Address [References LOCATION(Address)], Phone_number)</li>
	<li><b>LOCATION</b> (Address)</li>
	<li><b>RENT</b> (<i>Card_ID [References CARD(Number)], Item_ID [References BOOK or VIDEO(ID)]</i>, Date, Return_date)</li>
	<li><b>BOOK</b> (<i>ISBN, ID</i>, State, Availability, Deby_cost, Lost_cost, Address [References LOCATION(Address)])</li>
	<li><b>VIDEO</b> (<i>Title, Year, ID</i>, State, Availability, Deby_cost, Lost_cost, Address [References LOCATION(Address)])</li>
</ul>

<h3>Features</h3>
<ul>
	<li>Login system for customers and employees</li>
	<li>Rent and return books/videos with due date tracking</li>
	<li>Automatic fine calculation and card blocking</li>
	<li>Triggers to auto-create cards and update fines</li>
	<li>View all available books or videos</li>
	<li>CRUD operations for customers, books, and videos</li>
</ul>

<h3>Tech Stack</h3>
<ul>
	<li>Oracle Database</li>
	<li>PL/SQL (Procedures, Functions, Triggers)</li>
	<li>Draw.io (ER Diagram)</li>
</ul>

<h3>How to Run</h3>
<ol>
	<li>Open <code>Library.sql</code> in Oracle SQL Developer</li>
	<li>Execute all table creation and insertion statements</li>
	<li>Run provided PL/SQL procedures and triggers for various operations</li>
	<li>Use sample data to test the system</li>
</ol>

<h3>Future Improvements</h3>
<ul>
	<li>Add a web or desktop UI to interact with the database</li>
	<li>Include advanced search and filter options</li>
	<li>Generate PDF/Excel reports for rentals and fines</li>
</ul>
