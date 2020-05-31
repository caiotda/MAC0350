# MAC 0350

### Professor: João Eduardo Ferreira (JEF)

***

### Tópicos abordados

* Informações gerais da disciplina
* O que é um BD?
* Funções de um BD
* Abstrações: Classe e relacionamentos

***

## Informações gerais

* Objetivo: Projetar e implementar um Sistema de Software que utiliza um banco de dados com escala transacional

* Aprender bancos de dados **relacionais**.

  * postreSQL, mySQL
  * Utilizado para dados estruturados (apresentam estrutura clara)

* **Funções de um BD**

  * Armazenar e recuperar dados com **eficiência**.
    * Armazenar com **confiabilidade**
    * E recuperar com **otimização**

* Como um BD é estruturado?

  * Estrutura de dados + funcionalidades de manipulação (Linguagem) = **modelo** de banco de dados (**conceitual**)

    * Não ser confundido com o conceito de **modelagem** de dados: Tomar dados do mundo real e estrutura-los no BD seguindo um modelo e manipulaveis via um gerenciador.
    * É interessante fazer uma modelagem independente de modelo e independente de gerenciador, torna a modelagem mais forte. Essa abstração, inclusive, torna o BD mais **resiliente**.

  * Gerenciador de banco de dados (**Físico**) - Manipula os dados baseado no modelo do bd.

    ***

  ## Modelagem de um BD

  *  Partindo de um universo de dados, começamos **classificando os dados**, criando classes **disjuntas** com dados similares (Aqui uma estrutura de dados OO se sai bem).
    * Agrupa os dados de forma **intra**relocionada: Cada classe possui todos os atributos que são capazes de caracterizar os dados pertencentes à Classe. E esses dados devem ser enumeráveis, isto é, um desses atributos deve ser um identificador único.
  * E então, enumeramos os elementos de cada classe, de forma que o elemento seja **univocamente identificado**.
    * Também podemos dar características a cada elemento (ou **atributos**) da classe.
    * Se o atributo classificar o elemento como membro da classe, é um atributo de classe. Existem caracterísitcas extras àquelas que caracterizam um elemento como membro de uma classe também.
  * **Relações interclasse**: Até agora caracterizamos dados como pertencentes a uma classe. Mas podemos criar relações entre elementos de classes diferentes. Chamamos isso de **relacionamento *inter* classe**.
  * **Cardinalidade de relacionamentos**
    * Podemos restringir como funciona um relacionamento baseado em quantidades
    * Ex: alunos matriculados em disciplinas
      * 1 aluno pode se matricular em N disciplinas
      * Enquanto que 1 disciplina pode servir M alunos

  ***

  ### Recapitulando

  * Abstrações : 
    * Classe (**intra**classe)
    * Relacionamento (**Inter**classe)

  ​	



