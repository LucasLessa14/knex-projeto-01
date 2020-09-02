# knex-projeto-01

### Exercício da Formação NodeJS do Guia do Programador na Udemy

## Database

Use esse script para criar seu database em um container docker

```
docker run -e MYSQL_ROOT_PASSWORD=docker -e MYSQL_USER=docker -e MYSQL_PASSWORD=docker -p 3306:3306 -d mysql:8

docker run -e POSTGRES_PASSWORD=docker -e POSTGRES_USER=docker -p 5432:5432 -d postgres:12
```

Use esse script para criar as tabelas no seu database

``` sql
CREATE TABLE users(
  id serial NOT NULL,
  name text NOT NULL,
  email text NOT NULL,
  password text NOT NULL,
  role int NOT NULL,
  PRIMARY KEY (id)
);

CREATE TABLE passwordtokens(
  id serial NOT NULL,
  token text NOT NULL,
  user_id int NOT NULL,
  used int NOT NULL,
  PRIMARY KEY (id),
  FOREIGN KEY (user_id) REFERENCES users (id)
);
```