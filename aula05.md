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