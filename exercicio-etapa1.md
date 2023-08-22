### Criando o desafio 


# Exercícios de Banco de Dados - Etapa 2

## CRUD - Cadastro geral

### Cadastre pelo menos 5 cursos:

- Front-End, carga horária 40h
- Back-End, carga horária 80h
- UX/UI Design, carga horária 30h
- Figma, carga horária 10h
- Redes de Computadores, carga horária 100h
- Atenção: por enquanto, deixe o campo professor_id como nulo


```sql
INSERT INTO curso(nomeCurso, cargaHoraria, professor_id)
VALUES(
    'Front-End',
     40,
    null);

INSERT INTO curso(nomeCurso, cargaHoraria, professor_id)
VALUES(
    'Back-End',
     80,
    null);

INSERT INTO cursos(nomeCurso, cargaHoraria, professor_id)
VALUES(
    'UX/UI Design',
     30,
    null);

INSERT INTO cursos(nomeCurso, cargaHoraria, professor_id)
VALUES(
    'Figma, carga horária ',
     10,
    null)
INSERT INTO cursos(nomeCurso, cargaHoraria, professor_id)
VALUES(
        'Redes de Computadores',
        80
    );


```

### Cadastre pelo menos 5 professores:

- Jon Oliva, área infra
- Lemmy Kilmister, área design
- Neil Peart, área design
- Ozzy Osbourne, área desenvolvimento
- David Gilmour, área desenvolvimento

```sql
INSERT INTO professores(nomeProf, materia, curso_id)VALUES(
    'Pedeira',
    'infra',
    5);

UPDATE professores SET materia = 'design' WHERE id = 2; 
```

### Atualize os dados do campo professor_id da tabela cursos, associando cada curso ao seu professor correspondente.

```sql
UPDATE cursos SET professor_id = 5 WHERE id = 1;

UPDATE cursos SET professor_id = 4 WHERE id = 2;

UPDATE cursos SET professor_id = 3 WHERE id = 3;

UPDATE cursos SET professor_id = 2 WHERE id = 4;

UPDATE cursos SET professor_id = 1 WHERE id = 5;


```


### Cadastre pelo menos 10 alunos distribuidos aleatoriamente dentre os cursos, com datas de nascimento variadas, notas baixas e altas (sempre entre 0.00 e 10.00).

```sql
INSERT INTO alunos(nomeAluno, nasc, nota1, nota2, curso_id)VALUES(
    'Vinicius Miranda',
    '2001/12/17',
    08.05.
    07.06.
    1).
    (
        'Tanaka Marina',
    '1999/05/15',
    07.08,
    09.02,
    3
    ),
     (
        'Isabela Karen',
    '2000/05/15',
    09.09,
    05.10,
    2
    ),

     (
        'Herbert Miranda',
    '1997/07/18',
    06.07,
    10.09,
    4
    ),

     (
        'Patricia',
    '2000/11/05',
    06.07,
    10.09,
    2
    ),

     (
        'Scarlett Falbo',
    '2006/01/28',
    06.07,
    10.09,
    5
    ),

     (
        'Alvaro Claviere',
    '1999/02/03',
    06.07,
    10.09,
    3
    ),

     (
        'Maria do Carmo',
    '1999/06/08',
    06.07,
    10.09,
    1
    ),

     (
        'Melissa Medeiro',
    '2004/05/31',
    08.07,
    00.05,
    2
    ),

     (
        'Ricardo Loureiro',
    '2005/01/05',
    04.08,
    07.08,
    5
    );


```