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