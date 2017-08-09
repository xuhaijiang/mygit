### FULL TEXT

全文索引在 MySQL 中是一个 全文索引在 MySQL 中是一个 FULLTEXT 类型索引

### 创建

1. CREATE TABLE 
2. ALTER TABLE 或 CREATE INDEX 在 CHAR、VARCHAR 或 TEXT 列上创建

> 将数据装载到一个已经有 FULLTEXT 索引的表中，将是非常慢的

### 例子

	CREATE TABLE articles (
    	id INT UNSIGNED AUTO_INCREMENT NOT NULL PRIMARY KEY,
    	title VARCHAR(200),
    	body TEXT,
    	FULLTEXT (title,body)
    );

	INSERT INTO articles VALUES
    (NULL,'MySQL Tutorial', 'DBMS stands for DataBase ...'),
    (NULL,'How To Use MySQL Efficiently', 'After you went through a ...'),
    (NULL,'Optimising MySQL','In this tutorial we will show ...'),
    (NULL,'1001 MySQL Tricks','1. Never run mysqld as root. 2. ...'),
    (NULL,'MySQL vs. YourSQL', 'In the following database comparison ...'),
    (NULL,'MySQL Security', 'When configured properly, MySQL ...');


 `SELECT * FROM articles WHERE MATCH (title,body) AGAINST ('database')`

| id | title | body |
|---|:---|:---:|
| 5 |MySql vs. YourSQL |In the following **database** comparison ...|
| 1 |MySQL Tutorial |DBMS stands for **DataBase** ...|