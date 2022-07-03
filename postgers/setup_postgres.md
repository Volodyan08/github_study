# Setup PostgreSQL

Create user PostgreSQL

    $ create user your_user_name with password 'your_password'; 

Create DB
    
    $ create database "dbname";

Grand privileges to a new user
    
    $ grant all privileges on database dbname to your_user_name;

Switch connection to a new DB

    $ \c dbname

Enable PostGIS (as of 3.0 contains just geometry/geography)

    $ CREATE EXTENSION postgis;