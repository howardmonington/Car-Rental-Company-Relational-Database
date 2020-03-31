<h1> Relational Database Development </h1>
<h2> The Scenario </h2>
The challenge was to develop a relational database using Oracle SQL Developer for a hypothetical car rental business with several addresses. The business rents multiple different types of cars, which each have their own respective rental prices. The rental pricing is also dependent upon available promotions. Additionally, the business keeps track of all of its customers and employees. It is also possible to be both an employee and a customer at the same time.
<h2> Assumptions </h2>
To better understand the constraints, I created a list of assumptions for use with table design. These assumptions were:
<ol>
  <li> A person does not have more than two ID numbers. </li>
  <li> A person can be an employee, a customer, or both.</li>
  <li> The return date is predetermined at time of rental. </li>
  <li> Store locations have at least one car.</li>
  <li> Employees are assigned to exactly one store.</li>
  <li> A car can be rented many times</li>
  <li> A rental transaction is limited to one car.  </li>
  <li> A car classification can only have one discount code at a time. </li>
</ol>
<h2> Table Creation & Logical ER Model </h2>
After diving into the details, I determined that it was necessary to create 6 tables: Car, CarClassification, Promotion, RentalTransaction, and StoreLocation. I listed the attributes that I would keep track of, and then designed a data dictionary (attached as another file in this repository). Below is an image of the logical ER Model. I was able to generate this image after fully building the database, but it made more sense to post here to illustrate how the tables would relate with each other and the cardinalities.
<img src="https://user-images.githubusercontent.com/42416078/78066138-a2da9280-7351-11ea-8bb9-d9914208673a.png" />
<h2> The Normalization Process </h2>
Normalization is a database design technique that organizes tables in a manner that reduces redundancy and removes potential anomalies. The 3 main types of anomalies are:
<ol>
  <li> Deletion Anomalies: where deleting one row inadvertently deletes something else </li>
  <li> Insert Anomalies: where a table can't add a new record until it already exists </li>
  <li> Update Anomalies: where the same data is stored multiple times, and all of them don't get updated </li>
</ol>
In order to take care of all functional dependency problems, I normalized to BCNF:
<ul>
<li> First normal form (1NF): No repeating groups </li>
<li> Second normal form (2NF): Already in 1NF and there are no partial functional dependencies </li>
<li> Third normal form (3NF): Already in 2NF and there are no transitive dependencies </li>
<li> Boyce-Codd normal form (BCNF): Already in 3NF and every determinant is a candidate key </li>
</ul>
The fully normalized relations were:
<img src="https://user-images.githubusercontent.com/42416078/78067163-7d4e8880-7353-11ea-988a-1a75d7b78310.png"/>
<h2> Building Database in Oracle SQL </h2>
Finally, it was time to build the relational database. In order to create the database, I needed to create the tables in a specific order by first adding the tables with no foreign keys, and then creating the tables with foreign keys that refer to those new tables. That way, I would avoid building a table that refers to another table that hasn't even been created yet. In effect, I was adding the tables on the "one" side of the "one-to-many" relationship first. The full SQL for the table creation and order is available to view as in the "SQL for Database Structure" document.
<h3> Table Creation Order </h3>
<ol>
  <li> PROMOTION</li>
  <li> STORELOCATION</li>
  <li> CARCLASSIFICATION</li>
  <li> CAR</li>
  <li> PERSON</li>
  <li> RENTALTRANSACTION</li>
</ol>
<h2> Final Relational Model</h2>
Below is the final fully normalized relational model. After creating the tables, I populated them with data. Some example queries and their outputs can be viewed in the "Query Commands and Outputs" document.
<img src="https://user-images.githubusercontent.com/42416078/78074235-93624600-735f-11ea-932e-44feecc8a30b.png"/>

