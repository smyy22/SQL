### 1.Film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
```sql
SELECT rating FROM film GROUP BY rating;
```
### 2.Film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
```sql
SELECT replacement_cost, COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*)>50;
```
### 3.Customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 
```sql
SELECT store_id, Count(*) FROM customer GROUP BY store_id;
```
### 4.City tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.
```sql
SELECT Count(city), country_id FROM city GROUP BY country_id ORDER BY Count(city) DESC LIMIT 1;
```
</br>

***Notes:***

*HAVING -> gruplandırılmış verilere koşul eklemek için kullanılır.*

*WHERE  -> satırlara koşul eklemek için kullanılır.*
