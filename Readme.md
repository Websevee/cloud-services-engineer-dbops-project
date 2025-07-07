# dbops-project
Исходный репозиторий для выполнения проекта дисциплины "DBOps"

CREATE DATABASE store;

CREATE USER nikolay WITH PASSWORD 'pass';
GRANT CONNECT ON DATABASE store TO nikolay;
GRANT USAGE ON SCHEMA public TO nikolay;
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO nikolay;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO nikolay;
