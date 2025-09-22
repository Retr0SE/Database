# Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL

## Загальна інформація

**Здобувач освіти:** Фищук Богдан Сергійович

**Група:** ІПЗ-31

**Обраний рівень складності:** 3

**Посилання на проєкт:** https://supabase.com/dashboard/project/siollrknrvddtvhmlbbg/editor/17439?schema=public

## Виконання завдань

## Рівень 1

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
SELECT product_name, unit_price
FROM products
```

Результат: Виведено тільки назви товарів і їхні ціни з таблиці products.

Скріншот

<img width="839" height="558" alt="image" src="https://github.com/user-attachments/assets/072fcb74-7c30-4f82-b37a-744d094a35ac" />

### Показати контактні дані всіх співробітників (ім'я, прізвище, телефон, email).

```sql
--- Завдання 1.3
SELECT first_name, middle_name, phone,email
FROM employees
```

Результат: Показані контактні дані всіх співробітників (ім'я, прізвище, телефон, email)..

Скріншот

<img width="825" height="554" alt="image" src="https://github.com/user-attachments/assets/71bb6a21-59ee-47a3-a839-95c97eb86403" />

### Знайти всіх клієнтів з міста Київ.

```sql
-- Завдання 2.1
SELECT * FROM customers
WHERE city = 'Київ'
```

Результат: Знайдено всіх клієнтів з міста Київ.

Скріншот

<img width="1483" height="402" alt="image" src="https://github.com/user-attachments/assets/d7f75558-44ba-4021-b746-438a8dcb95e5" />

### Вивести товари, які коштують більше 25000 грн.

```sql
-- Завдання 2.2
SELECT * FROM products
WHERE unit_price > 25000
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

Результат: Знайдено замовлення зі статусом 'delivered'. Ці замовлення доставлені клієнтам.

Скріншот

<img width="1483" height="561" alt="image" src="https://github.com/user-attachments/assets/d6ad28ce-8aef-4c9c-b3e8-a3e3972fcf79" />

### Знайти співробітників, які працюють у відділі продажів (посада містить слово "продаж").

```sql
-- Завдання 2.4
SELECT * FROM employees
WHERE title like '%продаж%'
```

Результат: Знайдено співробітників, чия посада містить слово 'продаж'.

Скріншот

<img width="1486" height="556" alt="image" src="https://github.com/user-attachments/assets/be1a9386-ff83-4fd4-ae1f-fb3df239ff31" />

### Відсортувати товари за зростанням ціни.

```sql
-- Завдання 3.1
SELECT * FROM products 
ORDER BY unit_price ASC 
```

Результат: Виведено товари, відсортовані за ціною від найдешевшого до найдорожчого.

Скріншот

<img width="1486" height="553" alt="image" src="https://github.com/user-attachments/assets/b2ffe6a5-abb7-4ca1-81e1-d33b4008ff75" />

### Показати клієнтів в алфавітному порядку за іменем контактної особи.

```sql
-- Завдання 3.2
SELECT * FROM customers
ORDER BY contact_name
```

Результат: Показано клієнтів, відсортованих в алфавітному порядку за іменем контактної особи.

Скріншот

<img width="1487" height="552" alt="image" src="https://github.com/user-attachments/assets/adacdc9e-c584-453e-8ca9-410e54bac2bc" />

### Вивести замовлення від найновіших до найстаріших.

```sql
-- Завдання 3.3
SELECT * FROM orders 
ORDER BY order_date
```

Результат: Виведено замовленя, відсортовані за датою від найстаріших до найновіших.

Скріншот

<img width="1488" height="557" alt="image" src="https://github.com/user-attachments/assets/3f3a3865-b602-40b3-94cc-d2c1429e77bf" />

### Показати перші 10 найдорожчих товарів.

```sql
SELECT * FROM products
ORDER BY unit_price DESC LIMIT 10
```

Результат: Виведено товари з найвищою ціною, відсортовані від найдорожчого до найдешевшого.

Скріншот

<img width="1485" height="546" alt="image" src="https://github.com/user-attachments/assets/f333fadd-baf2-4257-accf-196551b1d0ad" />

### Вивести 5 останніх замовлень (за датою).

