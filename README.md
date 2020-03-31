<h1> Relational Database Development </h1>
<h2> The Scenario </h2>
The challenge is to develop a relational database using Oracle SQL Developer for a hypothetical car rental business with several addresses. The business rents multiple different types of cars, which each have their own respective rental prices. The rental pricing is also dependent upon available promotions. Additionally, the business keeps track of all of its customers and employees. It is also possible to be both an employee and a customer at the same time.
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
<h2> Table Creation </h2>
After diving into the details, I determined that it was necessary to create 6 tables: Car, CarClassification, Promotion, RentalTransaction, and StoreLocation. I listed the attributes that I would keep track of, and then designed a data dictionary (attached as another file in this repository). 
