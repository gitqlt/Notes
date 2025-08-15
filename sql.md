sql: Structured Query Language
====

#### Database tables, dbsize, tables w. size,recordnum
    sql> use <dbname>
    sql> show tables;  
    mysql> SELECT table_schema AS database_name, ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) AS total_mb FROM information_schema.tables WHERE table_schema = 'dbname' GROUP BY table_schema;
    mysql> SELECT table_name, table_rows AS record_count, ROUND((data_length + index_length) / 1024 / 1024, 2) AS total_mb FROM information_schema.tables WHERE table_schema = 'dbname' ORDER BY total_mb DESC;

#### table record number, size
    sql> select count(*) from <tablename>;
    mysql> select table_name,table_rows FROM information_schema.tables WHERE table_schema = 'dbname' and table_name = 'tablename';

#### table info
    sql> DESCRIBE <tablename>;
    sql> SHOW COLUMNS FROM <tablename>;
    mysql> SHOW CREATE TABLE <tablename>;