```sql
-- Завдання 4.3
SELECT * FROM orders
ORDER BY order_date DESC LIMIT 5 
```

Результат: Виведено 5 замовлень з найновішими датами, відсортованих у зворотному хронологічному порядку.

Скріншот

<img width="1485" height="548" alt="image" src="https://github.com/user-attachments/assets/e2678254-2d0d-4595-acd8-aed684dee73e" />

### Отримати перших 8 клієнтів в алфавітному порядку.

```sql
-- Завдання 4.4
SELECT * FROM customers ORDER BY contact_name ASC LIMIT 8 
```

Результат: Отримано перші 8 клієнтів, відсортованих в алфавітному порядку за іменем.

Скріншот

<img width="1487" height="549" alt="image" src="https://github.com/user-attachments/assets/63942e10-2b81-425e-b235-ebb19c771da7" />

## Рівень 2

### Знайти всіх клієнтів, чиї імена починаються на "Іван".

```sql
-- Завдання 1.1
SELECT * FROM customers WHERE contact_name LIKE 'Іван%'
```

Результат: Знайдено клієнтів, чиї контактні імена починаються на 'Іван'.

Скріншот

<img width="1494" height="548" alt="image" src="https://github.com/user-attachments/assets/a008adba-20fb-4133-bfd2-0a7c490ce4f2" />

### Вивести товари, в назві яких є слово "phone" або "телефон".

```sql
-- Завдання 1.2
SELECT * FROM products 
WHERE product_name LIKE '%phone%' 
OR product_name LIKE '%телефон%'
```

Результат: Виведено товари, назва яких містить слово 'phone' або 'телефон'.

Скріншот

<img width="1487" height="525" alt="image" src="https://github.com/user-attachments/assets/097b62bf-be70-4903-be66-e9836da68e9b" />

### В таблиці orders вивести назву доставки яка починається на 'Нова'.

```sql
-- Завдання 1.3
SELECT * FROM orders 
WHERE ship_via LIKE 'Нова%'
```

Результат: Знайдено замовлення, де назва доставки починається на 'Нова'.

Скріншот

<img width="1486" height="548" alt="image" src="https://github.com/user-attachments/assets/80cc809d-8222-4486-ba3e-f42e929be904" />

### Знайти назву доставки яка закінчується словом Є 'Пошта'.

```sql
-- Завдання 1.3
SELECT * FROM orders 
WHERE ship_via LIKE '%Пошта'
```

Результат: Знайдено замовлення, де назва доставки закінчується на 'Пошта'.

Скріншот

<img width="1489" height="547" alt="image" src="https://github.com/user-attachments/assets/455f8df5-3db4-4fa0-8a43-ea0b1b63bb5d" />

### Вивести область яка закінчується на 'зька'.


```sql
-- Завдання 1.3
SELECT * FROM regions 
WHERE region_name LIKE '%зька%'
```

Результат: Знайдено область, назва якої закінчується на 'зька'.

Скріншот

<img width="967" height="478" alt="image" src="https://github.com/user-attachments/assets/0dbe7b47-af59-4aef-966f-7d12cee03890" />

### Знайти товари дорожчі за 15000 грн і дешевші за 50000 грн.

```sql
-- Завдання 2.1
SELECT * FROM products 
WHERE unit_price > 15000 AND unit_price < 50000
```

Результат: Знайдено товари, ціна яких знаходиться в діапазоні від 15000 до 50000 грн.

Скріншот

<img width="1493" height="542" alt="image" src="https://github.com/user-attachments/assets/7c152258-b344-4908-abcb-707a1b6cb73a" />

### Вивести клієнтів з Києва або Львова, які є юридичними особами.

```sql
-- Завдання 2.2
SELECT * FROM customers
WHERE city = 'Київ' AND customer_type = 'company'
OR city = 'Львів' AND customer_type = 'company'
```

Результат: Знайдено клієнти, які є юридичними особами і знаходяться в містах Київ або Львів.

Скріншот

<img width="1484" height="370" alt="image" src="https://github.com/user-attachments/assets/4f9c3a94-8393-4fa2-b66b-191a0684381a" />

### Вибирати категорії з іменами «Електроніка» або «Побутова техніка», де є опис.

