- `mysql -u root -p`
- CREATE DATABASE ptn CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
- `CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;`
- `CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'password';`
- `GRANT ALL ON wordpress.* TO 'wordpressuser'@'localhost';`
- `FLUSH PRIVILEGES;`
- `EXIT;`
- ```
  ALTER DATABASE
      database_name
      CHARACTER SET = utf8mb4
      COLLATE = utf8mb4_unicode_ci;
  ```
- ```
  ALTER TABLE
      table_name
      CONVERT TO CHARACTER SET utf8mb4
      COLLATE utf8mb4_unicode_ci;
  ```
- ```
  ALTER TABLE
      table_name
      CHANGE column_name column_name
      VARCHAR(191)
      CHARACTER SET utf8mb4
      COLLATE utf8mb4_unicode_ci;
  ```
-