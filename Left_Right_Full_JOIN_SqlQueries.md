### 1.City tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
```sql
SELECT city, country FROM city
LEFT JOIN country ON city.country_id=country.country_id;
```
### 2.Customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
```sql
SELECT first_name, last_name, payment_id FROM payment
RIGHT JOIN customer ON payment.customer_id=customer.customer_id;
```
### 3.Customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.
```sql
SELECT rental_id, first_name, last_name FROM rental
FULL OUTER JOIN customer ON customer.customer_id= rental.customer_id;
```