```sql
-- Завдання 2.3
SELECT category_id, category_name, description
FROM categories
WHERE category_name IN ('Електроніка', 'Побутова техніка') 
  AND description IS NOT NULL;

```

Результат: Вибрано категорії, що відповідають зазначеним критеріям.

Скріншот

<img width="877" height="293" alt="image" src="https://github.com/user-attachments/assets/9ed32ef0-6bf8-4e8c-8153-f664a4321a4c" />


### Вибирати ідентифікатор замовлення, ідентифікатор клієнта, дату замовлення та місто доставки з таблиці orders для тих замовлень, що були зроблені у місті «Київ» у період '2024-01-01' і '2024-06-30'.

```sql
-- Завдання 2.3
SELECT customer_id, company_name, city
FROM customers
WHERE NOT customer_type = 'individual'
  AND city NOT IN ('Київ', 'Одеса');

```

Результат: Вибрані замовлення, яке відповідає зазначеним критеріям.

Скріншот

<img width="649" height="313" alt="image" src="https://github.com/user-attachments/assets/21346e57-c5fe-4a5e-94ea-f0ee5efaecc1" />

### Вибрати номер замовлення, дату, місто доставки та статус із таблиці orders для всіх замовлень, оформлених починаючи з 1 січня 2024 року, крім тих, що вже мають статус «delivered».

```sql
-- Завдання 2.3
SELECT order_id, order_date, ship_city, order_status
FROM orders
WHERE order_date >= '2024-01-01'
AND NOT order_status = 'delivered';
```

Результат: Вибрані замовлення, які були оформлені після 1 січня 2024 року та не мають статусу 'delivered'.

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

Результат: Знайдено товари, що відповідають заданим критеріям: або мають недостатню кількість на складі, або мають понад 12 замовлених одиниць.

Скріншот

<img width="990" height="478" alt="image" src="https://github.com/user-attachments/assets/ba5627f0-e11e-4ed5-b31a-e695c8f68025" />

### Вивести клієнтів з міст Київ, Харків, Одеса, Дніпро.

```sql
-- Завдання 3.1
SELECT * FROM customers WHERE city IN ('Київ', 'Харків', 'Одеса', 'Дніпро');
```

Результат: Знайдено клієнтів, що знаходяться в одному з перерахованих міст.

Скріншот

<img width="1488" height="517" alt="image" src="https://github.com/user-attachments/assets/bf246012-1f84-4923-84b8-03ebce1c2179" />

### Знайти товари в ціновому діапазоні від 10000 до 30000 грн.

```sql
-- Завдання 3.2
SELECT * FROM products WHERE unit_price BETWEEN 10000 AND 30000;
```

Результат: Знайдено товари, ціна яких знаходиться в діапазоні від 10000 до 30000 грн включно.

Скріншот

<img width="1488" height="551" alt="image" src="https://github.com/user-attachments/assets/eed18b2a-165b-45f9-96e5-52c2118fd60a" />

### Вибрати всі записи з таблиці customers, у яких поле company_name має значення NULL.

```sql
-- Завдання 3.3
SELECT * FROM customers WHERE company_name IS NULL;
```

Результат: Вибрано записи клієнтів, у яких поле company_name є порожнім, що вказує на фізичних осіб.

Скріншот

<img width="1485" height="543" alt="image" src="https://github.com/user-attachments/assets/8e3bce9a-cb56-449a-bdb5-32f44d8628df" />

### Вибрати всі записи з таблиці customers, у яких поле company_name має значення NOT NULL.

```sql
-- Завдання 3.3
SELECT * FROM customers WHERE company_name IS NOT NULL;
```

Результат: Вибрано записи клієнтів, у яких поле company_name містить значення, що вказує на юридичних осіб.

Скріншот

<img width="1489" height="488" alt="image" src="https://github.com/user-attachments/assets/ab181b55-7a0e-4c5f-ad75-14aeff0b88a4" />

### Вибирати клієнтів, у яких ім’я контакту починається на «І» або «К», і які живуть у Києві чи Львові.

```sql
-- Завдання 3.4
SELECT customer_id, contact_name, city
FROM customers
WHERE (contact_name LIKE 'І%' OR contact_name LIKE 'К%')
  AND city IN ('Київ', 'Львів');

```

Результат: Знайдено клієнти, які відповідають зазначеним критеріям фільтрації.

