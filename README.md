# Projeto de Banco de Dados: Vendas de Carros

Este projeto utiliza o **MySQL** para criar e gerenciar um banco de dados relacionado à venda de carros. O banco de dados armazena informações sobre veículos e clientes, permitindo manipulação de dados como inserções, exclusões e consultas.

## Estrutura do Banco de Dados

### 1. Criação do Banco de Dados
O banco de dados `vendas_de_carros` foi criado para armazenar informações sobre carros e clientes.

```sql
CREATE DATABASE vendas_de_carros;
USE vendas_de_carros;
```

<h2>2. Tabelas Criadas</h2>

<p><b>Tabela:</b> <code>carros</code></p>
<p>Armazena os dados dos veículos disponíveis para venda.</p>

<p><b>• Colunas:</b></p>

<p><code>• codigo:</code> Identificador único para o carro (chave primária).</p>
<p><code>• modelo:</code> Modelo do carro.</p>
<p><code>• ano: </code>Ano de fabricação.</p>
<p><code>• preço: </code>Preço do carro.</p>

<h2>Script de Criação:</h2>

```
CREATE TABLE carros (
    codigo INT UNSIGNED NOT NULL AUTO_INCREMENT,
    modelo VARCHAR(20) NOT NULL,
    ano INT NOT NULL,
    preço DOUBLE NOT NULL,
    PRIMARY KEY (codigo)
);
```

<h2>Dados Inseridos:</h2>

```
INSERT INTO carros(codigo, modelo, ano, preço) VALUES (111, 'Saveiro', 2015, 40000);
INSERT INTO carros(codigo, modelo, ano, preço) VALUES (222, 'Golf', 2012, 35000);
INSERT INTO carros(codigo, modelo, ano, preço) VALUES (333, 'Gol', 2020, 100000);
INSERT INTO carros(codigo, modelo, ano, preço) VALUES (444, 'S10', 2019, 230000);
INSERT INTO carros(codigo, modelo, ano, preço) VALUES (555, 'Hilux', 2022, 400000);

```

<h2>Exclusão de Registro:</h2>

```
DELETE FROM carros WHERE codigo = 555;
```



<p><b></b> <code></code></p>
Tabela: clientes

<p></p>
Armazena os dados dos clientes.

<p><b></b></p>
• Colunas:

<p><code>• nome:</code> Nome completo do cliente.</p>
<p><code>• cpf:</code> CPF do cliente.</p>

<p><code>• estado:</code>  Estado de residência (sigla).</p>
<p><code>• codigo:</code>  Identificador único para o cliente (chave primária).</p>
 
<h2>Script de Criação:</h2>

```
CREATE TABLE clientes (
    nome VARCHAR(45) NOT NULL,
    cpf VARCHAR(14) NOT NULL,
    estado VARCHAR(2) NOT NULL,
    codigo INT UNSIGNED NOT NULL AUTO_INCREMENT,
    PRIMARY KEY (codigo)
);
```

<h2>Dados Inseridos:</h2>

```
INSERT INTO clientes(nome, cpf, codigo, estado) VALUES ('Alexandre', '111.111.111-11', 222, 'PE');
INSERT INTO clientes(nome, cpf, codigo, estado) VALUES ('João', '222.222.222-22', 111, 'SP');
INSERT INTO clientes(nome, cpf, codigo, estado) VALUES ('Lucas', '333.333.333-33', 444, 'RJ');
INSERT INTO clientes(nome, cpf, codigo, estado) VALUES ('Marcelo', '444.444.444-44', 333, 'BH');
```

<h2>3. Consultas Realizadas</h2>

<p><code>Visualizar todos os carros:</code></p>

```
SELECT * FROM carros;

```

<p><b>Visualizar todos os clientes:</b></p>

```
SELECT * FROM clientes;
```


<p><b>Consultar relação entre clientes e carros:</b></p>

<p>Retorna os clientes associados aos carros, unindo as tabelas <code>clientes</code> e <code>carros.</code></p>

````
SELECT * 
FROM clientes 
JOIN carros 
ON clientes.codigo = carros.codigo;
```







