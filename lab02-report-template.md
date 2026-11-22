# Лабораторна робота 2. Створення складних SQL запитів

## Загальна інформація

**Здобувач освіти:** Стрижеус Софія
**Група:** ІПЗ-32
**Обраний рівень складності:** 2

## Виконання завдань

### Рівень 1

#### 1. З'єднання таблиць

**Завдання 1.1:** INNER JOIN - список товарів з категоріями та постачальниками


<img width="610" height="217" alt="image" src="https://github.com/user-attachments/assets/56588f7d-fe3e-4ad5-b09d-2ca5aac11bab" />

**Результат виконання:**

<img width="1116" height="493" alt="image" src="https://github.com/user-attachments/assets/b5291b67-2799-48b2-b207-841ef09940fe" />



**Пояснення:** об'єднує products, categories та suppliers за зовнішніми ключами, виводячи товари з категоріями, постачальниками та ціною (лише ті рядки, де є збіг у всіх таблицях).



**Завдання 1.2:** LEFT JOIN - клієнти з кількістю замовлень


<img width="718" height="246" alt="image" src="https://github.com/user-attachments/assets/199620e6-665c-4993-ab54-f6c9b4344277" />




**Результат виконання:**

<img width="827" height="531" alt="image" src="https://github.com/user-attachments/assets/b91d3ff0-73c4-42c4-9c88-9c88b4feb69c" />
<img width="827" height="182" alt="image" src="https://github.com/user-attachments/assets/118bd435-7c12-4c58-b0f3-cf8dd546555c" />




**Пояснення:** виводить усіх клієнтів та кількість їхніх замовлень (COUNT(o.order_id)). На відміну від INNER JOIN, зберігає клієнтів без замовлень (для них кількість дорівнює 0).



**Завдання 1.3:** Множинне з'єднання - детальна інформація про замовлення

<img width="635" height="392" alt="image" src="https://github.com/user-attachments/assets/cdf81aac-4d83-45e9-b0f6-2efca216e8b1" />


**Результат виконання:**

<img width="1788" height="546" alt="image" src="https://github.com/user-attachments/assets/60a382e7-12e3-4fbf-b8d5-a5c98a6ea621" />


**Аналіз складності:** Запит має помірну складність через з'єднання 5–6 пов'язаних сутностей (orders → customers, order_items → products → categories, suppliers). Спочатку від таблиці замовлень orders приєднуються клієнти (1:N) і позиції замовлення (1:N), після чого кожна позиція розкривається до товару (products), його категорії (categories) та постачальника (suppliers).



#### 2. Агрегатні функції

**Завдання 2.1:** Статистика товарів за категоріями

<img width="568" height="250" alt="image" src="https://github.com/user-attachments/assets/d98874b4-e407-4094-910f-9f99c679c379" />


**Результат виконання:**

<img width="931" height="508" alt="image" src="https://github.com/user-attachments/assets/24f9756d-9f27-435a-bee5-b803ebbb5113" />


**Завдання 2.2:** Продажі за регіонами з використанням HAVING

<img width="835" height="227" alt="image" src="https://github.com/user-attachments/assets/e7977b7b-18d0-4918-9d8f-4f252069dd3e" />


**Результат виконання:**

<img width="390" height="272" alt="image" src="https://github.com/user-attachments/assets/055dd1b9-ad64-42bf-9f9f-957ee72beae0" />


**Завдання 2.3:** Постачальники з кількістю товарів більше 2

<img width="552" height="193" alt="image" src="https://github.com/user-attachments/assets/4f3b37fa-b9f9-4b34-8eac-4f1234eee7a0" />


**Результат виконання:**

<img width="460" height="241" alt="image" src="https://github.com/user-attachments/assets/2e8d7861-5908-40d9-aaef-fae3f7df713b" />




#### 3. Базові підзапити

**Завдання 3.1:** Товари з ціною вище середньої по категорії

<img width="581" height="286" alt="image" src="https://github.com/user-attachments/assets/1df6c09a-7d5b-4e13-b30e-b5b5d111b37b" />


**Результат виконання:**

<img width="788" height="540" alt="image" src="https://github.com/user-attachments/assets/5d23fffc-9af7-4085-8fb0-c30f232a605f" />
<img width="787" height="133" alt="image" src="https://github.com/user-attachments/assets/e5f48b78-598a-4cde-8a2b-2ccae7bd26ac" />


**Завдання 3.2:** Клієнти з замовленнями у 2024 році

<img width="442" height="232" alt="image" src="https://github.com/user-attachments/assets/0eae2a30-8a1f-41ba-9115-ad18a7777ebf" />


**Результат виконання:**

<img width="447" height="530" alt="image" src="https://github.com/user-attachments/assets/48058c40-557e-435f-ae71-7a6ebfb22cbd" />
<img width="442" height="181" alt="image" src="https://github.com/user-attachments/assets/0f20bce4-691a-4fa4-a41f-1de0139d90c1" />


**Завдання 3.3:** Товари з загальною кількістю продажів

<img width="500" height="237" alt="image" src="https://github.com/user-attachments/assets/166552a3-3407-413b-9c5b-6c07ee7b49da" />

**Результат виконання:**

<img width="1028" height="603" alt="image" src="https://github.com/user-attachments/assets/3cf93bc7-cc28-4486-80a8-e4cb47e8e0ad" />




### Рівень 2

#### 4. Складні з'єднання

**Завдання 4.1:** RIGHT JOIN - аналіз категорій та товарів

<img width="581" height="195" alt="image" src="https://github.com/user-attachments/assets/3d8eae43-4042-419c-9cbe-8176898b87da" />


