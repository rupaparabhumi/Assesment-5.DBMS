```sql
--- product id, product name, price and product code
create table product
(PRO_ID int ,PRO_NAME varchar(20),PRO_PRICE int,PRO_COM int);

insert into product values
(101,"Mother Board",3200.00,15),
(102,"Key Board",450.00,16),
(103,"ZIP drive",250.00,14),
(104,"Speaker",550.00,16),
(105,"Monitor",5000.00,11),
(106,"DVD drive",900.00,12),
(107,"CD drive",800.00,12),
(108,"Printer",2600.00,13),
(109,"Refill cartridge",350.00,13),
(110,"Mouse",250.00,12);
```

                 product

| PRO_ID | PRO_NAME         | PRO_PRICE | PRO_COM |
| ------ | ---------------- | --------- | ------- |
| 101    | Mother Board     | 3200.00   | 15      |
| 102    | Key Board        | 450.00    | 16      |
| 103    | ZIP drive        | 250.00    | 14      |
| 104    | speaker          | 550.00    | 16      |
| 105    | Monitor          | 5000.00   | 11      |
| 106    | DVD drive        | 900.00    | 12      |
| 107    | CD drive         | 800.00    | 12      |
| 108    | Printer          | 2600.00   | 13      |
| 109    | Refill cartridge | 350.00    | 13      |
| 110    | Mouse            | 250.00    | 12      |

```sql
---1. prices are higher rhan or equal 250.Rs
--- pro_price desc and pro_name asc;

SELECT PRO_NAME , PRO_PRICE
FROM  product
WHERE PRO_PRICE >=250
ORDER by PRO_PRICE DESC , PRO_NAME ASC;
```

| PRO_NAME         | PRO_PRICE |
| ---------------- | --------- |
| Moniter          | 5000      |
| Mother Board     | 3200      |
| printer          | 2600      |
| DVD drive        | 900       |
| CD drive         | 800       |
| speaker          | 550       |
| key Board        | 450       |
| Refill cartridge | 350       |
| Mouse            | 250       |
| ZIP drive        | 250       |

```sql
---2. the cheapest item

SELECT PRO_NAME , PRO_PRICE
From product
where PRO_PRICE=
(SELECT MIN(PRO_PRICE) From product);
```

| PRO_NAME  | PRO_PRICE |
| --------- | --------- |
| ZIP drive | 250       |
| Mouse     | 250       |

```sql
--- 3.average price of the items for company

SELECT AVG(PRO_PRICE),PRO_COM
From product
Group by PRO_COM;
```

| AVG  | PRO_COM |
| ---- | ------- |
| 250  | 14      |
| 650  | 12      |
| 3200 | 15      |
| 5000 | 11      |
| 1475 | 13      |
| 500  | 16      |

```sql
--- 4.average total for all product mention the table

SELECT AVG(PRO_PRICE)
AS "Average_Price"
From product;
```

| Average_Price |
| ------------- |
| 1435          |
