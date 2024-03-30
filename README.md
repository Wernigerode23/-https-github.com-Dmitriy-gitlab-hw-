# Домашнее задание к занятию «SQL. Часть 2» - `Вернигоров Дмитрий`

### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию: 
- фамилия и имя сотрудника из этого магазина;
- город нахождения магазина;
- количество пользователей, закреплённых в этом магазине.

```sql
select concat(s.first_name , ' ', s.last_name),  c2.city, COUNT(c.customer_id) 
from staff s
join store s2 on s2.store_id = s.store_id 
join customer c on c.store_id = s2.store_id
join address a on a.address_id = s2.address_id 
join city c2 on c2.city_id = a.city_id 
group by s.staff_id, c2.city_id 
having COUNT(c.customer_id) > 300;
```
![12-4-1](./hw-12-4/12-4-1.png)

---

### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.
```sql
select COUNT(f.title)
from film f  
where f.`length`  >
  (select AVG(`length`) 
  from film);   
```
![12-4-2](./hw-12-4/12-4-2.png)

---

### Задание 3

Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.
```sql
select t1.amount_of_payments, t1.month_of_payments
from (
  select SUM(p.amount) amount_of_payments, DATE_FORMAT(p.payment_date, '%M %Y') month_of_payments 
  from sakila.payment p 
  group by DATE_FORMAT(p.payment_date, '%M %Y')) t1
order by t1.amount_of_payments desc  
limit 1;
```
![12-4-3](./hw-12-4/12-4-3.png)

---

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
