<<<<<<< HEAD
# Cálculo relacional de tuplas - Aula 05

***



***

* Abordagem "paralela" a algebra relacional pra fazer consultas

### Introdução

* A consulta tem a forma { t | P(t) }
  * t é a variavel tupla
    * Posso selecionar atributos da tupla, fazendo, na consulta, t.Ai, t.Aj,...
  * P(t) é o predicado lógico que determina a condição da consulta

* Ex de projeção

  * Em algebra
    $$
    \pi_{SNOME, PNOME, SALARIO}(EMPREGADO)
    $$
    

  * Em CRT
    $$
    \{ t.snome, t.pnome, salario| empregado(t)\}
    $$

* Ex de select (recupere todos empregados femininos)

  * Algebra
    $$
    \sigma_{sexo=f}(EMPREGADO)
    $$
    

  * CRT
    $$
    \{t \ | \ EMPREGADO(t) AND t.sexo=F\}
    $$
    

* Ex de join (Pegue o nome e endereço de todos empregados que trabalham pro departamento de pesquisa)

  * CRT
    $$
    \{ t.PNOME, t.SNOME, t.ENDERECO \ | \ EMPREGADO(t) \ AND \\ (\exists d) (DEPARTAMENTO(d)\  AND\  d.NOME\ =\ ' Pesquisa' \ AND \ d.DNUMERO = t.DNO)\}
    $$

    * Ou seja: pegue o primeiro e segundo nome e o endereço de um empregado t que, para um certo d, trabalha nesse departamento d(d.numero = t.dno) , que é um departamento de pesquisa
=======
# Aula 05

***

### Para a próxima aula

* Ter divisão fixa na cabeça
* Entender TODOS tipos de join.

***

## Retomando

### SQL

* DML: Linguagem de consulta
* Dica: para construir consultas em SQL, pensar primeiro na consulta em Álgebra Relacional e depois em Cálculo, e só então pensar em SQL.
  * A Sintaxe de cálculo relacional é muito proxima da sintaxe de SQL.



***

### Aula de hoje

* Aliases: Facilitam nomes de relações ou colunas quando usamos muito esse dado nas nossas consultas.

* Ex.:

  ```SQL
  SELECT PNOME, SNOME
  FROM EMPREGADO as EM
  WHERE EM.NSS=15 AND EM.NDEP > 10
  ```

* Cláusula WHERE

  * Ausência seleciona todas tuplas da relação especificada no FROM

    * Equivale a escrever WHERE TRUE

  * Se estivermos selecionando de duas tabelas sem especificar uma condição no WHERE, estamos fazendo um produto cartesiano. Ex.:

    ```sql
    SELECT PNOME, SNOME
    FROM EMPREGADO, DEPARTAMENTO
    ```

    Isso é um produto cartesiano. Um join seria:

    ```sql
    SELECT PNOME, SNOME
    FROM EMPREGADO, DEPARTAMENTE
    WHERE NSS=GERNSS
    ```

  * Apesar de podermos usar um WHERE vazio, não é recomendável. isso pode gerar resultados incorretos e/ou volumosos.

* Uso do *

  * Seleciona todos  atributos da tupla selecionada

    ```sql
    SELECT * FROM EMPREGADO
    WHERE DNUM=6
    ```

  * Nesse caso, selecionamos tuplas que contém PNOME, SNOME, NSS...

* Uso do DISTINCT

  * Util pra eliminar tuplas repetidas

    ```sql
    SELECT DISTINCT SALARIO
    FROM EMPREGADO
    ```

* Operações de conjunto

  * SQL apresenta operações de conjunto (união, subtração, intersecção). Aplica-se apenas a relações compatíveis (relações devem ter mesma quantidade de atributos e domínio).

  * Ex: Listar os números de projetos em que o empregado de sobrenome smith trabalhe ou que sejam controlados por algum departamento gerenciado pelo empregado de sobrenome smith

  ```SQL
  SELECT PNUM
  (FROM PROJETO, DEPARTAMENTO, EMPREGADO
  WHERE DNUM=DNUMBER AND GERNSS = NSS AND SNOME='SMITH'
   UNION
   SELECT PNUMERO
   FROM PROJETO, TRABALHA_PARA, EMPREGADO
   WHERE PNUMERO = PNO AND ENSS=NSS AND SNOME = 'SMITH'
  ```

  

* Outras operações:

  * UNION ALL
  * EXCEPT ALL
  * INTERSECT ALL

* Consultas aninhadas

  * Podemos especificar outra consulta dentro d euma clausula WHERE.
  * Ex: Recupere o nome e o endereço de todos os empregados que trabalham para o departamento de pesquisa.

  ```sql
  SELECT PNOME, SNOME, ENDERECO
  FROM EMPREGADO
  WHERE DNUM IN (SELECT DNUMERO
                FROM DEPARTAMENTO
                WHERE DNOME='PESQUISA')
  ```

  

* Nulidade

  * Podemos usar o valor NULL para identificar tuplas com valores não definidos

    * Ex: Recupre nome e sobrenome de  empregados que não possuem empregados

    ```sql
    SELECT pnome, snome
    FROM EMPREGADO
    WHERE NSSUPER IS NULL
    ```

    

* Funções agregadas

  * COUNT

  * MAX

  * MIN

  * AVG

  * EX.: Encontrar o maior salário, o menor salário e a média salarial de todos os empregados

    ```sql
    SELECT MAX(salario) MIN(salario) AVG(salario)
    FROM empregado
    ```

    

  * Função group by: ? 
  * Clausula having: ?
>>>>>>> 4c1bb9454824af58c1e8dcab2459a404019edcab