**Результат виконання:**

<img width="695" height="561" alt="image" src="https://github.com/user-attachments/assets/3b5ee5e7-6f3b-45ba-b847-3b56ee9efec1" />


**Завдання 4.2:** Self-join - співробітники та керівники

<img width="595" height="197" alt="image" src="https://github.com/user-attachments/assets/3081cb7d-9ea2-493d-8ca1-2efc1558a97c" />


**Результат виконання:**

<img width="837" height="420" alt="image" src="https://github.com/user-attachments/assets/b08e49ee-55fa-414a-8df2-6693416a5a91" />




#### 5. Віконні функції

**Завдання 5.1:** Ранжування товарів за ціною в категоріях

<img width="957" height="237" alt="image" src="https://github.com/user-attachments/assets/22981f83-1663-4a06-8e5e-23ebed1fd0ee" />


**Результат виконання:**

<img width="1786" height="592" alt="image" src="https://github.com/user-attachments/assets/0a3cf6ff-4439-42cd-b083-f3093b1cbb85" />


**Завдання 5.2:** Порівняння замовлень з попередніми датами

<img width="981" height="285" alt="image" src="https://github.com/user-attachments/assets/9c33d906-e84e-4ff7-adfb-a1618c507c51" />


**Результат виконання:**

<img width="1022" height="607" alt="image" src="https://github.com/user-attachments/assets/f6ddefc8-d705-4d0e-ab10-113aeefb5a27" />




## Аналіз продуктивності

### Дослідження планів виконання

**Найповільніший запит:**
```sql
SELECT
    o.order_id,
    o.order_date,
    cu.contact_name AS customer_name,
    p.product_name,
    c.category_name,
    s.company_name AS supplier_name,
    oi.quantity,
    oi.unit_price
FROM orders o
JOIN customers cu ON o.customer_id = cu.customer_id
JOIN order_items oi ON o.order_id = oi.order_id
JOIN products p ON oi.product_id = p.product_id
JOIN categories c ON p.category_id = c.category_id
JOIN suppliers s ON p.supplier_id = s.supplier_id
ORDER BY o.order_date DESC, o.order_id;

```

**План виконання (EXPLAIN ANALYZE):**

<img width="955" height="601" alt="image" src="https://github.com/user-attachments/assets/d7b820e7-4a79-421e-b7b0-1fdc6eba5c80" />


**Запропоновані оптимізації:**
1. Додати індекси на зовнішні ключі у таблицях фактів (order_items(order_id), order_items(product_id), orders(customer_id)) для прискорення з'єднань.
2. Обмежувати вибірку фільтром WHERE (наприклад, за датою замовлень або категорією), щоб не обробляти зайві рядки.
3. Додати індекс по orders(order_date DESC) для зменшення витрат на сортування результатів

### Створені індекси

**Індекс 1:**
```sql
CREATE INDEX idx_orders_customer_date ON orders(customer_id, order_date);

```
**Обґрунтування:** прискорює вибірку та сортування замовлень клієнтів за датою (використовується у запитах з JOIN по customer_id, фільтрацією по order_date та віконними функціями LAG/LEAD).

**Індекс 2:**
```sql
CREATE INDEX idx_order_items_product_id ON order_items(product_id);

```
**Обґрунтування:** прискорює агрегацію та пошук позицій замовлень за товаром (зокрема у підзапиті підрахунку продажів для кожного товару).



## Порівняльний аналіз

### Ефективність різних підходів

**Завдання:** Знайти топ-5 найдорожчих товарів у кожній категорії

**Підхід 1: Віконні функції**
```sql
WITH ranked_products AS (
    SELECT
        p.product_name,
        c.category_name,
        p.unit_price,
        DENSE_RANK() OVER (PARTITION BY p.category_id ORDER BY p.unit_price DESC) AS rnk
    FROM products p
    JOIN categories c ON p.category_id = c.category_id
)
SELECT product_name, category_name, unit_price, rnk
FROM ranked_products
WHERE rnk <= 5
ORDER BY category_name, rnk, product_name;

```

**Підхід 2: Корельований підзапит**
```sql
SELECT
    p.product_name,
    c.category_name,
    p.unit_price
FROM products p
JOIN categories c ON p.category_id = c.category_id
WHERE (
    SELECT COUNT(*)
    FROM products p2
    WHERE p2.category_id = p.category_id
      AND p2.unit_price > p.unit_price
) < 5
ORDER BY category_name, p.unit_price DESC;

```

**Час виконання:**
- Віконні функції: <img width="640" height="52" alt="image" src="https://github.com/user-attachments/assets/9151c28b-18cc-40ef-97ee-7d7f3343daac" />

- Корельований підзапит: <img width="441" height="52" alt="image" src="https://github.com/user-attachments/assets/814647a8-72b6-49ca-ac4d-df64ec4ed75a" />


**Висновок:** підхід із віконними функціями зазвичай читабельніший і масштабованіший, оскільки групує дані по категоріях без повторного виконання підзапиту для кожного рядка зовнішньої таблиці. Корельований підзапит на великих обсягах даних може працювати повільніше, якщо немає відповідних індексів по (category_id, unit_price).



## Висновки

**Самооцінка**: 4

**Обгрунтування**: виконано всі обов'язкові завдання Рівня 1 та Рівня 2 (різні типи JOIN, агрегатні функції з GROUP BY та HAVING, підзапити, self-join і віконні функції), додано аналіз планів виконання, створено індекси та виконано порівняння підходів для задачі топ-5 товарів у категорії.
