# Docker and Flask_DB Project
This Simple Project will help you deploy a flask application with MYSQL database.

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
What things you need to install the software and how to install them.
```
Flask
mysql-connector
docker-compose
```

### Installing
A step by step series of examples that tell you how to get a development env running
As in the app dir the requirements.txt file is given.

Now after installing the docker-compose
Run the following commands.

```
$ docker-compose up
```
You can see the image being built, the packages installed according to the requirements.txt, etc. If everything went right, you will see the following line:

```
app_1  |  * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
```

We can find out that everything is running as expected by typing this url in a browser or using curl, and receiving the following response:
```
$ curl http://0.0.0.0:5000/
{"favorite_colors": [{"Lancelot": "blue"}, {"Galahad": "yellow"}]}
```

You can access the database directly using the mysql client and following command (make sure your client is the same version of MySQL specified in the docker-compose.yml):

Before that install the following dependencies for Unix:
```
sudo apt install mysql-client-core-5.7   
sudo apt install mariadb-client-core-10.1
```
Then,
```
$ mysql --host=127.0.0.1 --port=32000 -u root -p
```
Below are the basic SQL commands.
```
MySQL [(none)]> show databases ;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| knights            |
| mysql              |
| performance_schema |
| sys                |
+--------------------+

MySQL [(none)]> use knights;
MySQL [knights]> show tables;
+-------------------+
| Tables_in_knights |
+-------------------+
| favorite_colors   |
+-------------------+
MySQL [knights]> SELECT * FROM favorite_colors;
+----------+--------+
| name     | color  |
+----------+--------+
| Lancelot | blue   |
| Galahad  | yellow |
+----------+--------+
```
