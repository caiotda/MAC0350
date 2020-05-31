# Aula 06



***

Atualizações sobre aula virtual

* Provas abolidas
* Projeto priorizado
* Grupo de 2 ou 3 pessoas
* Proximas listas de exercicio de SQL serão feitas encima de uma base de dados remota feita pelos monitores
* 

***

Atualizações sobre o projeto

* Tem tres fases

  1.  Descrição do domínio da aplicação: escolher o que quer modelar
  2. Projeto conceitual da aplicação: descrever o domínio em classes. Criar o Projeto lógico físico: mapear pro modelo relacional. Criar a base de dados.
  3. Consultas em SQL.
  4. Utilizar uma interface python (Django provavelmente).

  Bonus: fazer inserção via interface, não diretamente no banco

***

# SQL

### Introdução

* DDL e DML: Linguagem de definição de dados e de manipulação de dados
  * DDL: especificação do esquema da base de dados.
  * DML: inserção remoção, alteração de dados.

```sql
CREATE TABLE COMPANHIA.EMPREGADO {
	PNOME	VARCHAR(15)	NOT NULL,
	MNOME	CHAR
	NSS		INTEGER(9)	NOT NULL
	PRIMARY_KEY NSS
}

```

### DDL

* ADD: adiciona atributo na tabela
* DROP: elimina todos atributos especificados ou tabela
  * DROP TABLE
  * DROP ATRIBUTO
  * DROP SCHEMA
    * Exclui esquema do banco

### DML

* Alguns comandos: 

  * INSERT

    * Insere uma ou mais tuplas em uma tablea

      ```sql
      INSERT INTO PROJETO VALUES('ProductX', 1, 'bellaire', '5')
      INSERT INTO PROJETO VALUES('ProductY', 2, 'sugarland', '5')
      ```

    * Existem outras formas de fazer inserção, como criar uma tabela temporaria.

    * Também dá pra inserir o resultado de uma consulta

  * UPDATE

    * 

  * DELETE

  * SELECT

    * Comando de consulta

    * Sintaxe

      ```sql
      SELECT [DISTINCT | ALL] <lista_de_atributos> FROM < lista_de_tabelas>  [WHERE <condicoes> GROUP BY <atributo> HAVING <condição> ORDER BY atributo [ASC | DESC]]
      ```

    * A graça do SQL é ele ser declarativo, você apenas informa o que quer fazer, sem se preocupar com implementações

    * Exemplos de consultas simples:

      * Recuperar a data de aniversario e o endereço do emprego chamado ' John Smith'. Vamos comparar SQL com algebra.

        ```sql
        SELECT DANANASC, ENDERECO
        FROM EMPREGADO
        WHERE PNOME='John' AND MNOME= 'B.' AND SNOME='Smith'
        
        ```

        Em algebra relacional: 
        $$
        EMP\_SMITH \leftarrow \sigma_{pnome = " john" \ AND\  MNOME="B." \ AND\  SNOME=" SMITH"}(empregado)\\
        resultado \leftarrow \pi_{DATANASC, ENDERECO}(EMP\_SMITH)
        $$
        

        

        Em Calculo relacional de tuplas
        $$
        \{e.DATANASC, e.ENDERECO\  |\  EMPREGADO(E) \ AND \\ e.PNOME='John' AND \ e.MNOME=" B" AND e.SNOME="Smith"\}
        $$
        

        * O SQL abstrai muito poder da algebra e do calculo, mas traz simplicidade

      * Consulta2: obter o nome e endereço dos empregados que trabalham para o departamento de 'Pesquisa'