# PostgresQL: Part 1

## What is PostgresQL?

PostgresQL is an open source ORDBMS(Object Relational Database Management System). It was developed at Barkeley Computer Science Department, California(University of California). 
Postgres is available under PostgresQL license and free to use. You are free to use, modify and distribute PostgreSQL in any form.

## PostgreSQL features highlights

1. User-defined types
2. Table inheritance
3. Sophisticated locking mechanism
4. Foreign key referential integrity
5. Views, rules, subquery
6. Nested transactions (savepoints)
7. Multi-version concurrency control (MVCC)
8. Asynchronous replication

## What makes PostgreSQL stand out


* PostgreSQL is the first database management system that implements multi-version concurrency control (MVCC) feature, even before Oracle. The MVCC feature is known as snapshot isolation in Oracle.
* You can define your own data types, index types, functional languages, etc.
* Adding a new optimizer(Custoom Plugin).
* If you need any support, an active community is available to help.

## Who is using PostgreSQL

Many companies have built products and solutions using PostgreSQL. Some featured companies are Apple, Fujitsu, Red Hat, Cisco, Juniper Network, etc.

## Connect to database

$ sudo -su postgres psql 

## Check Postgres installed or not

### View server version

-----------------------------------------------------
$ SHOW server_version;
-----------------------------------------------------

OR

To find the Postgres server version from the shell command line, simply issue a postgres command with the -V flag (for version):

$ postgres -V
postgres (PostgreSQL) 9.3.10

In the event that the postgres command is not found, you may need to locate the directory of the utility. This can be done by issuing the locate bin/postgres command:

$ locate bin/postgres
/usr/lib/postgresql/9.3/bin/postgres

Now with the direct path to the postgres utility, you can call it with the -V flag as illustrated above:

$ /usr/lib/postgresql/9.3/bin/postgres -V
postgres (PostgreSQL) 9.3.10

### Check client version

----------------------------------------------------
$ SELECT VERSION(); from the postgres-server shell.
----------------------------------------------------

OR 

To view the client version, again simply pass the -V flag to the psql client utility command:

----------------------------------------------------
$ psql -V
psql (PostgreSQL) 9.3.10
----------------------------------------------------

Similar to the above, if you cannot find the utility – or have multiple installations of PostgreSQL on that machine – you can easily locate psql:

----------------------------------------------------
$ locate bin/psql
/usr/bin/psql
/usr/lib/postgresql/9.3/bin/psql
----------------------------------------------------

Then issue a direct call to the located psql utility for the version:

----------------------------------------------------
$ /usr/lib/postgresql/9.3/bin/psql -V
psql (PostgreSQL) 9.3.10
----------------------------------------------------

## Run pgAdmin 4
cd ~/pgadmin4 && source bin/activate && python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py


## Aletr a user instead of postgres
sudo -u postgres psql -d <database-name-here> -c "alter user "$USER" with password '<user-passsword>';"






# PostgresQl: Part 2 - Queries Samples
* SELECT d."username", t."t_senderId", ENCODE(t."t_senderPublicKey", 'hex'), t."t_timestamp" from trs_list t INNER JOIN delegates d ON t."t_id" = d."transactionId" WHERE t."t_type" = 2 ORDER BY "t_timestamp" DESC LIMIT 5

* SELECT b."b_confirmations" FROM trs t LEFT OUTER JOIN blocks_list AS b ON t."blockId" = b."b_id" WHERE t."senderId" = 'DDK4995063339468361088' ORDER BY t."timestamp" DESC LIMIT 1

* SELECT * FROM trs t LEFT OUTER JOIN blocks_list AS b ON t."blockId" = b."b_id" WHERE t."senderId" = 'DDK4995063339468361088' ORDER BY t."timestamp" DESC LIMIT 1

* SELECT id from trs WHERE "senderId" = 'DDK4995063339468361088' ORDER BY "timestamp" DESC LIMIT 1

* SELECT date_part('day', to_timestamp(1451667600 + 82150336));

* SELECT * FROM generate_series(2,9,5);

* SELECT * FROM generate_series(to_timestamp(1451667600 + 82150336), CURRENT_TIMESTAMP, '1 day');

* SELECT CURRENT_TIMESTAMP;

* SELECT CURRENT_TIME;

* SELECT LOCALTIMESTAMP;

* SELECT now();

* SELECT timeofday();

* SELECT clock_timestamp();

* SELECT transaction_timestamp();

