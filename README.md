# CRUD_Flask_PostgreSQL
1. Activate PostgreSQL server:

$ cd C:\Program Files\PostgreSQL\10\bin
$ psql -U postgres
  Password for user postgres: <insert password here>
2. Create a database on PostgreSQL, my database name is "lin_flask":

postgres=#  CREATE DATABASE lin_flask;
postgres=#  \l 
postgres=#  \c lin_flask

3.Create a "users" table on "lin_flask" database:

lin_flask=#  CREATE TABLE users(
             id SERIAL PRIMARY KEY,
             name VARCHAR(255),
             age VARCAR(255)
             );
lin_flask=#  \d

4. Clone this repo. Insert your database URI to database.yaml file, then install all the packages needed. In this project I'm using flask, flask_cors, flask_mysqldb, Flask-SQLAlchemy & psycopg2:
$ git clone https://github.com/LintangWisesa/CRUD_Flask_PostgreSQL.git
$ cd CRUD_Flask_PostgreSQL
$ pip install flask flask_cors Flask-SQLAlchemy psycopg2

5. Run the server file. Make sure your PostgreSQL server is still running. Your application server will run locally at http://localhost:5000/ :
$ python app.py

6. Give a request to the server. You can use Postman app:

See the opening screen (home.html)

GET /
Post a data to database:

POST /data
body request: {name:"x", age:"y"}
Get all data & specific data by id:

GET /data
GET /data/{:id}
Update a data by id:

PUT /data/{:id}
body request: {name:"x", age:"y"}
Delete a data by id:

DELETE /data/{:id}
