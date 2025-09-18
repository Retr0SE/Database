# Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL

## Загальна інформація

**Здобувач освіти:** Фищук Богдан Сергійович

**Група:** ІПЗ-31

**Обраний рівень складності:** 3

**Посилання на проєкт:** https://siollrknrvddtvhmlbbg.supabase.co

## Виконання завдань

### Отримати всі записи з таблиці customers.

```sql
-- Завдання 1.1
SELECT * FROM customers
```

Результат: Отримано 15 записів клієнтів, включаючи як фізичних осіб, так і юридичні особи з різних міст України.

Скріншот

<img width="1484" height="561" alt="image" src="https://github.com/user-attachments/assets/c915fc02-607e-4169-b196-ccb5c9c043bf" />


### Вивести тільки назви товарів і їхні ціни з таблиці products.

```sql
-- Завдання 1.2
SELECT product_name, unit_price FROM products
```

Результат: Виведено тільки назви товарів і їхні ціни з таблиці products.

Скріншот

<img width="839" height="558" alt="image" src="https://github.com/user-attachments/assets/072fcb74-7c30-4f82-b37a-744d094a35ac" />

### Показати контактні дані всіх співробітників (ім'я, прізвище, телефон, email).

```sql
--- Завдання 1.3
SELECT first_name, middle_name, phone,email FROM employees
```

