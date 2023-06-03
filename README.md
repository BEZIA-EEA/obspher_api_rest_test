# obspher_api_rest_test
 serveur web RESTful en C++

 # Build
 ```
 mkdir build
 cd buid
 cmake ..
 make
```
# run
```
./server
```
# Mysql database creation 
```
CREATE DATABASE IF NOT EXISTS obs_rest;

USE obs_rest;

CREATE TABLE IF NOT EXISTS Users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255),
    email VARCHAR(255),
    password VARCHAR(255)
);

CREATE TABLE IF NOT EXISTS Projects (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255),
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES Users(id)
);
```

