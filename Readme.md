## Создание БД
```sql
CREATE DATABASE store;
```

## Создание пользователя для миграций `migrations_user`
```sql
CREATE USER migrations_user WITH PASSWORD 'pass';
```

## Добавление привилегий пользователю `migrations_user`
Необходимо переключиться на БД `store` для выполнения следующих запросов:
```sql
GRANT ALL PRIVILEGES ON SCHEMA public TO migrations_user;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO migrations_user;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON TABLES TO migrations_user;
```


## SQL-запрос, который показывает, какое количество сосисок было продано за предыдущую неделю.
```sql
SELECT o.date_created, SUM(op.quantity)
FROM orders AS o
JOIN order_product AS op ON o.id = op.order_id
WHERE o.status = 'shipped' AND o.date_created > NOW() - INTERVAL '7 DAY'
GROUP BY o.date_created; 
```