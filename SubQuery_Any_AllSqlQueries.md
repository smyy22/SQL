### 1.Film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
```sql
SELECT COUNT(*) FROM film WHERE length > (SELECT AVG(length) FROM film);
```
### 2.Film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
```sql
SELECT COUNT(*) FROM film WHERE rental_rate=(SELECT MAX(rental_rate) FROM film);
```
### 3.Film tablosunda en düşük rental_rate ve en düşüK replacement_cost değerlerine sahip filmleri sıralayınız.
```sql
SELECT * FROM film WHERE rental_rate=(SELECT MIN(rental_rate) FROM film) AND 
replacement_cost=(SELECT MIN(replacement_cost) FROM film);
```
### 4.Payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
```sql
SELECT payment.customer_id ,customer.first_name , customer.last_name, COUNT(payment.customer_id) AS Sum 
FROM customer 
INNER JOIN payment 
ON customer.customer_id = payment.customer_id 
GROUP BY customer.first_name , customer.last_name, payment.customer_id
ORDER BY Sum DESC;
```