Скріншот

<img width="891" height="300" alt="image" src="https://github.com/user-attachments/assets/38addbcf-05f8-48f8-9bf1-c642b75157e4" />

### Вибрати клієнтів з українськими телефонами (+380), але не з Києва чи Харкова.

```sql
-- Завдання 3.4
SELECT customer_id, contact_name, phone, city
FROM customers
WHERE city NOT IN ('Київ', 'Харків')
  AND phone LIKE '+380%';

```

Результат: Знайдено клієнти, які мають український номер телефону і не знаходяться у Києві або Харкові.

Скріншот

<img width="800" height="315" alt="image" src="https://github.com/user-attachments/assets/55f32c86-7e91-437b-b061-9e56126fa09c" />

### Вибрати постачальників із Києва, Львова чи Одеси, у яких email закінчується на .com.

```sql
-- Завдання 3.4
SELECT supplier_id, company_name, city, email
FROM suppliers
WHERE city IN ('Київ', 'Львів', 'Одеса')
  AND email LIKE '%.com';

```

Результат: Знайдено постачальники, що відповідають заданим критеріям.

Скріншот

<img width="729" height="238" alt="image" src="https://github.com/user-attachments/assets/d0aa6b34-4765-4356-abb1-ea88f96755ca" />

### Показати постачальників, у назві яких є слово «Торг» або «Market», і вказаний телефон.

```sql
-- Завдання 3.4
SELECT supplier_id, company_name, phone
FROM suppliers
WHERE (company_name LIKE '%Техно%' OR company_name LIKE '%Market%')
  AND phone IS NOT NULL;

```

Результат: Знайдено постачальників, назва яких містить 'Техно' або 'Market' і які мають вказаний номер телефону.

Скріншот

<img width="507" height="287" alt="image" src="https://github.com/user-attachments/assets/499dc6a8-80fa-4be9-9133-511a81d1d8c9" />

### Вивести постачальників із поштовими індексами Києва (02000–04999) або Львова (79000–79999).

```sql
-- Завдання 3.4
SELECT supplier_id, company_name, postal_code, city
FROM suppliers
WHERE postal_code BETWEEN '02000' AND '04999'
   OR postal_code BETWEEN '79000' AND '79999';

```

Результат: Знайдено постачальників, поштовий індекс якого знаходиться в зазначеному діапазоні.

Скріншот

<img width="718" height="310" alt="image" src="https://github.com/user-attachments/assets/822962be-c0f4-4ffc-a07c-b7723169477b" />

### Посортувати спочатку за містом (від А до Я), а в межах міста — за ім’ям контакту..

```sql
-- Завдання 3.5
SELECT customer_id, contact_name, city, registration_date
FROM customers
ORDER BY city ASC, contact_name ASC;

```

Результат: Виведено клієнтів, відсортованих спочатку за містом, а потім за іменем контакту в межах кожного міста.

Скріншот

<img width="844" height="346" alt="image" src="https://github.com/user-attachments/assets/d676c9e9-ad81-4c51-9e1c-13c5ae4c1ace" />

### Спочатку посортувати за назвою області (від А до Я), а всередині області — компанії у зворотному алфавіті.

```sql
-- Завдання 3.5
SELECT s.supplier_id, s.company_name, r.region_name, s.city
FROM suppliers s
JOIN regions r ON s.region_id = r.region_id
ORDER BY r.region_name ASC, s.company_name DESC;

```

Результат: Виведено постачальників, відсортованих спочатку за назвою області, а потім за назвою компанії у зворотному алфавітному порядку.

Скріншот

<img width="880" height="336" alt="image" src="https://github.com/user-attachments/assets/5a676e46-eac4-4bdd-8769-95bb4d6c4596" />

### Спочатку посортувати по категоріях, а в межах категорії — найдорожчі товари вище.

```sql
-- Завдання 3.5
SELECT product_id, product_name, category_id, unit_price, units_in_stock
FROM products
ORDER BY category_id ASC, unit_price DESC;

```

Результат: Виведено товари, відсортовані спочатку за ідентифікатором категорії, а потім за ціною від найдорожчого до найдешевшого.

Скріншот

