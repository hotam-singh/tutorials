# Important Commands

## VIM editor commands

### search in editor
/<search-pattern>
Example: /web3

and press n for next occurrence 

### Find each occurrence of 'foo' (in all lines), and replace it with 'bar'.
:%s/<search-pattern>/<replaced-with-pattern>
Example: :%s/foo/bar/g
 
### Go to line number
:<line-number>
Example: :420

## Linux Commands

### generate pem file for linux server
ssh-keygen -t rsa -b 2048 -f FILENAME

### Copy a repository from local to a remote server
scp -ri <pem-file> source <user>@<ip>:<destination>
scp -ri hotam.pem digibyte-7.17.2/ ubuntu@54.254.164.23:backup
	
### Copy a file from local to remote server
scp -i <pem-file> source <user>@<IP>:<destination>
scp -i hotam.pem digibyte-7.17.2/ ubuntu@54.254.164.23:backup

### Get public IP
curl ipinfo.io/ip

### copy file from one user to another
sudo cp /home/hotam/ETP/test/ETP-Linux-x86_64.tar.gz /home/etp/ETP-Linux-x86_64.tar.gz && sudo chown etp:etp /home/etp/ETP-Linux-x86_64.tar.gz

sudo cp /home/hotam/ETP/test/etp-Linux-x86_64.tar.gz /home/etp/backup/etp-Linux-x86_64.tar.gz && sudo chown etp:etp /home/etp/backup/etp-Linux-x86_64.tar.gz

cp backup/etp-Linux-x86_64.tar.gz ./

### Grep some pattern
grep -irl <pattern>
Example: grep -irl web3/src

### Create a zip of a folder
find /full_path -path '*/.*' -prune -o -type f -print | zip ~/file.zip -@    //includes hidden files
example: find /home/hotam/altcoin-exchange -path '*/.*' -prune -o -type f -print | zip ~/altcoin-exchange.zip -@

### Upload a zip file to remote server
scp  <source>  <user>@<host>:<path
Example: scp  altcoin-exchange.zip  root@68.183.92.226:new-core
								  
### Unzip a zipped file
unzip <zip-file-name>
Example: unzip altcoin-exchange.zip

### 1. check ubuntu version
`$ lsb_release -a`

### 2. Change password for a user in ubuntu
`$ passwd`

### 3. access to the root directories
```
$ sudo -H /bin/bash 
$ cd /etc/apt
do your editing of files
exit
```
### 4. create a soft link
`$ sudo ln -fs /home/hotam/project/git/QA-automation /etc/automation`

### 5. Check Permissions For A Directory or File in linux
`$ ls -la /root or <any directory here>`

### 6. edit `/etc/environment` directory
`$ sudo -H gedit /etc/environment`

### 7. create hard link in linux
`$ ln {source} {link}`

### 8. Enable wifi
`$ sudo service network-manager restart`

### 9. get wi-fi configuration
`$ iwconfig`

### 10. Get all info and cause of issue in a txt file.
`$ wget -N -t 5 -T 10 https://github.com/UbuntuForums/wireless-info/raw/master/wireless-info && chmod +x wireless-info && ./wireless-info`

### 11. BIOS status for bluetooth and wi-fi
```
$ rfkill list
$ sudo rfkill unblock all
```

### 12. Install cryptkeeper on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install cryptkeeper
```

### 13. Check all running process
```
sudo netstat -tunlp
```

### 14. Check current user
```
whoami
```

## GitHub Commands

### 1. First commit on GitHub
```
$ echo "# elasticsearch_with_node" >> README.md
$ git init
$ git add .
$ git add README.md //optional
$ git commit -m "first commit"
$ git remote add origin https://github.com/hotam-singh/<repository_name>.git
$ git push -u origin master
```
### 2. Ignore config.json before commiting.
```
$ git update-index --assume-unchanged <file>

//Example:
$ git update-index --assume-unchanged config.json
```
###  3. Re-commit config.json before commiting.
```
$ git update-index --no-assume-unchanged <file>

//Example:
$ git update-index --no-assume-unchanged config.json
```
### 4. Check Permissions For A Directory or File in linux
```
ls -la /root
```

### 5. Mirror a GitHub repository from one to another
```
// clone from
git clone --mirror https://github.com/<github-user>/<repository-name> 

// clone to
$ cd <repository-name>.git>
git push --mirror https://github.com/<github-user>/<repository-name>.git> 

Example:

// clone from
git clone --mirror https://github.com/oodlestechnologies/DDKCoin

// clone to
cd DDKCoin.git
git push --mirror https://github.com/ddkoin/DDKCore.git

OR

