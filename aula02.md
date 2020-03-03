# Aula 02

***

Comentários sobre a última aula

* Tipo de entidade é análogo a estrutura da classe
* Instância da classe é análogo a um elemento da classe
* Atributo chave é um sinônimo da propriedade enumeravel, isto é, um atributo pelo qual voce identifica um elemento da classe univoquamente.

***

## Relacionamentos e tipos de relacionamentos

* Relacionamentos podem ter atributos.
* Grau de um relacionamento: Quantidade de entidades envolvidas.
  * Ex: Relacionamento "fornece" -> Um fornecedor e1 fornece uma peça t1 a um projeto p1 
  * Pode ser triplo, quadruplo, quintuplo... a cardinalidade é livre. O importante é manter correspondência entre os relacionados. 
* Relacionamentos triplos: Relaciona três entidades **ao mesmo tempo**, isto é, estabeleço que três entidades devem estar relacionadas ao mesmo tempo. Devido a essa restrição, não podemos representar um relacionamento triplo como um relacionamento duplo. Dá pra representar um relacionamento duplo como um relacionamento triplo, mas um dos relacionados vai ficar vazio.
  * É mais simples usar um relacionamento triplo quando ele faz sentido ao invés de usar o relacionamento duplo. Se eu usar o duplo eu teria que garantir, de alguma forma, a correspondencia entre as relações. A correspondência no relacionamento triplo sai de graça.
* Participação de um relacionamento
  * Total: Um relacionamento é total se toda entidade de uma classe deve estar relacionada a outra, se existe uma relação que conecta as duas classes.
    * Ex: TRABALHA-PARA: é uma relação total pois todo empregado trabalha, necessariamente, para uma empresa.
  * Parcial: Não necessariamente toda entidade deve estar relacionada
    * Ex: GERENCIA: não é necessario que toda entidade de uma classe gerencie uma entidade de outra classe
* Atributo derivado: um atributo obtido derivado de outros dados na sua base
  * Ex: NUMERO_DE_ALUNOS: é só contar a quantidade de vinculos entre uma disciplina e os alunos. Para não fazer essa conta o tempo todo, armazena-se a quantidade no atributo derivado. toda vez que aumenta um aluno, incrementa-se o atributo derivado.
* Notação do DER (Diagrama Entidade-Relacionamento)

***

# Modelo de dados relacional

* É definido por relações 

* Cada atributo possui um domínio (valores que ele pode assumir).

* Instância de uma Relação (R): Descrição de como será uma relaçao

  * Ex: ESTUDANTE(Nome, média, telefone)

* Uma instância de uma relação(r) é um conjunto de tuplas (ou, de forma mais simples, uma tabela com diversas linhas).

  * A tupla é uma lista ordenada de valores, onde cada valor é um elemento do domínio.

  * Ex de instância

    

    | ESTUDANTE | Nome    | Média | Telefone  |
    | --------- | ------- | ----- | --------- |
    | Tuplas    | Caio    | 6     | 123123123 |
    |           | Joaquim | 9     | 1516791   |
    |           | Maria   | 8     | 98237193  |

    

* O R seria a primeira linha da tablea (o esquema da relação). Todas as outras linhas são instâncias.
* No modelo lógico, temos classes. No modelo relacional (que é um modelo físico), as classes viram relações.