<img width="939" height="348" alt="image" src="https://github.com/user-attachments/assets/e8ae4d73-ddd2-412d-8e67-577899c4eb6f" />

### Показати клієнтів 11–15 за датою реєстрації (новіші зверху).

```sql
-- Завдання 3.4
SELECT customer_id, contact_name, city, registration_date
FROM customers
ORDER BY registration_date DESC
LIMIT 5 OFFSET 10;

```

Результат: Виведено клієнтів з 11 по 15, відсортованих за датою реєстрації від найновіших.

Скріншот

<img width="710" height="349" alt="image" src="https://github.com/user-attachments/assets/04158281-7ced-4c46-9cd9-4d242eafa1e4" />

### Вивести «другу сторінку» постачальників по алфавіту (записи 6–10).

```sql
-- Завдання 3.5
SELECT supplier_id, company_name, city, email
FROM suppliers
ORDER BY company_name ASC
LIMIT 5 OFFSET 5;

```

Результат: Виведено постачальників з 6 по 10, відсортованих в алфавітному порядку.

Скріншот

<img width="873" height="339" alt="image" src="https://github.com/user-attachments/assets/30c4d999-d7af-47ed-a37c-f66e073d6025" />

## Рівень 3

### Знайти товари, в назві яких є "Samsung" або "Apple", але немає слова "чохол".

```sql
-- Завдання 1.1
SELECT *
FROM products
WHERE (product_name ILIKE '%Samsung%' OR product_name ILIKE '%Apple%')
  AND product_name NOT ILIKE '%чохол%';

```

Результат: Знайдено товари, назва яких містить 'Samsung' або 'Apple', але не містить 'чохол'.

Скріншот

<img width="1381" height="336" alt="image" src="https://github.com/user-attachments/assets/d7da68ec-190f-4128-98f5-6bbd99f5a18d" />

### Знайти клієнтів, чиє ім’я починається на «А» або містить «енко», але виключає тих, хто з Києва.

```sql
-- Завдання 1.2
SELECT customer_id, contact_name, city, email
FROM customers
WHERE (contact_name LIKE 'А%' OR contact_name LIKE '%енко%')
  AND city NOT LIKE 'Київ';
```

Результат: Знайдено клієнти, що відповідають заданим критеріям.

Скріншот

<img width="1080" height="360" alt="image" src="https://github.com/user-attachments/assets/41f94584-9054-416f-9c45-b70035f977e6" />

### Вивести продукти, у назві яких є «Pro» або «Ultra», але не «Demo», і з ціною > 500.

```sql
-- Завдання 1.2
SELECT product_id, product_name, unit_price
FROM products
WHERE (product_name LIKE '%Pro%' OR product_name LIKE '%Ultra%')
  AND product_name NOT LIKE '%Demo%'
  AND unit_price > 500;

```

Результат: Знайдено продукти, що відповідають заданим критеріям.

Скріншот

<img width="754" height="354" alt="image" src="https://github.com/user-attachments/assets/b8fd1623-af8b-487b-8e05-249b6d86ca24" />


### Вивести клієнтів із Львова, Одеси або Харкова, але з email, відмінним від Gmail.

```sql
-- Завдання 1.2
SELECT customer_id, contact_name, city, email, registration_date
FROM customers
WHERE city IN ('Львів', 'Одеса', 'Харків')
  AND email NOT LIKE '%@gmail.com';

```

Результат: Знайдено клієнти, що відповідають заданим критеріям.

Скріншот

<img width="1026" height="335" alt="image" src="https://github.com/user-attachments/assets/658f661a-97b0-45df-a72b-aefb9f3613fe" />

### Вивести фізичних осіб, чиє ім’я починається на «І» або «К», і телефон починається з +380.

```sql
-- Завдання 1.2
SELECT customer_id, contact_name, phone, customer_type
FROM customers
WHERE customer_type = 'individual'
  AND (contact_name LIKE 'І%' OR contact_name LIKE 'К%')
  AND phone LIKE '+380%';


```

Результат: Знайдено клієнти, що відповідають заданим критеріям.

Скріншот

<img width="856" height="360" alt="image" src="https://github.com/user-attachments/assets/bb4a5d55-8237-4af5-b393-eab5cf3d4349" />

