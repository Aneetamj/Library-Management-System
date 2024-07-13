# Library-Management-System
You are going to build a project based on Library Management System. It keeps track of all information about books in the library, their cost, status and total number of books available in the library.

Create a database named library and following TABLES in the database: 

1. Branch 
2. Employee 
3. Books
4. Customer
5. IssueStatus
6. ReturnStatus


-- create database library

create database library;

use library;

-- create table branch

create table branch(Branch_no int primary key,Manager_Id int,Branch_Address varchar(225),Contact_no int);

-- create table employee

create table employee(emp_id int primary key, emp_name varchar(50),position varchar(50),salary float,branch_no int,
foreign key (branch_no) references branch(branch_no));

-- create table books

create table books(isbn int primary key,book_title varchar(150),category varchar(150), rental_price float, status varchar(3),
author varchar(150),publisher varchar(150));

-- create table customer
create table customer(customer_id int primary key ,customer_name varchar(50),customer_address varchar(225),reg_date date );

-- create table issuestatus 

create table issuestatus(issue_id int primary key,issued_cust int,issued_book_name varchar(150), issue_date date, isbn_books int,
foreign key (issued_cust) references customer(customer_id), foreign key (isbn_books) references books(isbn));

-- create table returnstatus 

create table returnstatus(return_id int primary key, return_cust int, return_book_name varchar(150), return_date date, isbn_book2 int,
foreign key (isbn_book2) references books(isbn));

-- Insert values into Branch table

insert into branch values (1, 101, '123 Library St', '123456789'),(2, 102, '456 Book Rd', '987654321'),
(3, 103, '789 Novel Ave', '555555555'), (4, 104, '101 Fiction Blvd', '444444444'), (5, 105, '202 Nonfiction Ln', '333333333'),
(6, 106, '303 Literature Dr', '222222222'), (7, 107, '404 Reading St', '111111111'), (8, 108, '505 Bookstore Ct', '666666666'),
 (9, 109, '606 Shelf Rd', '777777777'), (10, 110, '707 Author Pl', '888888888');
 
 -- Insert values into Employee table
 
insert into employee values (1, 'Alice Johnson', 'Manager', 60000, 1),(2, 'Bob Smith', 'Assistant', 40000, 1),
(3, 'Carol White', 'Manager', 60000, 2),(4, 'Dave Brown', 'Assistant', 40000, 2),(5, 'Eve Black', 'Manager', 60000, 3),
(6, 'Frank Green', 'Assistant', 40000, 3),(7, 'Grace Blue', 'Manager', 60000, 4),(8, 'Hank Yellow', 'Assistant', 40000, 4),
(9, 'Ivy Red', 'Manager', 60000, 5),(10, 'Jack Purple', 'Assistant', 40000, 5);

-- Insert values into Books table

insert into books values ('316148410', 'The Great Gatsby', 'Fiction', 10.99, 'yes', 'F. Scott Fitzgerald', 'Scribner'),
('014028334', '1984', 'Dystopian', 9.99, 'no', 'George Orwell', 'Penguin Books'),
('061120084', 'To Kill a Mockingbird', 'Fiction', 8.99, 'yes', 'Harper Lee', 'J.B. Lippincott & Co.'),
('743273565', 'The Catcher in the Rye', 'Fiction', 7.99, 'no', 'J.D. Salinger', 'Little, Brown and Company'),
('451621776', 'Pride and Prejudice', 'Romance', 6.99, 'yes', 'Jane Austen', 'T. Egerton'),
('452284234', 'The Hobbit', 'Fantasy', 9.99, 'yes', 'J.R.R. Tolkien', 'George Allen & Unwin'),
('553213117', 'Fahrenheit 451', 'Dystopian', 7.99, 'no', 'Ray Bradbury', 'Ballantine Books'),
('316769485', 'The Alchemist', 'Fiction', 10.99, 'yes', 'Paulo Coelho', 'HarperTorch'),
('375504203', 'Life of Pi', 'Adventure', 8.99, 'no', 'Yann Martel', 'Knopf Canada'),
('743273503', 'Angels & Demons', 'Thriller', 6.99, 'yes', 'Dan Brown', 'Pocket Books');

-- Insert values into Customer table

