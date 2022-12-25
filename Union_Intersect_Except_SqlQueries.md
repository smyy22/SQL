### 1.Actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
```sql
(SELECT first_name FROM customer)
UNION
(SELECT first_name FROM actor);
```
### 2.Actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.
```sql
(SELECT first_name FROM customer)
INTERSECT
(SELECT first_name FROM actor);
```
### 3.Actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
```sql
(SELECT first_name FROM customer)
EXCEPT
(SELECT first_name FROM actor);
```
### 4.İlk 3 sorguyu tekrar eden veriler için de yapalım.
```sql
(SELECT first_name FROM customer)
UNION ALL
(SELECT first_name FROM actor);
```
```sql
(SELECT first_name FROM customer)
INTERSECT ALL
(SELECT first_name FROM actor);
```
```sql
(SELECT first_name FROM customer)
EXCEPT ALL
(SELECT first_name FROM actor);
```
<h2>Not:</h2>

***UNION:*** *Farklı SELECT sorgularıyla oluşan sonuçları tek bir sonuç kümesi haline getirir. Sorguların sütun sayıları eşit olmalıdır ve veri tipleri aynı olmalıdır.
**UNION ALL** ile de tekrar eden verileri görebiliriz.*

***INTERSECT:*** *Farklı SELECT sorguları sonucu kesişen verileri bulmamıza yarar.*

***EXCEPT:*** *İlk sorguda olup ancak ikinci sorguda olmayan verileri gösterir.Tekrar edenleri görmek için EXCEPT ALL kullanırız.*
