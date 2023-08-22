# Exercícios de Banco de Dados - Etapa 3

## CRUD - Consultas

### 1- Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

```sql
SELECT nomeAluno as Alunos,
nasc as Nascimento 
from alunos WHERE > 2009 GROUP BY Alunos;



```

![](./foto-etapa3/01.png)

### 2- Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

``` sql
SELECT nomeAluno as Aluno,
nota1 as 1° nota,
nota2 as 2° nota, 
ROUND((nota1 + nota2)/2, 2 ) AS média
FROM alunos
```
![](./foto-etapa3/02.png)

### 3- Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

```sql

SELECT cursos as Aluno,
cargaHoraria as 'Carga Horária',
ROUND((cargaHoraria * 0.25)) as 'Limite de faltas'
FROM cursos
ORDER BY cursos desc;


```
![](./foto-etapa3/03.png)

### 4- Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".

```sql

    SELECT nomeProf as Professor,
    materia as Matéria from professores WHERE materia LIKE '%desenvolvimento%';
```
![](./foto-etapa3/04.png)


```sql


```