insert into customer values (1, 'John Doe', '789 Maple St', '2022-01-01'),(2, 'Jane Smith', '456 Oak St', '2022-02-01'),
(3, 'Jim Beam', '123 Pine St', '2022-03-01'),(4, 'Jill Hill', '456 Cedar St', '2022-04-01'),(5, 'Jack Black', '789 Birch St', '2022-05-01'),
(6, 'Jenny White', '123 Walnut St', '2022-06-01'),(7, 'Jason Green', '456 Ash St', '2022-07-01'),(8, 'Jessica Blue', '789 Elm St', '2022-08-01'),
(9, 'Jeremy Yellow', '123 Poplar St', '2022-09-01'),(10, 'Julia Red', '456 Fir St', '2022-10-01');

-- Insert values into IssueStatus table

insert into issuestatus values (1, 1, 'The Great Gatsby', '2023-03-01', '316148410'),(2, 2, '1984', '2023-04-01', '014028334'),
(3, 3, 'To Kill a Mockingbird', '2023-05-01', '061120084'),(4, 4, 'The Catcher in the Rye', '2023-06-01', '743273565'),
(5, 5, 'Pride and Prejudice', '2023-07-01', '451621776'),(6, 6, 'The Hobbit', '2023-08-01', '452284234'),
(7, 7, 'Fahrenheit 451', '2023-09-01', '553213117'),(8, 8, 'The Alchemist', '2023-10-01', '316769485'),
(9, 9, 'Life of Pi', '2023-11-01', '375504203'),(10, 10, 'Angels & Demons', '2023-12-01', '743273503');

-- Insert values into ReturnStatus table

insert into returnstatus values (1, 1, 'The Great Gatsby', '2023-03-15', '316148410'),(2, 2, '1984', '2023-04-15', '014028334'),
(3, 3, 'To Kill a Mockingbird', '2023-05-15', '061120084'),(4, 4, 'The Catcher in the Rye', '2023-06-15', '743273565'),
(5, 5, 'Pride and Prejudice', '2023-07-15', '451621776'),(6, 6, 'The Hobbit', '2023-08-15', '452284234'),
(7, 7, 'Fahrenheit 451', '2023-09-15', '553213117'),(8, 8, 'The Alchemist', '2023-10-15', '316769485'),
(9, 9, 'Life of Pi', '2023-11-15', '375504203'),(10, 10, 'Angels & Demons', '2023-12-15', '743273503');


-- Retrieve the book title, category, and rental price of all available books. 
select book_title, category,rental_price, status from books where status='yes';

-- List the employee names and their respective salaries in descending order of salary. 
select emp_name,salary from employee order by salary desc;

-- Retrieve the book titles and the corresponding customers who have issued those books. 
select b.book_title, c.customer_name from books b join issuestatus i on b.isbn = i.isbn_books
join customer c on i.issued_cust = c.customer_id;

-- Display the total count of books in each category. 
select category, count(*) as total_books from books group by category;

-- Retrieve the employee names and their positions for the employees whose salaries are above Rs.50,000. 
select emp_name, position from employee where salary > 50000;

-- List the customer names who registered before 2022-01-01 and have not issued any books yet. 
select c.customer_name from customer c left join issuestatus i on c.customer_id = i.issued_cust
where c.reg_date < '2022-01-01' and i.issued_cust is null;

-- Display the branch numbers and the total count of employees in each branch. 
select branch_no, count(*) as total_employees from employee group by branch_no;

-- Display the names of customers who have issued books in the month of June 2023.
select c.customer_name from customer c join issuestatus i on c.customer_id = i.issued_cust
where i.issue_date between '2023-06-01' and '2023-06-30';

--  Retrieve book_title from book table containing history. 
select book_title from books where book_title like '%history%';

-- Retrieve the branch numbers along with the count of employees for branches having more than 5 employees
select branch_no, count(*) as total_employees from employee group by branch_no having count(*) > 5;

-- Retrieve the names of employees who manage branches and their respective branch addresses.
select e.emp_name, b.branch_address from employee e join branch b on e.branch_no = b.branch_no where position = 'Manager';

--  Display the names of customers who have issued books with a rental price higher than Rs. 25.
select c.customer_name from customer c join issuestatus i on c.customer_id = i.issued_cust
join books b on i.isbn_books = b.isbn where b.rental_price > 25;
