# Лабораторна робота 1. Робота з СУБД PostgreSQL та основи SQL

## Загальна інформація

**Здобувач освіти:** Фищук Богдан Сергійович

**Група:** ІПЗ-31

**Обраний рівень складності:** 3

**Посилання на проєкт:** https://supabase.com/dashboard/project/siollrknrvddtvhmlbbg/editor/17439?schema=public

## Виконання завдань

## Рівень 1

### 2.Створити запити з використанням INNER JOIN для отримання інформації з кількох пов'язаних таблиць.

```sql
SELECT p.product_name, c.category_name, p.unit_price
FROM products p
INNER JOIN categories c ON p.category_id = c.category_id;
```

Результат: 

Скріншот

<img width="975" height="523" alt="image" src="https://github.com/user-attachments/assets/075d3214-37c5-4e3e-8a3e-dcafe13ad25f" />

### 3.Використати LEFT JOIN для включення всіх записів з головної таблиці.

```sql
SELECT c.contact_name, c.customer_type,
       COUNT(o.order_id) as order_count,
       COALESCE(SUM(o.freight), 0) as total_freight
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.contact_name, c.customer_type;
```

Результат: 

Скріншот

<img width="814" height="530" alt="image" src="https://github.com/user-attachments/assets/4a1f952b-6729-4619-ac4a-1aaefbb32272" />

### 4.Створити запит з множинними з'єднаннями (мінімум 3 таблиці).

```sql
SELECT 
    o.order_id,
    o.order_date,
    c.contact_name AS customer,
    e.last_name AS employee
FROM public.orders AS o
JOIN public.customers AS c 
    ON o.customer_id = c.customer_id
JOIN public.employees AS e 
    ON o.employee_id = e.employee_id;
```

Результат: 

Скріншот

<img width="796" height="475" alt="image" src="https://github.com/user-attachments/assets/8354ef30-908d-4e83-89ad-7de050735e3f" />

### 6.Використати функції COUNT, SUM, AVG, MIN, MAX для обчислення статистичних показників.

```sql
SELECT 
    e.last_name AS employee,
    COUNT(*) AS total_orders,
    SUM(o.freight) AS total_freight,
    ROUND(AVG(o.freight), 2) AS avg_freight,
    MIN(o.freight) AS min_freight,
    MAX(o.freight) AS max_freight
FROM orders o
JOIN employees e ON o.employee_id = e.employee_id
GROUP BY e.last_name
```

Результат: 

Скріншот

<img width="855" height="439" alt="image" src="https://github.com/user-attachments/assets/796d67a0-c628-46c0-bbbf-5ed3f1cd4c0e" />

### 6.Використати функції COUNT, SUM, AVG, MIN, MAX для обчислення статистичних показників.

```sql
SELECT 
    e.last_name AS employee,
    COUNT(*) AS total_orders,
    SUM(o.freight) AS total_freight,
    ROUND(AVG(o.freight), 2) AS avg_freight,
    MIN(o.freight) AS min_freight,
    MAX(o.freight) AS max_freight
FROM orders o
JOIN employees e ON o.employee_id = e.employee_id
GROUP BY e.last_name
```

Результат: 

Скріншот

<img width="855" height="439" alt="image" src="https://github.com/user-attachments/assets/796d67a0-c628-46c0-bbbf-5ed3f1cd4c0e" />

## Висновки

Загалом виконані завдання довели, що SQL є потужним інструментом для роботи з базами даних: від простих вибірок і підрахунків до складних аналітичних звітів. Нестандартні запити допомогли краще зрозуміти логіку поєднання умов, використання агрегатних функцій і групування, а також можливості аналізу часових та бізнесових закономірностей. Отриманий досвід можна застосовувати для реальних завдань управління та аналізу інформації.

**Самооцінка**: 5

**Обгрунтування**: Я виконав усі поставлені вимоги та додатково реалізував нестандартні приклади для високої оцінки.
