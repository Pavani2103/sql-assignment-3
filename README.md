# sql-assignment-3

-- Assignent 3

-- 1.write a query to display the orders placed by customer with phone number 030-0074321

select * From Orders INNER Join Customer ON Orders.CustomerId = Customer.id and Customer.Phone = '030-0074321';

-------------------------------------------

-- 2.  fetching all the products which are available under Category �Seafood�.

SELECT * FROM ProductTable
WHERE CATEGORY ='SeaFood'

--------------------------------------------------

-- 3. Display the orders placed by customers not in London

select * From Orders INNER Join Customer ON Orders.CustomerId = Customer.id 
and Customer.Country != 'London';

---------------------------------------------

-- 4. selects all the order which are placed for the product Chai.

select * From Orders where id = 
(Select OrderId from OrderItem Inner Join Product ON OrderItem.ProductId = Product.id and ProductName= 'Chai')

------------------------------------------------

-- 5. Write a query to display the name , department name and rating  of any given employee

SELECT E.NAME AS EMP_NAME , D.DeptName AS DEPT_NAME,E.RATING
FROM Employee E INNER JOIN Dept D
ON E.DEPTID=D.DEPTID
