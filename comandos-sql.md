# Comandos SQL - referências

## Modelagem Física com comandos **DDL**


### Crianr banco de dados

CREATED DATANASE vendas CHARACTER SET utf8mb4

### Criar tabela de fabricantes

```SQL
CREATE TABLE fabricante(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```