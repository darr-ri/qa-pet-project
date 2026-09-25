# SQL-запросы

**Инструмент:** SQLite Online

**Схема БД:**
- Таблица users
![img_25.png](img_25.png)

- Таблица products
![img_26.png](img_26.png)

- Таблица orders
![img_27.png](img_27.png)

- Таблица order_items
![img_28.png](img_28.png)

## 1. Простые SELECT
- SELECT * FROM users
![img.png](img.png)

- SELECT username, email FROM users
![img_1.png](img_1.png)

- SELECT * FROM users WHERE role = 'admin'
![img_2.png](img_2.png)

- SELECT * FROM products ORDER BY price ASC
![img_3.png](img_3.png)

- SELECT * FROM users LIMIT 3;
![img_4.png](img_4.png)

## 2. Фильтрация WHERE
- SELECT * FROM products WHERE price > 15
![img_5.png](img_5.png)

- SELECT * FROM users WHERE created_at > '2026-03-01'
![img_6.png](img_6.png)

- SELECT * FROM orders WHERE status IN ('new', 'completed')
![img_7.png](img_7.png)

- SELECT * FROM products WHERE price BETWEEN 10 AND 30
![img_8.png](img_8.png)

- SELECT * FROM users WHERE username LIKE '%user%'
![img_9.png](img_9.png)

## 3. Агрегатные функции
- SELECT COUNT(*) FROM orders WHERE status = 'completed'
![img_10.png](img_10.png)

- SELECT AVG(price) FROM products
![img_11.png](img_11.png)

## 4. GROUP BY 
- SELECT status, COUNT(*) AS order_count
  FROM orders
  GROUP BY status
![img_12.png](img_12.png)

- SELECT user_id, COUNT(*) AS order_count
  FROM orders
  GROUP BY user_id
  HAVING COUNT(*) > 1
![img_13.png](img_13.png)

## 6. JOIN

- SELECT u.username, o.id AS order_id, o.status, o.total
  FROM orders o
  INNER JOIN users u ON o.user_id = u.id
![img_14.png](img_14.png)

## 7. INSERT, UPDATE, DELETE

- INSERT INTO users (id, username, email, role, created_at)
  VALUES (6, 'new_user', 'new@example.com', 'customer', '2026-09-25')
![img_15.png](img_15.png)

- UPDATE users SET role = 'admin' WHERE id = 6
![img_16.png](img_16.png)

- DELETE FROM users WHERE id = 6
![img_20.png](img_20.png)

## Практические сценарии 

Сценарий 1. Проверить, что заказ создан

Пользователь оформил заказ в UI. Проверяем в БД

- SELECT * FROM orders
 WHERE user_id = 1
 ORDER BY created_at DESC
 LIMIT 1
![img_21.png](img_21.png)

Если запись есть и status = 'new' — заказ создан корректно.

Сценарий 2. Найти заказы без пользователей

- SELECT o.id, o.user_id
  FROM orders o
  LEFT JOIN users u ON o.user_id = u.id
  WHERE u.id IS NULL
![img_22.png](img_22.png)

Если результат не пустой — баг целостности данных.

Сценарий 3. Найти дубли email

- SELECT email, COUNT(*) AS cnt
  FROM users
  GROUP BY email
  HAVING COUNT(*) > 1
![img_23.png](img_23.png)

Если результат есть — баг уникальности.

Сценарий 4. Найти товары с отрицательной ценой

- SELECT * FROM products WHERE price < 0;
![img_24.png](img_24.png)

Если есть — критический баг.

