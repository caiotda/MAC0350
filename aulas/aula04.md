# Álgebra Relacional e linguagens formais de consulta 

***

* Cap07

### Conteúdo dessa aula

* Algebra relacional
* Calculo relacional

***

### introdução

* Álgebra relacional: conjunto de operações que permitem consultas de relações

### Operador Select - sigma

* Seleciona, segundo alguma condição, tuplas de uma relação

  * ex: selecionar os empregados que trabalham para o departamento 4: 
    $$
    \sigma{NDEP=4}(EMPREGADO
    $$

  * Expecificio a condição(Naquele subscrito do sigma. Ai posso usar operações matematicas  e lógicas) e o alvo

* Posso usar operadores logicos (AND OR) e operadores matematicos (>=, <=, =, >, <).

* Características e propriedades
  * O grau do resultado é o mesmo da relação original
  * Comutativa: posso trocar selects cascateados por selects unidos por um AND.

### Operador project - pi

* O project seleciona **colunas**.

* Uso
  $$
  \pi_{SNOME, PNOME, SALARIO}(EMPREGADO)
  $$

* Retorna uma nova relação, selecionando as colunas especificadas da relação original.
* Note que isso pode **excluir a coluna que contem a chave da relação**. Se há replicação no resultado (caso não selecionamos a coluna com a chave), o **project exclui as repetidas**. 
  
* Isso é feito pra evitar inconsistências ao performar um project.
  
* Características
  * A quantidade de tuplas resultantes sera menor ou igual a relação orignal
  * **NÂO** é comutativa.

* OBS: podemos concatenar operadores diferentes. Podemos fazer um SELECT seguido de um PROJECT, por exemplo (mostrar o salario e o nome de todos funcionarios que ganham menos que R$5000,00).
  * Podemos, inclusive, fracionar as relações criando **relação intermediarias**.
    * ex: DEP5_EMP5 <- sigma(ndep = 5) (EMPREGADO)
      * result <- pi(PNOME, SNOME, SALARIO)(DEP5_EMP5)
    * É como se guardasse uma função complexa numa variavel, por exempoo.
* Podemos renomear atributos após fazer consultas.

### Operações de teoria dos conjuntos

* União: todos tuplas de R e S
* Intersec: todas tuplas comuns de R e S
* Diferença simétrica: toda tupla que esta em R e que não está em S
* Produto cartesiano: combinação de todas tuplas de R e S
  * Serve pra mostrar mais informações
  * Também cria relações entre duas tabelas
    * O problema é que é dificil criar uma relação na qual temos que combinar dois conjuntos completamente
    * Um ex é matricular alunos do primeiro ano em disciplinas obrigatorias. Podemos criar uma tabela para as materias do primeiro semestre e fazer um produto cartesiano entre a tabela dos ingressantes e as disciplinas obrigatorias pra ja ter uma tabela contendo todas disciplinas daqueles alunos.
  * A maior utilidade é unir tabelas  e depois fazer uma seleção.
* As tres primeiras precisam que as tabelas sejam compativeis.
* Produto cartesiano não é muito intuitivo.

### Operador Join

* É um produto cartesiano seguido por seleção.
* Utilizado pra combinar informações de duas ou mais relações.

### Operador DIVISION

* O JOIN possui uma limitação: ele é bem custoso, por fazer um produto cartesiano entre duas tabelas.
  * Se uma tabela tiver um grau de relacionamento maior que 4, fica muito custoso.

* O DIVISION seleciona todos elementos de A que respeitem uma condição (Não ficou muito claro....)

  * Mas essa condição, ao contrario de um SELECT, não é uma condição booleana que é passada pelas colunas (selecione todos funcionarios que ganham mais que R$5000: essa verificação é feita olhando a coluna SALARIO e olhamos tupla a tupla). E sim uma outra tabela: Feito um join, procurar um conjunto de tuplas que possuem um outro padrão especificado em uma outra tabela
    * Ex: encontre funcionarios que tabelam em todos projetos
      * TODOS_PROJETOS = PROJECT_(PROJETOS)(EMPREGADOS)
      * TRABALHADORES = DIVISION (EMPREGADOS, TODOS_PROJETOS)

  ***

  ### Funções de agregação

  * Recebem um conjunto de tuplas e retornam um único valor

    * SUM
    * AVERAGE
    * MAXIMUM
    * MINIMUM
    * COUNT

  * Para usar uma função agragada, utilizamos o operador FUNCTION

  * Especificamos um **atributo de agregamento** para especificar o que devemos agregar

    



***

## TAREFA

* Fazer a lista do fim do capítulo 7 da apostila.
* Estudar inner join, outer join, left join, right join