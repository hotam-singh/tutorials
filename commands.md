# Important Commands

## Linux Commands

### check ubuntu version
`$ lsb_release -a`

### Change password for a user in ubuntu
`$ passwd`

### access to the root directories
```
$ sudo -H /bin/bash 
$ cd /etc/apt
do your editing of files
exit
```
### create a soft link
`$ sudo ln -fs /home/hotam/project/git/QA-automation /etc/automation`

### Check Permissions For A Directory or File in linux
`$ ls -la /root or <any directory here>`

### edit `/etc/environment` directory
`$ sudo -H gedit /etc/environment`

### create hard link in linux
`$ ln {source} {link}`

### Enable wifi
`$ sudo service network-manager restart`

### get wi-fi configuration
`$ iwconfig`

### Get all info and cause of issue in a txt file.
`$ wget -N -t 5 -T 10 https://github.com/UbuntuForums/wireless-info/raw/master/wireless-info && chmod +x wireless-info && ./wireless-info`

### BIOS status for bluetooth and wi-fi
```
$ rfkill list
$ sudo rfkill unblock all
```

### Install cryptkeeper on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install cryptkeeper
```

## GitHub Commands

### Fiest commit on GitHub
```
$ echo "# elasticsearch_with_node" >> README.md
$ git init
$ git add .
$ git add README.md //optional
$ git commit -m "first commit"
$ git remote add origin https://github.com/hotam-singh/<repository_name>.git
$ git push -u origin master
```
### Ignore config.json before commiting.
```
$ git update-index --assume-unchanged <file>

//Example:
$ git update-index --assume-unchanged config.json
```
###  Re-commit config.json before commiting.
```
$ git update-index --no-assume-unchanged <file>

//Example:
$ git update-index --no-assume-unchanged config.json
```
### Check Permissions For A Directory or File in linux
```
ls -la /root
```
## NodeJS Commands

### install node.js in ubuntu
```
$ sudo apt-get update
$ sudo apt-get install nodejs
$ nodejs -v
```

### install npm in ubuntu
```
$ sudo apt-get install npm
$ npm -v
```

### replace nodejs with node
```
$ ln -s /usr/bin/nodejs /usr/bin/node OR sudo ln -s /usr/bin/nodejs /usr/bin/node
$ nodejs -v
$ node -v
```

### upgrade node to the latest version
```
$ sudo npm cache clean -f
$ sudo npm install -g n
$ sudo n stable
$ node -v
```

### Updating node modules inside package.json
```
$ sudo npm install -g npm-check-updates
$ ncu
$ ncu –u
$ npm install
```

### Stop running process
```
$ killall node
$ ps -ef|grep node
```

### To get any application already running on specific port which we are trying to connect to
`$ sudo lsof -i -P -n | grep LISTEN`

### Killing Node Process Running In Backend solution: 1
`$ pkill -f node`

### Killing Node Process Running In Backend solution: 2
```
$ ps aux | grep node
$ kill -9 process_id
```

## NPM Commands

### update npm to latest version 
`$ sudo npm i -g npm`

## MySQL Commands

### Install mysql on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install mysql-server

// Run security script. It will allow you to set default security settings.
$ mysql_secure_installation
```

### connect to mysql database
`$ mysql -u root -p`

### change mysql password if forgot
```
$ sudo /etc/init.d/mysql stop
$ sudo mysqld --skip-grant-tables & mysql -u root mysql
$ UPDATE mysql.user SET Password=PASSWORD('YOURNEWPASSWORD') WHERE User='root'; FLUSH PRIVILEGES; exit;
```

### To verify my mysql installed or not on ubuntu
`$ dpkg --get-selections | grep mysql`

### run mysql on beta server
`$ mysql -hbetadb.websitetoolbox.com -uhotam -p`

### Check version of MYSQL
`$ SELECT VERSION(); after login into mysql shell`

### dump data from database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> > filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test > test.sql
```
### dump data into database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> < filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test < test.sql
```

### create database
`$ create database <database_namee>;`


### drop database
`$ drop database <datanase_name>;`

## PostgresQL Commands

### postgres database commands
```
$ sudo service postgresql restart
$ dropdb ETP_test
$ createdb ETP_test
$ sudo -u postgres psql -d ETP_test -c "alter user "$USER" with password 'password';"
```

### Running postgres database 
```
$ sudo -u postgres psql
$ \list or \l      //List all databases
$ \connect database_name or \c databse_name     //Connect to listed databases
$ \dt     //List Database Tables
```

### Creating dump file of existing data in postgres
`$ pg_dump -U $USER -W -d database_name > ETPDump_file  //-W=password, -d=dump`

### Create dump file of existing database schema in pstgres
`$ pg_dump -U $USER -W -Cs ETP_test > ETPDump  //-W=password -Cs=create schema`

### Back up single table from a database
`$ pg_dump --host localhost --port 5432 -U $USER --format plain --verbose --file "file_name_here" --table public.<table_name_here> <database_name_here>`

### Check version of PostgreSQL
`SELECT VERSION(); after login into postgres shell`

### dump data into database
```
$ psql <database_name> < filename
Example:
$ psql dump < psqldump
```

### dump data from database
```
$ pg_dump <database_name> > filename
Example:
$ pg_dump puppies > psqldump
```

## MongoDB Commands
 	
### check mongodb version
In mongo shell:

`db.version()`

### dump data to mongodb
`$ mongoimport -d <database name> -c <collection name> --type <file type> <path to a file> --headerline`

### dump database from mongodb
`$ mongoexport --db <datanase_name> --collection <collection_name> --out filename.json/filename.csv`

## Elasticsearch Commands

### Elastic Search server Configuration on production server
```
//After installation process, run below command to give permissions to elasticsearch directory
$ sudo chown -R elasticsearch:elasticsearch /var/lib/elasticsearch/
```

### Edit configuration of elasticsearch
```
//etc/elasticsearch/elasticsearch.yml file
$ sudo nano /etc/elasticsearch/elasticsearch.yml
```

### Restart elastic search server when any modification is made in /etc/elasticsearrch/elasticsearch.yml
```
$ sudo service elasticsearch restart
$ sudo /etc/init.d/elasticsearch start
```

### Get the status of elasticsearch server status
```
$ sudo service elasticsearch status 
// OR 
$ curl -X GET 'http://<server_ip_address>:9200'
```