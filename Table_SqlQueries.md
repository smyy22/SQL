### 1.Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```sql
CREATE TABLE employee(
	id INTEGER PRIMARY KEY,
	name VARCHAR(50) NOT NULL,
	birthday DATE,
	email VARCHAR(100)
);
```
### 2.Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```sql
insert into employee (name, birthday, email) values ('Mirna', '16-07-2022', 'mlowre0@about.com');
insert into employee (name, birthday, email) values ('Judie', '06-04-2022', 'jsharrard1@dropbox.com');
insert into employee (name, birthday, email) values ('Bale', '28-03-2022', 'bshute2@cnn.com');
insert into employee (name, birthday, email) values ('Arty', '02-04-2022', 'asiley3@mail.ru');
...
```
### 3.Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
```sql
UPDATE employee
SET name= 'Melis',
	email='melis@gmail.com'
WHERE id=10
RETURNING *;
```
```sql
UPDATE employee
SET name= 'Melisa',
	email='melisa@gmail.com'
WHERE name LIKE 'M%'
RETURNING *;
```
.....
### 4.Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
```sql
DELETE FROM employee WHERE id=16
RETURNING *;
```
```sql
DELETE FROM employee WHERE name LIKE '%m'
RETURNING *;
```
.....

<h2>Not:</h2>

- ***Tablo Oluşturma işlemi:***

```sql
CREATE TABLE <table_name>(
	<column_name> <data_type> <constraint>,
	...
	<column_name> <data_type> <constraint>; 
)
```
- ***Oluşturduğumuz Tablonun İçerisine Veri Eklemek İçin***
```sql
INSERT INTO employee (name, birthday, email)
VALUES
('...', '...','...'),
('...', '...','...'),
```

- ***Aynı Şablonda Yeni Bir Tablo Oluşturma Örneği:***
 
```sql
 CREATE TABLE employee2(LIKE employee);
```
- ***Ouşturduğumuz Tabloya Eski Tablodan Veri Ekleme Örneği***
```sql
INSERT INTO employee2 SELECT * FROM employee WHERE name='Sim';
``` 
- ***Eğer Yeni Tablo Oluştururken Varolan Tablonun Verisiyle Beraber Aynı Oluştrumak İstersek:***
```sql
CREATE TABLE employee3 AS SELECT * FROM employee;
``` 
- ***Eğer Tabloyu Silmek İstersek aşağıdaki kodu yazarız, IF EXISTS yazmamızın sebebi eğer tablo yoksa hata vermesin diye***
```sql
DROP TABLE IF EXISTS employee4;
```
- ***Tablodaki Veriyi Update Etmek İçin:***
```sql
UPDATE employee
SET name= 'Melis',
	email='melis@gmail.com'
WHERE id=10
RETURNING *;
```
*RETURNING ile sadece update işlemi yaptığımız veriyi alıyoruz.*

- ***Tablodaki Herhangi Bir Veriyi Silme İşlemi:***
```sql
DELETE FROM employee WHERE id=16
RETURNING *;
```

- ***PRIMARY KEY:***
 *Veri sıralarını birbirinden ayırmamızı sağlayan bir kısıtlama (constraint) yapısıdır, null değerine sahip olamaz, bir tabloda en fazla bir tane bulunur.*
 
 - ***FOREIGN KEY:***
*Bir tabloda bulunan herhangi bir sütundaki verilerin genelde başka bir tablo sütununa referans vermesi durumudur, bir tabloda birden fazla sütun olarak tanımlanabilir.*
```sql
CREATE TABLE book(
	id SERIAL PRIMARY KEY,
	title VARCHAR(100),
	page_number VARCHAR(100),
	employee_id INTEGER REFERENCES employee(id)
)
```
*Burada employee_id ile foreign key oluşturmuş olduk. Bu tablo ile employee tablosu arasında bağlantı oluşturduk.*
