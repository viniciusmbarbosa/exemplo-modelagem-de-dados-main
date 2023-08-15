# Comandos SQL - referências

## Modelagem Física com comandos **DDL**


### Crianr banco de dados

CREATE DATABASE vendas CHARACTER SET utf8mb4

### Criar tabela de fabricantes

```SQL
CREATE TABLE fabricante(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```
### Visualizar detalher estruturais da tabela

```sql
DESC fabricantes;
```

### Criar tabela de produtos
``` SQL
CREATE TABLE produto(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
     descricao TEXT (500) NULL,
    preco DECIMAL (6,2) NOT NULL,
    frabricante_id INT NOT NULL
);
```

### Criação do relacionamento entre as tabelas (chave estrangeira)

```sql
ALTER TABLE produtos
    -- CONSTRAINT/RESTRIÇÃO indicando o nome do relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes

    -- Criando a chave-estrangeira (fabricante_id) que
    -- aponta para a chave-primária (id) de outra tabela (fabricantes)
    FOREIGN KEY (fabricante_id) references fabricante(id);
```  

### Exemplos de alterações estruturais na tabela

#### Renomear tabela

```SQL
ALTER TABLE fabricantes RENAME TO fornecedores;
ALTER TABLE fornecedores RENAME TO fabricantes;
```

#### Modificar colunas
```SQL
ALTER TABLE produtos
    MODIFY COLUMN preco INT NULL ;

ALTER TABLE produtos
    MODIFY COLUMN preco DECIMAL (6,2) NOT NULL;
```

```SQL
ALTER TABLE fabricantes
    CHANGE nome nome_do_fabricante VARCHAR(20) NOT NULL;

    ALTER TABLE fabricantes
    CHANGE nome nome_do_fabricante nome VARCHAR(45) NOT NULL;
```

#### Adicionar coluna
```sql
ALTER TABLE  produtos
    ADD quantidade INT NULL AFTER preco;

```
