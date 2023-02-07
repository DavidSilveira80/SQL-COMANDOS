# SQL-COMANDOS
Comandos básicos da linguagem SQL voltados para Mysql

---
## Criando um database

~~~roomsql
CREATE DATABASE empresa; 
~~~
---
## Criando uma table funcionário

~~~roomsql
CREATE TABLE funcionario
(
   id int unsigned not null auto_increment,
   nome varchar(45) not null,
   salario double not null DEFAULT '0',
   departamento varchar(45) not null,
   PRIMARY KEY(id)
);
~~~
---
## Criando table veiculos para relacionar com a table funcionarios

~~~roomsql
CREATE TABLE veiculos
(
    id int unsigned not null auto_increment,
    funcionario_id int unsigned default null,
    veiculo varchar(45) not null DEFAULT '',
    placa varchar(10) not null DEFAULT '',
    PRIMARY KEY(id),
    CONSTRAINT fk_veiculos_funcinarios FOREIGN KEY(funcionario_id) REFERENCES funcionario(id)
);
~~~
---
## Criando a table salarios

~~~roomsql
create table salarios
(
    faixa varchar(45) not null,
    inicio double not null,
    fim double not null,
    PRIMARY KEY(faixa)
);
~~~
---
## Alterando tables

~~~roomsql
ALTER TABLE funcionario CHANGE COLUMN nome nome_func varchar(50) not null;
~~~
---
## Deletando a table salarios

~~~roomsql
DROP TABLE salarios;
~~~
---
## Criando índices

~~~roomsql
CREATE INDEX departamentos ON funcionario(departamento);
~~~

~~~roomsql
CREATE INDEX nomes ON funcionario(nome);
~~~
---

