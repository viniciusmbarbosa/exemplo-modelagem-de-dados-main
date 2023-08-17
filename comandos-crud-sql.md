# Comandos para operações CRUD no Banco de dados

## Resumo

- C -> CREATE (Inserir dados usando comando `INSERT`)
- R -> READ (Ler dados usando comando `SELECT`)
- U -> UPDATE (atualizar dados usando comando `UPDATE`)
- D -> DELETE (excluir dados usando comando `DELETE`)


## INSERT

### Fabricantes

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple');

INSERT INTO fabricantes (nome) VALUE ('LG'),('Samsung'),('Brastemp');

INSERT INTO fabricantes (nome) VALUE('Positivo'), ('Microsoft');
```

### Produtos

```sql
INSERT INTO produtos(nome, preco, descricao, quantidade, fabricante_id) 
VALUE(
    'Ultrabook', 
    3500,
    'Equipamento de última geração cheio de recursos, com processador Intel core i9 do balacobaco',
    7,
    2 -- Id do gabricante Dell
);


INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUE(
    'Tablet Android',
    'Tablet com a versão 14 do sistema operacional android, possui tela de 10 polegadas e armazenamento de 128 GB, e 64 GB de RAM por que o Vinícius pergunta',
    1500.99,
    4,
    5
);

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUE(
    'Geladeira',
    'Refrigerador frost-free com acesso à Internet',
    5000,
    12,
    6 
),
(
    'Iphone 18 Pro Max',
    'Smartphone Apple cheio das frescuras e caro pra caramba. Coisa de rico..',
    12666.66,
    3,
    3
),
(
    'Ipad Mini',
    'Tablet Apple com tela retina display e blablabla.',
    4999.01,
    5,
    3
);

INSERT INTO produto(nome,descricao, preco, quantidade,fabricante_id)
VALUE(
    'Xbox Series S',
    'Velocidade e desempenho de última geração.',
    1997,
    5,
    8
);

INSERT INTO produtos(nome,descricao, preco, quantidade,fabricante_id)
VALUE(
    'Notebook Motion',
    'Descricão: intel DUal Core 4GB de RAM, 128GB SSD e Tela 14,1 polegada',
    1213.65,
    8,
    7
);

```

## SELECT

```sql
SELECT * FROM produtos;

SELECT nome, preco FROM produtos;

SELECT preco, nome FROM produtos;

SELECT nome, preco, quantidade FROM produtos
/* WHERE significa onde! */
WHERE preco < 5000;

SELECT nome, descricao FROM produtos WHERE fabricante_id = 3;
```

## SELECT: Outras formas de uso


### Classificando

``` sql
SELECT nome, preco FROM produtos ORDER BY nome;
SELECT nome, preco FROM produtos ORDER BY preco;
SELECT nome, preco FROM produtos ORDER BY preco DESC;

-- DESC: classificação em ordem decrescente
-- ASC (padrão): classificação em ordem crescente


```

### Buscando de dados

``` sql
SELECT nome, descricao FROM produtos WHERE descricao LIKE '%sistema%';

-- Usamos o operador LIKE e o caractere coringa % para permitir uma busca da palavra indicada em qualquer posição dentro do texto.
-- Nesete contexto, o % significa 'qualquer texto' antes da palavra ou depois da palavra.


```

### Operações e funções de agregação

``` sql
SELECT SUM(preco) FROM produtos; -- SOMA
SELECT SUM(preco) as Total FROM produtos; -- Alias/ apedido

-- Exemplo de alias/apelido para outras colunas
SELECT nome as produtos, preco as "Preço" FROM produtos;
SELECT nome produto, preco "Preço" FROM produto;

-- MÉDIA
SELECT AVG(preco) as "Média dos Preços" FROM produtos;
SELECT ROUND(AVG(preco), 2) as "Média dos preços" FROM produtos;

-- CONTAGEM
SELECT COUNT(id) as "QTD de produtos" FROM produtos;

-- DISTINCT é usada para distinguir o id dos produtos.

SELECT COUNT(DISTINCT fabricante_id) as "Qtd de fabricantes com produtos" FROM produtos;

``` 

### Operadores lógicos: E, OU, NÃO


### E
``` sql
SELECT nome, preco FROM produtos WHERE 
WHERE preco >= 2000 AND preco <= 6000;

-- A query abaixxo não retorna registros
-- já que as condições não foram totalmente atendidas
SELECT nome, preco FROM produtos 
WHERE preco > 5000 AND preco <= 6000;



```

#### OU

``` sql
SELECT nome, preco FROM produtos
WHERE preco > 5000 OR preco <= 3000;

-- Exiba nome e preço somente dos produtos da Apple e da Asus

SELECT nome, preco FROM produtos WHERE fabricante_id = 3 OR fabricante_id = 5;


SELECT nome, preco FROM produtos WHERE fabricante_id IN(3, 5);


SELECT nome, preco FROM produtos WHERE fabricante_id NOT IN(3, 5);
```

#### NÃO 

```sql

SELECT nome, descricao, preco FROM produtos WHERE NOT fabricante_id = 8;

-- Um operador que pode substituir o NOT (!)
SELECT nome, descricao, preco FROM produtos WHERE  fabricante_id != 8;

```

## UPDATE

```sql
UPDATE fabricantes SET nome = 'Asus do Brasil'
WHERE id = 1; -- NÃO ESQUECER DO WHERE!! PERIGO!


UPDATE produtos SET preco = 6549.74
WHERE id = 4


-- Altere a quantidade dos produtos da Apple e da Samsung para 20

UPDATE produtos SET quantidade = 20 
WHERE id = 3 OR id = 5; 
```


## DELETE 

```sql

-- NÃO SE ESQUEÇA DO WHERE!! PERIGO

DELETE FROM fabricante WHERE id = 1;
DELETE FROM fabricante WHERE id = 4;
DELETE FROM fabricantes WHERE id = 3;

-- A query abaixo NÂO FUNCIONA devido à restrição 
-- de chave estrangeira/relacionamento, ou seja, 
-- existem produtos associados ao fabricante 3 (apple)
-- DELETE FROM fabricantes WHERE id = 3;

```

---
