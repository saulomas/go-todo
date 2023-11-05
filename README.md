# API todo em Golang e PostgreSQL

## Command

docker run -d --name api-todo -p 5432:5432 -e POSTGRES_PASSWORD=1234 postgres:13.5

docker exec -it api-todo psql -U postgres

create database api_todo;
create user user_todo;
alter user user_todo with encrypted password '1122';
grant all privileges on database api_todo to user_todo;

\l
\c api_todo
\dt

create table todos (id serial primary key, name varchar, description text, done bool);
\dt

grant all privileges on all tables in schema public to user_todo;

drop table todos;
create table todos (id serial primary key, title varchar, description text, done bool default FALSE);

grant all privileges on all tables in schema public to user_todo;
grant all privileges on all sequences in schema public to user_todo;