git push --mirror https://github.com/ddkoin/DDKCore
```

### 6. generate new ssh key for github

#### Generate SSH Key
```
ssh-keygen -t rsa
```

#### Get SSH Key
```
xclip -sel clip < ~/.ssh/id_rsa.pub
OR
cat ~/.ssh/id_rsa.pub
```

### 7. How can I determine the URL that a local Git repository was originally cloned from?
git config --get remote.origin.url

## NodeJS Commands

### 1. Install node.js in ubuntu
```
$ sudo apt-get update
$ sudo apt-get install nodejs
$ nodejs -v
```

### 2. Install npm in ubuntu
```
$ sudo apt-get install npm
$ npm -v
```

### 3. Replace nodejs with node
```
$ ln -s /usr/bin/nodejs /usr/bin/node OR sudo ln -s /usr/bin/nodejs /usr/bin/node
$ nodejs -v
$ node -v
```

### 4. Upgrade node to the latest version
```
$ sudo npm cache clean -f
$ sudo npm install -g n
$ sudo n stable
$ node -v
```

### 5. Updating node modules inside package.json
```
$ sudo npm install -g npm-check-updates
$ ncu
$ ncu –u
$ npm install
```

### 6. Stop running process
```
$ killall node
$ ps -ef|grep node
```

### 7. To get any application already running on specific port which we are trying to connect to
`$ sudo lsof -i -P -n | grep LISTEN`

### 8. Killing Node Process Running In Backend solution: 1
`$ pkill -f node`

### 9. Killing Node Process Running In Backend solution: 2
```
$ ps aux | grep node
$ kill -9 process_id
```

### 10. Run NodeJS app with different dev modes

#### Running from CLI
```
NODE_ENV=<development_mode> node/nodemon <file_name>

Example:
NODE_ENV=development node app.js
```

#### Running with PM2
```
pm2 start/restart <pm2_config> --env <development_mode> --update-env

Example:
pm2 start ecosystem.config.js --env development/production/testnet/mainet --update-env
```

### 11. Uninstall NodeJS
#### Remove NodeJS and its configuration files
```
$ sudo apt-get purge nodejs
```

#### Remove unused packages
```
$ sudo apt purge appstream
$ sudo apt-get autoremove
```

#### Cleanup
```
$ sudo rm -rf /usr/local/bin/npm /usr/local/share/man/man1/node* /usr/local/lib/dtrace/node.d ~/.npm ~/.node-gyp /opt/local/bin/node opt/local/include/node /opt/local/lib/node_modules
$ sudo rm -rf /usr/local/lib/node*
$ sudo rm -rf /usr/local/include/node*
$ sudo rm -rf /usr/local/bin/node*
```

### 12. Auto generate .gitignore and add node_mosules to it
echo node_modules/ >> .gitignore

### 13. npm install error
sudo apt-get install build-essential
sudo apt-get install autoconf automake g++ libtool

## NPM Commands

### 1. update npm to latest version 
`$ sudo npm i -g npm`

### 2. update all dependencies
```
npm audit
npm dedupe
```

### 3. check npm module version
```
npm show <module-name> version

Example:
npm show express version
```

### 4. List a module in node_modules
```
npm list | grep <module-name>

Example:
npm list | grep body-parser
```

## MySQL Commands

### 1. Install mysql on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install mysql-server

// Run security script. It will allow you to set default security settings.
$ mysql_secure_installation
```

### 2. connect to mysql database
`$ mysql -u root -p`

### 3. change mysql password if forgot
```
$ sudo /etc/init.d/mysql stop
$ sudo mysqld --skip-grant-tables & mysql -u root mysql
$ UPDATE mysql.user SET Password=PASSWORD('YOURNEWPASSWORD') WHERE User='root'; FLUSH PRIVILEGES; exit;
```

### 4. To verify my mysql installed or not on ubuntu
`$ dpkg --get-selections | grep mysql`

### 5. run mysql on beta server
`$ mysql -hbetadb.websitetoolbox.com -uhotam -p`

### 6. Check version of MYSQL
`$ SELECT VERSION(); after login into mysql shell`

### 7. dump data from database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> > filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test > test.sql
```
### 8. dump data into database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> < filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test < test.sql
```

### 9. create database
`$ create database <database_namee>;`


### 10. drop database
`$ drop database <datanase_name>;`

## PostgresQL Commands

### 1. postgres database commands
```
$ sudo service postgresql restart
$ dropdb ETP_test
$ createdb ETP_test
$ sudo -u postgres psql -d ETP_test -c "alter user "$USER" with password 'password';"
```

### 2. Running postgres database 
```
$ sudo -u postgres psql
$ \list or \l      //List all databases
$ \connect database_name or \c databse_name     //Connect to listed databases
$ \dt     //List Database Tables
```