### Знайти товари дорожчі 20000 грн (категорії 1 або 2) АБО товари дешевші 5000 грн будь-якої категорії.

```sql
-- Завдання 2.1
SELECT product_id, product_name, category_id, unit_price
FROM products
WHERE 
      (unit_price > 20000 AND category_id IN (1, 2))
   OR (unit_price < 5000);

```

Результат: Знайдено товари, що відповідають заданим критеріям.

Скріншот

<img width="838" height="338" alt="image" src="https://github.com/user-attachments/assets/abc8ed01-bc43-4f68-8320-d5db799adbd6" />

### Вивести товари дорожчі за 15000 грн у категорії 3 або 4, або дешевші за 3000 грн і в наявності більше 50 шт.

```sql
-- Завдання 2.2
SELECT product_id, product_name, category_id, unit_price, units_in_stock
FROM products
WHERE 
    ((unit_price > 15000 AND category_id IN (3, 4))
     OR (unit_price < 3000 AND units_in_stock > 50));

```

Результат: Знайдено   товари, що відповідають заданим критеріям.

Скріншот

<img width="906" height="341" alt="image" src="https://github.com/user-attachments/assets/f9b33a04-3c4f-4719-9181-a4d794bc7c33" />

### Вивести товари, які або зняті з продажу (discontinued = true) і коштують понад 10000, або продаються і коштують менше 2000.

```sql
-- Завдання 2.2
SELECT product_id, product_name, unit_price, discontinued
FROM products
WHERE 
    ((discontinued = true AND unit_price > 10000)
     OR (discontinued = false AND unit_price < 2000));

```

Результат: Знайдено 1 товар, що відповідає заданим критеріям.

Скріншот

<img width="694" height="255" alt="image" src="https://github.com/user-attachments/assets/2c1c9e54-5f64-4234-9587-88052c538a49" />

### Вивести товари, які належать до категорій 2 або 5, і при цьому або дорожчі за 12000 грн, або мають більше 100 шт. на складі.

```sql
-- Завдання 2.2
SELECT product_id, product_name, category_id, unit_price, units_in_stock
FROM products
WHERE 
    (category_id IN (2, 5) 
     AND (unit_price > 12000 OR units_in_stock > 100))

```

Результат: Знайдено товари, що відповідають заданим критеріям.

Скріншот

<img width="890" height="342" alt="image" src="https://github.com/user-attachments/assets/a8031812-b175-45b5-9485-f7bdd40806bf" />

### Створити звіт товарів з 5+ різними умовами фільтрації одночасно.

```sql
-- Завдання 3.1
SELECT product_id, product_name, category_id, unit_price, units_in_stock, units_on_order, discontinued
FROM products
WHERE unit_price BETWEEN 5000 AND 20000         -- ціновий діапазон
  AND category_id IN (1, 3, 5)                  -- вибрані категорії
  AND units_in_stock > 10                       -- є на складі
  AND units_on_order < 50                       -- небагато замовлено
  AND discontinued = false                      -- ще продається
  AND product_name NOT LIKE '%чохол%';          -- виключаємо чохли

```

Результат: Знайдено 1 товар, що відповідає всім 6-ти заданим критеріям.

Скріншот

<img width="1185" height="238" alt="image" src="https://github.com/user-attachments/assets/0bd26ace-f405-49b0-b78a-7e643fd1d74a" />

### Написати запит для аналізу клієнтської бази з множинними критеріями відбору.

```sql
-- Завдання 3.2
SELECT customer_id, company_name, contact_name, city, customer_type, registration_date
FROM customers
WHERE city IN ('Київ', 'Львів', 'Одеса')
  AND customer_type = 'individual'
  AND registration_date BETWEEN '2023-01-01' AND '2024-12-31'
  AND (email LIKE '%.ua' OR email LIKE '%.com')
  AND phone IS NOT NULL;

```

Результат: Знайдено клієнтів, що відповідають всім зазначеним критеріям.

Скріншот

<img width="1185" height="238" alt="image" src="https://github.com/user-attachments/assets/0bd26ace-f405-49b0-b78a-7e643fd1d74a" />

### Вивести підрахунок кількість товарів з ціною менше 5000 грн.

```sql
-- Завдання 4.1
SELECT COUNT(*) AS cheap_count
FROM products
WHERE unit_price < 5000;

```

