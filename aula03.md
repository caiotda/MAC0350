# Aula 03

## Modelo relacional

* Grau da relação: quantidade de atributos

* Ex da aula passada, relação DEPENDENTE

  * Grau 5
  * Cada relação tem seu domínio. Ex: Código do cliente, seu domínio são 4 dígitos que reoresentam o código do cliente.
  * O nome: seu dominio são caracteres que representam nome dos dependentes
  * Enfim, o domínio de uma propriedade estabelece **como** o atributo deve ser

* **Notação relacional**

  * R - **Relação Esquema**: Descreve como uma relação se comporta, contém quantos atributos a relação terá
    * Ex: R(t1,t2, ..., tn): uma relação com grau n, com atributos t1, t2, ..., tn
  * r(R): Representa as tuplas de R, onde cada tupla é um t
    * t = <v1, v2, ..., vn> tupla de R
  * t[Ai] indica o valor vi em t para o atributo Ai

  ### Atributos chaves de uma relação

  * Superchave: Subconjunto de atributos que pode identificar unicamente as tuplas de uma relação.
  * Chave: É a menor superchave possível.
  * Chave-candidatas: Chaves de uma relação
  * Chave-primária: Uma das chaves candidatas que foi escolhida como chave.

  ### Restrições de integridade

  * São regras que restringem os valores que podem ser armazenados nas relações
  * Um SGBD deve garantir que:
    * Restrições de chave: os valores das **chaves-candidatas**  devem ser únicos em todas tuplas da relação
    * Restrições da entidade: chaves-**primárias** não devem ser nulas
    * REstrição de integridade referencial: Usada pra manter a consistência entre tuplas Estabelece que um valor de atributo, que faz referência a uma outra dupla, deve-se referir a uma tupla existente
      * Benefícios: no Júpiter, todo aluno está linkado a uma disciplina. Estabelecer essa restrição garante que não consigo excluir um aluno que está matriculado em algumas disciplina, ou apagar uma disciplina que possui alunos.
      * Isso, inclusive, é um ponto positivo pra o modelo de dados relacional: ele **enforça** integridade entre os dados.

  ### Mapeamento do DER/MDR - Sair do "desenhinho" e ir pro modelo relacional

  * Como fazer o esquema do BD?
    * Passo1
      * PAra cada tipo de entidade E no DER, crie uma relação R que inclua todos atributos simples dos atributos
        * Para cada cara no DER, ou seja, cada entidade, vira uma tabela.
      * Escolha um dos atributos chaves de E como a chave-primária de R
      * Se a chave escolhida é composta, então o conjunto de atributos simples que o compôem formarão a chave-primária de R.
    * Passo 2
      * Para cada tipo de entidade fraca @ do DER com o tipo de entidade de identificação E, 
    * Passo 3
      * Pra cada relacionamento binario 1:1, R, identifique as relações S e T que correspondem aos tipos de entidades que participam de R
    * Ele explicou o resto em aula, depois copio aqui