### 3. Creating dump file of existing data in postgres
`$ pg_dump -U $USER -W -d database_name > ETPDump_file  //-W=password, -d=dump`

### 4. Create dump file of existing database schema in pstgres
`$ pg_dump -U $USER -W -Cs ETP_test > ETPDump  //-W=password -Cs=create schema`

### 5. Back up single table from a database
`$ pg_dump --host localhost --port 5432 -U $USER --format plain --verbose --file "file_name_here" --table public.<table_name_here> <database_name_here>`

### 6. Check version of PostgreSQL
`SELECT VERSION(); after login into postgres shell`

### 7. dump data into database
```
$ psql <database_name> < filename
Example:
$ psql dump < psqldump
```

### 8. dump data from database
```
pg_dump -d <database-name> -f <filename> 

Example:
pg_dump -d DDK_test -f latest.db.gz

// Alternate way 
$ pg_dump <database_name> > filename
Example:
$ pg_dump puppies > psqldump
```

### 9. Import .zip pg_dump into database
```
gunzip -fcq blockchain.db.gz | psql -d <database-name>
```

### 10. Check if a database exists or not in postgres
```
psql template1 -U <user> -c "SELECT 1 AS result FROM pg_database WHERE datname='<database-name>'";

Example: 
psql template -U $USER -c "SELECT 1 AS result FROM pg_database WHERE datname='DDK_test'";
```

### 11. Restart the server
```
$ sudo service postgresql restart
```

### 12. Connect to database
```
sudo -su postgres psql
```

### 13. Uninstall PostgresQL
#### Stop the running postgreSQL instance
```
/etc/init.d/postgresql stop
```

#### Remove postgres and its related config files
```
sudo apt-get --purge remove postgresql\*
```

#### Cleanup
```
rm -r /etc/postgresql/
rm -r /etc/postgresql-common/
rm -r /var/lib/postgresql/
userdel -r postgres
groupdel postgres
```

### 14. Run pgAdmin 4
cd ~/pgadmin4 && source bin/activate && python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py

## MongoDB Commands
 	
### 1. check mongodb version
In mongo shell:

`db.version()`

### 2. dump data to mongodb
`$ mongoimport -d <database name> -c <collection name> --type <file type> <path to a file> --headerline`

### 3. dump database from mongodb
`$ mongoexport --db <datanase_name> --collection <collection_name> --out filename.json/filename.csv`

## Elasticsearch Commands

### 1. Elastic Search server Configuration on production server
```
//After installation process, run below command to give permissions to elasticsearch directory
$ sudo chown -R elasticsearch:elasticsearch /var/lib/elasticsearch/
```

### 2. Edit configuration of elasticsearch
```
//etc/elasticsearch/elasticsearch.yml file
$ sudo nano /etc/elasticsearch/elasticsearch.yml
```

### 3. Restart elastic search server when any modification is made in /etc/elasticsearrch/elasticsearch.yml
```
$ sudo service elasticsearch restart
$ sudo /etc/init.d/elasticsearch start
```

### 4. Get the status of elasticsearch server status
```
$ sudo service elasticsearch status 
// OR 
$ curl -X GET 'http://<server_ip_address>:9200'
```

### 5. Change cluster health color YELLOW to GREEN
```
curl -XPUT 'http://localhost:9200/_settings' -H "Content-Type: application/json"  -d '{    "index" : {        "number_of_replicas" : 0    }}'
```

### 6. Check elastic search health
```
curl -X GET "localhost:9200/_cluster/health/twitter?level=shards"
```

### 7. Flush elasticsearch
```
curl -XDELETE <ip_address or host>:9200/*

Example:
curl -XDELETE localhost:9200/*
```

## Redis Commnads

### 1. Connect to Redis
```
// On local
$ redis-cli

// On a server
$ redis-cli -h <host> -p <port>

Example:
$ redis-cli -h 159.65.139.248 -p 6380 // default port 6379
```
### 2. Flush all keys
```
$ flushall
```

## Kafka Commands

### 1. Start Zookeeper 
```
bin/zookeeper-server-start.sh config/zookeeper.properties
```

### 2. Start Kafka
```
bin/kafka-server-start.sh config/server.properties
```

### 3. Create a Topic
```
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic <topic_name>

Examples:
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic queuedTransactions
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic bundeledTransactions
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic multisignatureTransaction
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic unconfirmedTransaction
```

### 4. Delete a Topic
```
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic <topic_name>

Example:
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic queuedTransactions
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic bundeledTransactions
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic multisignatureTransaction
bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic unconfirmedTransaction
```