Результат: Виведено, що кількість товарів з ціною менше 5000 грн становить 3.

Скріншот

<img width="312" height="209" alt="image" src="https://github.com/user-attachments/assets/f43c9bfc-859f-4fba-b925-a41fab0e775c" />

### Вивести підрахунок кількість товарів з ціною від 5000 до 20000 грн.

```sql
-- Завдання 4.1
SELECT COUNT(*) AS mid_count
FROM products
WHERE unit_price BETWEEN 5000 AND 20000;

```

Результат: Виведено, що кількість товарів з ціною в діапазоні від 5000 до 20000 грн становить 6.

Скріншот

<img width="315" height="244" alt="image" src="https://github.com/user-attachments/assets/d39fda75-15bd-46bd-9017-52312a04b968" />

### Вивести підрахунок кількість товарів з ціною понад 20 000 грн.

```sql
-- Завдання 4.1
SELECT COUNT(*) AS premium_count
FROM products
WHERE unit_price > 20000;

```

Результат: Виведено, що кількість товарів з ціною понад 20000 грн становить 16.

Скріншот

<img width="312" height="272" alt="image" src="https://github.com/user-attachments/assets/94a79c6a-503a-41f5-bcf1-e245b42db1a5" />

### Вивести кількість клієнтів у кожному місті.

```sql
-- Завдання 4.2
SELECT city, COUNT(*) AS customer_count
FROM customers
GROUP BY city
ORDER BY customer_count DESC;

```

Результат: Виведено кількість клієнтів для кожного міста, відсортовану за кількістю у спадному порядку.

Скріншот

<img width="426" height="365" alt="image" src="https://github.com/user-attachments/assets/9f1f47d6-e242-429d-be48-2b418a14473c" />

### Вивести кількість бізнесів vs фізичних осіб по містах.

```sql
-- Завдання 4.2
SELECT city, customer_type, COUNT(*) AS count_type
FROM customers
GROUP BY city, customer_type
ORDER BY city, count_type DESC;

```

Результат: Виведено кількість клієнтів, розділену за містом та типом (фізична або юридична особа).

Скріншот

<img width="443" height="301" alt="image" src="https://github.com/user-attachments/assets/2151ac04-a6ef-4d55-998b-8e27eb272129" />

### Вивести ТОП-5 міст з найбільшою кількістю клієнтів.

```sql
-- Завдання 4.2
SELECT city, COUNT(*) AS customer_count
FROM customers
GROUP BY city
ORDER BY customer_count DESC
LIMIT 5;

```

Результат: Виведено 5 міст з найбільшою кількістю клієнтів, відсортованих за цією кількістю у спадному порядку.

Скріншот

<img width="413" height="381" alt="image" src="https://github.com/user-attachments/assets/2f4c9877-8311-41e7-8717-d39531701977" />

### Вивести клієнти з міста Київ.

```sql
-- Завдання 4.2
SELECT customer_id, contact_name, company_name
FROM customers
WHERE city = 'Київ';

```

Результат: Виведено 4 клієнти, що знаходяться в місті Київ.

Скріншот

<img width="700" height="351" alt="image" src="https://github.com/user-attachments/assets/3e79df50-548e-4a87-943d-d72dd1842cf3" />

### Вивести замовлення по місяцях.

```sql
-- Завдання 4.3
SELECT DATE_TRUNC('month', order_date) AS month, COUNT(*) AS order_count
FROM orders
GROUP BY month
ORDER BY month;

```

Результат: Виведено кількість замовлень, згрупованих по місяцях, та відсортованих за датою місяця.

Скріншот

<img width="683" height="490" alt="image" src="https://github.com/user-attachments/assets/cc67eb50-932b-43f3-9dc9-5f94cdf9b115" />

### Вивести замовлення по днях тижня.

```sql
-- Завдання 4.3
SELECT TO_CHAR(order_date, 'Day') AS weekday, COUNT(*) AS order_count
FROM orders
GROUP BY weekday
ORDER BY order_count DESC;

```

Результат: Виведено кількість замовлень, згрупованих за днями тижня, відсортованих за кількістю у спадному порядку.

Скріншот

