<h1> PROVA PRÁTICA DE SQL </h1>

1ª abra o arquivo "bdescola.txt" acima e execute no PostgreSQL, utilizando a ferramenta PgAdmin4 no seu computador. 


<h1>Resultado esperado</h1>

<h3> TB_Aluno </h3>


![f1](https://user-images.githubusercontent.com/105823539/206056988-db155227-4803-4f3d-befc-fa33ffe21860.png)

<h3> TB_Curso </h3>

![f2](https://user-images.githubusercontent.com/105823539/206057340-eb35bdcb-531e-41ed-b470-309ec1202d42.png)

<h3> TB_Matricula </h3>

![f3](https://user-images.githubusercontent.com/105823539/206057706-40801bb9-8991-44e0-8651-15df8652db80.png)

<h1> 1ª Questão </h1>

Faça um comando SQL para matricular o aluno “Pedro César” no curso de
Informática. Os dados devem ser inseridos na tabela TB_MATRÍCULA.


```
insert into tb_aluno (cod_aluno,nome_aluno, sexo)
values (4,'Pedro César', 'M');

insert into tb_matriculas (cod_curso,cod_aluno)
values (4,4) 

```


<h1>Resultado esperado</h1>

![f4](https://user-images.githubusercontent.com/105823539/206182695-4b273ff5-a023-4425-9dd8-ec21997266d5.png)


<h1> 2ª Questão </h1>

Escreva um comando SQL que retorne os nomes dos alunos e do(s) cursos em
que estão matriculados. Os dados deverão estar ordenados pelo nome do curso.

```  
select tb_aluno.nome_aluno, tb_curso.nome_curso
from tb_aluno
inner join tb_matriculas
on tb_aluno.cod_aluno = tb_matriculas.cod_aluno
inner join tb_curso
on tb_curso.cod_curso =tb_matriculas.cod_curso 
```


<h1> Resultado esperado</h1>

![f5](https://user-images.githubusercontent.com/105823539/206185332-b1dfd259-a1a1-4986-8c45-2cb6b23c76a6.png)

<br>

<h1> 3ª Questão </h1>

Crie um comando SQL que retorne o e-mail de todos os alunos maiores de idade.

```
select e_mail 
from tb_aluno 
where 2022 - ano_nasc >= 18
  ```
  
  
  <h1>Resultado Eseperado</h1>

![f6](https://user-images.githubusercontent.com/105823539/206065663-7c1da64d-2191-40ec-af97-62c8f491125e.png)

<br>

<h1> 4ª Questão</h1>

Desenvolva um comando SQL que mostre o total de alunos.

```
select count (cod_aluno) from tb_aluno
```


<h1>Resultado esperado</h1>

![f7](https://user-images.githubusercontent.com/105823539/206186052-31f25064-6e8d-4216-a6de-aff30239765f.png)
<br>

<h1> 5ª Questão</h1>

Escreva um comando SQL para listar o total de alunos matriculador em cada curso.

``` ```


<h1>Resultado esperado</h1>

<br>

<h1> 6ª Questão</h1>

Desenvolva um comando SQL que retorne o nome de todos os alunos maiores que
18 anos.

```
select nome_aluno from tb_aluno where 2022 - ano_nasc >= 18

```


<h1>Resultado esperado</h1>

![f9](https://user-images.githubusercontent.com/105823539/206068222-6a1e2fb5-12b0-4f39-b51e-1e17f80058e9.png)

<br>

<h1> 7ª Questão</h1>

Faça um comando SQL que retorne o nome de todas as mulheres.

```
select nome_aluno from tb_aluno where sexo = 'F'

```


<h1>Resultado esperado</h1>

![f10](https://user-images.githubusercontent.com/105823539/206068885-f3952766-93c8-4d84-872b-777b01d48487.png)

<br>

<h1 >8ª Questão </h1>

Faça um comando SQL que retorne o nome de todas as mulheres matriculadas
no curso de Medicina.

``` 
select nome_aluno, tb_curso.nome_curso as nome_curso
from tb_aluno
inner join tb_curso
on  tb_curso.nome_curso = 'Medicina'
where sexo = 'F' 
```
<h1>Resultado esperado</h1>

![f11](https://user-images.githubusercontent.com/105823539/206321575-e66cfd44-2f3e-42dc-90a5-69c09eab1739.png)


<br>

<h1 >9ª Questão </h1>

Faça um comando SQL que retorne os nomes dos cursos ordenados por ordem
alfabética.

```
select nome_curso from tb_curso order by nome_curso

```

<h1>Resultado esperado</h1>

![f12](https://user-images.githubusercontent.com/105823539/206073424-a617aed5-3ec2-474b-92d8-3cb84d07b31d.png)

<br>

<h1 >10ª Questão </h1>
Crie o enunciado de uma consulta SQL que utilize “junção” (com resposta).
<br>
<br>
<i>-Retorne respectivamente o nome dos alunos, o sexo e o curso em que estão matriculados.</i>


```
select tb_aluno.nome_aluno,sexo, tb_curso.nome_curso
from tb_aluno
inner join tb_curso
on tb_aluno.cod_aluno = tb_curso.cod_curso
```

<h1>Resultado esperado</h1>

![f13](https://user-images.githubusercontent.com/105823539/206186449-ea435a56-3b99-4a02-831c-aa94d9c16b00.png)

---

<h1>Questões teóricas</h1>

<h3>1. Defina: SQL.</h3>
<h5>
  O Structured Query Language,ou Linguagem de Consulta Estruturada, é uma linguagem para acesso,criação e manipulação de dados, sendo utilizada principalmente para trabalhar com banco de dados relacionais.  </h5>
  
  <h3> 2. Faça um relacionamento cronológico sobre SQL.</h3>
<h5>
O SQL foi desenvolvido originalmente nos laboratórios da IBM na década de 70 sendo lançado pela Oracle em 1979. Na década de 80,a empresa American National Standards Institute (ANSI) iniciou seus trabalhos, com a ideia de que o SQL fosse padronizado para se tornar a linguagem padrão para gerenciamento de informações em um banco de dados relacional. Posteriormente, o SQL sofreu importantes melhorias com modificações e adições até os dias atuais. </h5>

<h3>3. Liste as principais caracteríticas de SQL. </h3>

<h5>
- Possui sintaxe e semântica próprias que tenta se aproximar à língua inglesa.
  <br>
  
  
-Utilizada tanto por programadores"normais" tanto também pelos Administradores do Banco de Dados.
  
-Permite fazer uma série de operações de inclusão, de pesquisa e de definição de dados.
  
-Possui linguagem do tipo declarativa. </h5>


<h3> 4.Descreva a sintaxe do comando SQL: SELECT. Quais cláusulas são obrigatórias e
quais são opcionais? </h3>

<h5>
  
Select (nome_coluna) from (nome_tabela)

Após o uso do Select será preciso a escolha de uma coluna para ser selecionada. Logo após, o From é usado para especificar a origem da coluna.
Tanto select e from são cláusulas obrigatórias em uma consulta SQL. </h5>


<h3> 5. Qual a importância da linguagem SQL no desenvolvimento de softwares
atualmente? Justifique. </h3>

<h5> 

  A importância do SQL no software reside principalmente no armazenamento de dados. Com o SQL é possível criar um banco de dados para armazenar informações, por exemplo, sobre uma empresa.</h5>