Результат: Показані контактні дані всіх співробітників (ім'я, прізвище, телефон, email)..

Скріншот

<img width="825" height="554" alt="image" src="https://github.com/user-attachments/assets/71bb6a21-59ee-47a3-a839-95c97eb86403" />

### Знайти всіх клієнтів з міста Київ.

```sql
-- Завдання 2.1
SELECT * FROM customers WHERE city = 'Київ'
```

Результат: Знайдено всіх клієнтів з міста Київ.

Скріншот

<img width="1483" height="402" alt="image" src="https://github.com/user-attachments/assets/d7f75558-44ba-4021-b746-438a8dcb95e5" />

### Вивести товари, які коштують більше 25000 грн.

```sql
-- Завдання 2.2
SELECT * FROM products WHERE unit_price > 25000
```

Результат: Виведено товари, які коштують більше 25000 грн.

Скріншот

<img width="1486" height="557" alt="image" src="https://github.com/user-attachments/assets/64cb2623-4ed6-40b0-b719-eb913360f2a6" />

### Показати всі замовлення зі статусом 'delivered'.

```sql
-- Завдання 2.3
SELECT * FROM orders 
WHERE order_status = 'delivered'
```

Результат: 

Скріншот

<img width="1483" height="561" alt="image" src="https://github.com/user-attachments/assets/d6ad28ce-8aef-4c9c-b3e8-a3e3972fcf79" />

### Знайти співробітників, які працюють у відділі продажів (посада містить слово "продаж").

```sql
-- Завдання 2.4
SELECT * FROM employees
WHERE title like '%продаж%'
```

Результат: 

Скріншот

<img width="1486" height="556" alt="image" src="https://github.com/user-attachments/assets/be1a9386-ff83-4fd4-ae1f-fb3df239ff31" />

### Відсортувати товари за зростанням ціни.

```sql
-- Завдання 3.1
SELECT * FROM products 
ORDER BY unit_price ASC 
```

Результат: 

Скріншот

<img width="1486" height="553" alt="image" src="https://github.com/user-attachments/assets/b2ffe6a5-abb7-4ca1-81e1-d33b4008ff75" />

### Показати клієнтів в алфавітному порядку за іменем контактної особи.

```sql
-- Завдання 3.2
SELECT * FROM customers ORDER BY contact_name
```

Результат: 

Скріншот

<img width="1487" height="552" alt="image" src="https://github.com/user-attachments/assets/adacdc9e-c584-453e-8ca9-410e54bac2bc" />

### Вивести замовлення від найновіших до найстаріших.

```sql
-- Завдання 3.3
SELECT * FROM orders 
ORDER BY order_date
```

Результат:

Скріншот

<img width="1488" height="557" alt="image" src="https://github.com/user-attachments/assets/3f3a3865-b602-40b3-94cc-d2c1429e77bf" />

### Показати перші 10 найдорожчих товарів.

```sql
SELECT * FROM products
ORDER BY unit_price DESC LIMIT 10
```

Результат: 

Скріншот

<img width="1485" height="546" alt="image" src="https://github.com/user-attachments/assets/f333fadd-baf2-4257-accf-196551b1d0ad" />

### Вивести 5 останніх замовлень (за датою).

```sql
-- Завдання 4.3
SELECT * FROM orders ORDER BY order_date DESC LIMIT 5 
```

Результат: 

Скріншот

<img width="1485" height="548" alt="image" src="https://github.com/user-attachments/assets/e2678254-2d0d-4595-acd8-aed684dee73e" />

### Отримати перших 8 клієнтів в алфавітному порядку.

```sql
-- Завдання 4.4
SELECT * FROM customers ORDER BY contact_name ASC LIMIT 8 
```

Результат: 

Скріншот

<img width="1487" height="549" alt="image" src="https://github.com/user-attachments/assets/63942e10-2b81-425e-b235-ebb19c771da7" />

### Знайти всіх клієнтів, чиї імена починаються на "Іван".

```sql
-- Завдання 1.1
SELECT * FROM customers WHERE contact_name LIKE 'Іван%'
```

Результат: 

Скріншот

<img width="1494" height="548" alt="image" src="https://github.com/user-attachments/assets/a008adba-20fb-4133-bfd2-0a7c490ce4f2" />

### Вивести товари, в назві яких є слово "phone" або "телефон".

```sql
-- Завдання 1.2
SELECT * FROM products 
WHERE product_name LIKE '%phone%' 
OR product_name LIKE '%телефон%'
```

Результат: 

Скріншот

<img width="1487" height="525" alt="image" src="https://github.com/user-attachments/assets/097b62bf-be70-4903-be66-e9836da68e9b" />

### В таблиці orders вивести назву доставки яка починається на 'Нова'.

```sql
-- Завдання 1.3
SELECT * FROM orders 
WHERE ship_via LIKE 'Нова%'
```

Результат: 

Скріншот

<img width="1486" height="548" alt="image" src="https://github.com/user-attachments/assets/80cc809d-8222-4486-ba3e-f42e929be904" />

### Знайти назву доставки яка закінчується словом Є 'Пошта'.

```sql
-- Завдання 1.3
SELECT * FROM orders 
WHERE ship_via LIKE '%Пошта'
```

Результат: 

Скріншот

<img width="1489" height="547" alt="image" src="https://github.com/user-attachments/assets/455f8df5-3db4-4fa0-8a43-ea0b1b63bb5d" />

### Вивести область яка закінчується на 'зька'.


```sql
-- Завдання 1.3
SELECT * FROM regions 
WHERE region_name LIKE '%зька%'
```

Результат: 

Скріншот

<img width="967" height="478" alt="image" src="https://github.com/user-attachments/assets/0dbe7b47-af59-4aef-966f-7d12cee03890" />

### Знайти товари дорожчі за 15000 грн і дешевші за 50000 грн.

```sql
-- Завдання 2.1
SELECT * FROM products 
WHERE unit_price > 15000 AND unit_price < 50000
```

Результат: 

Скріншот

<img width="1493" height="542" alt="image" src="https://github.com/user-attachments/assets/7c152258-b344-4908-abcb-707a1b6cb73a" />

### Вивести клієнтів з Києва або Львова, які є юридичними особами.

```sql
-- Завдання 2.2
SELECT * FROM customers
WHERE city = 'Київ' AND customer_type = 'company'
OR city = 'Львів' AND customer_type = 'company'
```

Результат: 

Скріншот

<img width="1484" height="370" alt="image" src="https://github.com/user-attachments/assets/4f9c3a94-8393-4fa2-b66b-191a0684381a" />

### Вибрати всі замовлення з таблиці orders, у яких місто доставки — «Київ» і дата замовлення — 20 січня 2024 року.

```sql
-- Завдання 2.3
SELECT * FROM orders
WHERE ship_city = 'Київ'
  AND order_date = '2024-01-20'
```

Результат: 

Скріншот

<img width="1484" height="354" alt="image" src="https://github.com/user-attachments/assets/d187cf5c-b48a-47f5-821b-6151a5702d2c" />

### вибирає ідентифікатор замовлення, ідентифікатор клієнта, дату замовлення та місто доставки з таблиці orders для тих замовлень, що були зроблені у місті «Київ» у період '2024-01-01' і '2024-06-30'.

```sql
-- Завдання 2.3
SELECT order_id, customer_id, order_date, ship_city
FROM orders
WHERE ship_city = 'Київ'
AND order_date BETWEEN '2024-01-01' AND '2024-06-30';
```

Результат: 

Скріншот

<img width="655" height="439" alt="image" src="https://github.com/user-attachments/assets/36bd6d65-e961-4747-9172-aaf6a889a0eb" />

### Вибрати номер замовлення, дату, місто доставки та статус із таблиці orders для всіх замовлень, оформлених починаючи з 1 січня 2024 року, крім тих, що вже мають статус «delivered».

```sql
-- Завдання 2.3
SELECT order_id, order_date, ship_city, order_status
FROM orders
WHERE order_date >= '2024-01-01'
AND NOT order_status = 'delivered';
```

Результат: 

Скріншот

<img width="600" height="413" alt="image" src="https://github.com/user-attachments/assets/e1ee0e42-5711-4e01-86e9-58639e295d40" />

### Вибрати товари, у яких кількість на складі менше мінімального рівня замовлення, або кількість замовлених товарів більша за 12.

```sql
-- Завдання 2.3
SELECT product_id, product_name, units_in_stock, units_on_order, reorder_level
FROM products
WHERE (units_in_stock < reorder_level AND units_in_stock > 0)
   OR units_on_order > 12;

```

Результат: 

Скріншот

<img width="990" height="478" alt="image" src="https://github.com/user-attachments/assets/ba5627f0-e11e-4ed5-b31a-e695c8f68025" />

### Вивести клієнтів з міст Київ, Харків, Одеса, Дніпро.

```sql
-- Завдання 3.1
SELECT * FROM customers WHERE city IN ('Київ', 'Харків', 'Одеса', 'Дніпро');
```

Результат: 

Скріншот

<img width="1488" height="517" alt="image" src="https://github.com/user-attachments/assets/bf246012-1f84-4923-84b8-03ebce1c2179" />

### Знайти товари в ціновому діапазоні від 10000 до 30000 грн.

```sql
-- Завдання 3.2
SELECT * FROM products WHERE unit_price BETWEEN 10000 AND 30000;
```

Результат: 

Скріншот

<img width="1488" height="551" alt="image" src="https://github.com/user-attachments/assets/eed18b2a-165b-45f9-96e5-52c2118fd60a" />

### Вибрати всі записи з таблиці customers, у яких поле company_name має значення NULL.

```sql
-- Завдання 3.3
SELECT * FROM customers WHERE company_name IS NULL;
```

Результат: 

Скріншот

<img width="1485" height="543" alt="image" src="https://github.com/user-attachments/assets/8e3bce9a-cb56-449a-bdb5-32f44d8628df" />

### Вибрати всі записи з таблиці customers, у яких поле company_name має значення NOT NULL.

```sql
-- Завдання 3.3
SELECT * FROM customers WHERE company_name IS NOT NULL;
```

Результат: 

Скріншот

<img width="1489" height="488" alt="image" src="https://github.com/user-attachments/assets/ab181b55-7a0e-4c5f-ad75-14aeff0b88a4" />


## Висновки

**Самооцінка**: 5

**Обгрунтування**: [обґрунтування самооцінки]
