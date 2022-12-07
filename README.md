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


```  ```


<h1>Resultado esperado</h1>



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

<br>

<h1> 3ª Questão </h1>

Crie um comando SQL que retorne o e-mail de todos os alunos maiores de idade.

```select e_mail 
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
select tb_aluno.nome_aluno, tb_curso.nome_curso
from tb_aluno
inner join tb_curso
on tb_aluno.cod_aluno = tb_curso.cod_curso
where sexo = 'F' and nome_curso ='Medicina'
```
<h1>Resultado esperado</h1>

![f11](https://user-images.githubusercontent.com/105823539/206072549-00c9fb9a-e970-4507-8185-894225742439.png)

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
