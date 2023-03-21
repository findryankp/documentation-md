# MySql On Your VM
**Development by:** 
- Findryankp

## Tutorial
1. docker login SERVER_HERE
2. docker pull mysql/mysql-server
3. docker run -p 3306:3306 -d --name [docker-name] -e MYSQL_ROOT_PASSWORD=[password] -e MYSQL_PASSWORD=[password] -e MYSQL_USER=[username] mysql/mysql-server
4. mysql -uroot -ppassword
5. CREATE USER 'findryankp'@'%' IDENTIFIED BY 'passwordfindryan';
6. GRANT ALL PRIVILEGES ON * . * TO 'findryankp'@'%';
7. quit

* EXAMPLE :
docker run -p 3306:3306 -d --name docker-mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_PASSWORD=root -e MYSQL_USER=root mysql/mysql-server

mysql -u[root] -p[root]


# Akses Server
mysql -h host -P 3306 -u root -p