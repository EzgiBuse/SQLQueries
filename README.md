HW7

SELECT rating, COUNT(*) as film_sayisi FROM film GROUP BY rating;

SELECT replacement_cost, COUNT(*) as film_sayisi FROM film GROUP BY replacement_cost HAVING COUNT(*) > 50;

SELECT store_id, COUNT(*) as musteri_sayisi FROM customer GROUP BY store_id;

SELECT country_id, COUNT(*) as sehir_sayisi FROM city GROUP BY country_id ORDER BY sehir_sayisi DESC LIMIT 1;