* SELECT make_interval(days => 1);

* SELECT to_timestamp(1533557527); /*result: "2018-08-06 17:42:07+05:30"*/

* SELECT EXTRACT(EPOCH FROM timestamptz '2018-08-06 05:53:00') -
       EXTRACT(EPOCH FROM timestamptz '2016-03-01 12:00:00'); /*result: 76701180*/

* SELECT timestamptz '2013-07-01 12:00:00' - timestamptz '2013-03-01 12:00:00'; /*result: 122 days*/

* SELECT * FROM trs;

* SELECT * from trs where DATE(1533557527) >= CURRENT_DATE AND DATE(1533557527) < CURRENT_DATE + INTERVAL '1 DAY';

* SELECT EXTRACT(second from "2018-08-06T12:12:07+00:00") AS second FROM trs;

* SELECT sum("id") OVER (ORDER BY "timestamp") AS running_ct
	FROM  (
   	SELECT date_trunc('minute', "when") AS "timestamp"
        , count(*) AS minute_ct
   FROM   trs
   GROUP  BY 1
   ) sub
	ORDER  BY 1;
	
* SELECT to_timestamp(81534553, 'YYYY-MM-DD hh24:mi:ss')::timestamp FROM trs;

* UPDATE mem_accounts SET "username" = 'DSTAKEREWARD', "u_username" = 'DSTAKEREWARD' WHERE "address" = 'DDK4995063339468361088';

* UPDATE mem_accounts SET "username" = 'DPENDINGGB', "u_username" = 'DPENDINGGB' WHERE "address" = 'DDK15546849747111093123';

* UPDATE mem_accounts SET "username" = 'DCONTRIBUTOR', "u_username" = 'DCONTRIBUTOR' WHERE "address" = 'DDK5143663806878841341';

* UPDATE mem_accounts SET "username" = 'DADVISOR', "u_username" = 'DADVISOR' WHERE "address" = 'DDK14224602569244644359';

* UPDATE mem_accounts SET "username" = 'DTEAM', "u_username" = 'DTEAM' WHERE "address" = 'DDK9758601670400927807';

* UPDATE mem_accounts SET "username" = 'DFOUNDER', "u_username" = 'DFOUNDER' WHERE "address" = 'DDK12671171770945235882';

* UPDATE mem_accounts SET "username" = 'DAIRDROP', "u_username" = 'DAIRDROP' WHERE "address" = 'DDK10720340277000928808';

* UPDATE mem_accounts SET "username" = 'DRESERVEDEX', "u_username" = 'DRESERVEDEX' WHERE "address" = 'DDK5216737955302030643';

* UPDATE mem_accounts SET "username" = 'DDKFOUNDATION', "u_username" = 'DDKFOUNDATION' WHERE "address" = 'DDK8999840344646463126';

* SELECT * FROM blocks b LEFT JOIN mem_accounts m ON b."generatorPublicKey" = m."publicKey";

* UPDATE mem_accounts SET "username" = 'DSTAKEREWARD', "u_username" = 'DSTAKEREWARD' WHERE "address" = 'DDK4995063339468361088';

* SELECT address FROM referals WHERE level[1] = 'DDK17471048754315917391';

* SELECT * FROM stake_orders WHERE "senderId" = 'DDK250215393355075043';

* SELECT "startTime" FROM stake_orders where "senderId" = 'DDK250215393355075043' ORDER BY "startTime" DESC LIMIT 1;

* SELECT SUM("freezedAmount") FROM stake_orders WHERE "senderId" = 'DDK250215393355075043' AND "status" = 1

* (SELECT "startTime" FROM stake_orders where "senderId" = 'DDK250215393355075043' ORDER BY "startTime" DESC LIMIT 1) 
	UNION ALL 
	
	(SELECT SUM("freezedAmount") FROM stake_orders WHERE "senderId" = 'DDK250215393355075043' AND "status" = 1);
	
* SELECT address FROM referals WHERE level[1] = 'DDK3719160100826468721';

* alter table mem_accounts drop column virgin;



# PostgresQL: Part 3 - Errors
## 1. could not connect to server: Connection refused Is the server running on host "localhost" (127.0.0.1) and accepting TCP/IP connections on port 5432?

**Solution** 
```
1. edit postgresql.conf
$ vim /etc/postgres/9.6/main/postgres.conf

2. change below options
listen_addresses = '*'
port = 5432

3. save and close this file
4. restart the server
sudo service postgresql restart
```

