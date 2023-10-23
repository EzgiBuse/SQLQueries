HW8

CREATE TABLE employee (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    birthday DATE,
    email VARCHAR(100)
);

INSERT INTO employee (name, birthday, email) VALUES ('John Doe', '1990-05-15', 'johndoe@example.com');
-- Diğer 49 satır için de aynı yapı kullanılabilir.

UPDATE employee SET name = 'Jane Doe' WHERE id = 1;
UPDATE employee SET email = 'janedoe@example.com' WHERE id = 2;

DELETE FROM employee WHERE id = 1;
DELETE FROM employee WHERE name = 'Jane Doe';

HW9

SELECT city.city, country.country
FROM city
INNER JOIN country ON city.country_id = country.country_id;


SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
INNER JOIN customer ON payment.customer_id = customer.customer_id;


SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
INNER JOIN customer ON rental.customer_id = customer.customer_id;

HW10

SELECT city.city, country.country
FROM city
LEFT JOIN country ON city.country_id = country.country_id;

SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
RIGHT JOIN customer ON payment.customer_id = customer.customer_id;

SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
FULL JOIN customer ON rental.customer_id = customer.customer_id;


HW11

SELECT first_name FROM actor
UNION
SELECT first_name FROM customer;


SELECT first_name FROM actor
INTERSECT
SELECT first_name FROM customer;

SELECT first_name FROM actor
EXCEPT
SELECT first_name FROM customer;


HW12

SELECT COUNT(*) FROM film WHERE length > (SELECT AVG(length) FROM film);

SELECT COUNT(*) FROM film WHERE rental_rate = (SELECT MAX(rental_rate) FROM film);

SELECT * FROM film WHERE rental_rate = (SELECT MIN(rental_rate) FROM film) AND 
replacement_cost = (SELECT MIN(replacement_cost) FROM film);

SELECT customer_id, COUNT(*) as transaction_count FROM payment GROUP BY customer_id ORDER BY transaction_count DESC;

