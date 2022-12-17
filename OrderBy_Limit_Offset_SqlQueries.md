### 1.Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
```sql
SELECT title,length FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;
```
### 2.Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
```sql
SELECT title,length FROM film WHERE title LIKE '%n' ORDER BY length ASC OFFSET 5 LIMIT 5;
```
### 3.Customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
```sql
SELECT * FROM customer WHERE store_id=1 ORDER BY last_name DESC LIMIT 4;
```

***Notes:***

*ASC: Artan Sıralama*

*DESC: Azalan Sıralama*

*Order By kullanırken ASC veya DESC yazmadığımızda otomatik olarak ASC gibi alıp işlemi yapar.*

*LIMIT ile ne kadar sıralamak istiyorsak belirliyoruz*

*OFFSET ile sıralamak istemediğimiz kadar sayıyı belirtiyoruz*
