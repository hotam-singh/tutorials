###  Import data into a MySQL table from a CSV file. 
LOAD DATA LOCAL INFILE '<csv_file_path>' INTO TABLE <table_name> FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' IGNORE 1 ROWS (table_fileds_name_separated_by_comma);

Example: LOAD DATA LOCAL INFILE '/home/hotam/Downloads/MOCK_DATA.csv' INTO TABLE users FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' IGNORE 1 ROWS 
(id, first_name, last_name, email, gender, ip_address);

## DROP vs TRUNCATE vs DELETE
The DROP command removes a table from the database. All the tables' rows, indexes and privileges will also be removed. 
DROP and TRUNCATE are DDL commands, whereas DELETE is a DML command. 
DELETE operations can be rolled back (undone), while DROP and TRUNCATE operations cannot be rolled back.