<img width="434" height="444" alt="image" src="https://github.com/user-attachments/assets/375b10f6-08ca-4bc7-b946-7edd059bfcf4" />

### Вивести кількість замовлень у кожному тижні.

```sql
-- Завдання 4.3
SELECT 
    TO_CHAR(order_date, 'IYYY-IW') AS week,
    COUNT(*) AS total_orders
FROM orders
GROUP BY week
ORDER BY week;

```

Результат: Виведено кількість замовлень, згрупованих за тижнями, відсортованих за номером тижня.

Скріншот

<img width="625" height="536" alt="image" src="https://github.com/user-attachments/assets/16241741-57b2-4e9b-8ada-5ac52f418583" />

## Креативні завдання

### Вивести найдорожчі та найдешевші товари одночасно (в межах кожної категорії).

```sql
-- Завдання 5.1
SELECT category_id, 
       MAX(unit_price) AS max_price, 
       MIN(unit_price) AS min_price
FROM products
GROUP BY category_id;

```

Результат: 

Скріншот

<img width="595" height="573" alt="image" src="https://github.com/user-attachments/assets/a4347ca1-94a5-4a23-9446-d2ba456d2f4f" />

### Розбити товари по рангам за ціною.

```sql
-- Завдання 5.2
SELECT 
    product_id,
    product_name,
    unit_price,
    RANK() OVER (ORDER BY unit_price DESC) AS price_rank
FROM products;

```

Результат: Виведено ідентифікатори категорій та відповідні максимальні та мінімальні ціни товарів у кожній з них.

Скріншот

<img width="625" height="536" alt="image" src="https://github.com/user-attachments/assets/16241741-57b2-4e9b-8ada-5ac52f418583" />

### Визначити категорію товару за ціною.

```sql
-- Завдання 5.3
SELECT 
    product_id,
    product_name,
    unit_price,
    CASE 
        WHEN unit_price < 5000 THEN 'Дешевий'
        WHEN unit_price BETWEEN 5000 AND 20000 THEN 'Середній'
        ELSE 'Преміум'
    END AS price_category
FROM products;

```

Результат: Для кожного товару виведено його ранг на основі ціни. Найдорожчий товар має ранг 1. При цьому, товари з однаковою ціною отримують однаковий ранг.

Скріншот

<img width="625" height="536" alt="image" src="https://github.com/user-attachments/assets/16241741-57b2-4e9b-8ada-5ac52f418583" />

### Знайти найдорожчий товар в кожній категорії.

```sql
-- Завдання 5.4
SELECT DISTINCT ON (category_id) -- DISTINCT ON дозволяє відібрати перший рядок для кожної групи після сортування.
    category_id,
    product_id,
    product_name,
    unit_price
FROM products
ORDER BY category_id, unit_price DESC;

```

Результат: Для кожної категорії виведено тільки один запис — найдорожчий товар. 

Скріншот

<img width="625" height="536" alt="image" src="https://github.com/user-attachments/assets/16241741-57b2-4e9b-8ada-5ac52f418583" />

### Вивести середню ціну товарів по категоріях із різницею від загальної середньої.

```sql
-- Завдання 5.5
SELECT 
    category_id,
    ROUND(AVG(unit_price), 2) AS avg_price,
    ROUND(AVG(unit_price) - (SELECT AVG(unit_price) FROM products), 2) AS diff_from_global
FROM products
GROUP BY category_id;

```

Результат: Виведено середню ціну товарів для кожної категорії, а також різницю між цією середньою ціною та загальною середньою ціною всіх товарів у базі даних.

Скріншот

<img width="625" height="536" alt="image" src="https://github.com/user-attachments/assets/16241741-57b2-4e9b-8ada-5ac52f418583" />

## Висновки

Загалом виконані завдання довели, що SQL є потужним інструментом для роботи з базами даних: від простих вибірок і підрахунків до складних аналітичних звітів. Нестандартні запити допомогли краще зрозуміти логіку поєднання умов, використання агрегатних функцій і групування, а також можливості аналізу часових та бізнесових закономірностей. Отриманий досвід можна застосовувати для реальних завдань управління та аналізу інформації.

**Самооцінка**: 5

**Обгрунтування**: Я виконав усі поставлені вимоги та додатково реалізував нестандартні приклади для високої оцінки.
