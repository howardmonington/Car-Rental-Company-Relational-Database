<h1> Relational Database Development </h1>
<h2> The Scenario </h2>
The challenge is to develop a relational database for a hypothetical car rental business with several addresses. The business rents multiple different types of cars, which each have their own respective rental prices. The rental pricing is also dependent upon available promotions. Additionally, the business keeps track of all of its customers and employees. It is also possible to be both an employee and a customer at the same time.
<h2> Assumptions </h2>
To better understand the constraints, I created a list of assumptions for use with table design. These assumptions were:
<li> A person does not have more than two ID numbers. </li>
<li> A person can be an employee, a customer, or both.</li>
<h2> Table Creation </h2>
After diving into the details, I determined that it was necessary to create 6 tables: Car, CarClassification, Promotion, RentalTransaction, and StoreLocation.
