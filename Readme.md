# dbops-project
Исходный репозиторий для выполнения проекта дисциплины "DBOps"

```sql
CREATE DATABASE store;

CREATE USER migrations_user WITH PASSWORD 'pass';
GRANT CONNECT ON DATABASE store TO migrations_user;
GRANT USAGE ON SCHEMA public TO migrations_user;
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO migrations_user;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO migrations_user;