# Modelo Relacional

* Modelo bem simples e formal
* Toda relação possui um **esquema**: o esquema define basicamente quantos atributos (colunas) a relação vai ter
  * MAis formalmente, um esquema é uma sequência do tipo R(A1, A2, ..., An), onde cada A é um atributo da relação
  * Cada atributo possui um **domínio**: é o valor que cada coluna *pode* assumir.
  * A quantidade de atributos de uma relação define o grau de uma relação.
* Definido o esquema, podemos criar **instâncias** dessa relação (ou, mais simplesmente, podemos chama-las de relações). Essas relações são formalmente definidas como r(t1, t2, ..., tn), sendo cada t uma uma linha da tabela, também conhecida como **Tupla**
* Podemos fazer consultas sobre o valor de certos atributos em uma tubla t. Usa-se a seguinte notação para tal
  * t[Nome, idade, Curso] = <'Caio', 21, 'bcc'>.

### Atributos chaves de uma relação: como identificar unicamente uma tabela?

* Como diferenciamos pessoas? O pensamento mais óbvio é definir uma pessoa pelo nome, mas duas pessoas podem ter o mesmo nome, certo? Então ok, digamos que você tenha dois amigos chamados "João Pedro da Silva", como você os diferencia? Você pode identifica-lo por onde ele mora e o nome da mãe, por exemplo. "Qual João? Aquele que mora no butantã, filho da claudia". Isso já deve ser o bastante pra identificar unicamente.

* Esses atributos usados pra identificar unicamente um individuo são chamados de **Super chave**.

* Se a gente adicionar qualquer coisa a mais pra uma super chave, ainda conseguimos usar pra identificar o João. A gente pode até falar qual o prato favorito dele em adicional e ja funciona.

* Se tomarmos o menor número de atributos que identificam o indivíduo, temos uma **chave**.

* Agora digamos que temos dois numeros que podem identificar unicamente o JOão: RG e CPF. Esses dois atributos sozinhos ja são chaves. Como tenho mais de uma chave possivel, cada um desses é uma **chave candidata**. A chave que for escolhida pra ser usada na minha base de dados é a **Chave primaria da relação**

* Mais formalmente: Se chamarmos a Super Chave de SC, então vale para duas tuplas quaisqueres que
  $$
  t_i[SC] \neq t_j[SC], \forall i,j
  $$

* 

* Além disso, a chave não pode ser nula (até porque esse valor não é unico). Essa é a **restrição de integridade**.

### Como relacionar duas tabelas

* Ok, você agora consegue identificar unicamente uma pessoa. Mas digamos que o João trabalhe num departamento e ele é uma tupla da tabela de empregados. Como representamos nos dados que João trabalha no departamento nº4? Parece ser muito simples: 

**EMPREGADOS**

| Nome    | N Departamento | ID   |
| ------- | -------------- | ---- |
| João    | 4              | 123  |
| Caio    | 1              | 456  |
| Claudio | 4              | 789  |

**DEPARTAMENTOS**

| Numero | Função           |
| ------ | ---------------- |
| 4      | Embalar remessas |
| 1      | Enviar remessas  |

Nesse caso podemos observar que João trabalha no departamento 4 e que essa relação ẽ N:1 (N funcionarios podem trabalhar em um departamento). Além disso, note que o número do departamento é uma chave primária (o que faz sentido, já que não conseguiriamos relacionar empregados com departamentos se não conseguissemos identificar unicamente um departamento).

* Esses atributos que referenciam a chave primária de outra tabela são chamados de **Chave estrangeira**

* Como definimos uma chave estrangeira? Bem, uma chave estrangeira é uma ligação entre duas tabelas, certo? Uma referencia. Para conseguir fazer essa relação, precisamos de duas coisas

  1) Ser possível conectar as duas tabelas

  2) Conseguir identificar unicamente o destino da ligação

* Assim, podemos reformular nossa definição fazendo o seguinte: 
  * Uma chave estrangeira que relaciona r1 com r2 é um atributo ou conjunto de atributos (CE) de r1 com domínio identico a chave primária de r2 (nesse caso, CE = N departamento e o domínio são os Naturais)
* Feito isso, está estabelecido o link entre as tabelas.
* Mas agora tem um ponto: e se eu uso o N departamento do João para alguma operação, e, por acidente, exclui-se a tabela de departamentos do banco. Isso pode acontecer?
* Não, não pode. **Enquanto existe uma ligação entre duas tabelas, elas não podem ser deletadas**. Isso é o que chamamos de **Restrição de integridade referencial**.

### Definição final de de uma base de dados relacional

* Uma base de dados é um conjunto de esquemas de relações e um conjunto de restrições de integridade.
* As restrições de integridade são restrição sobre o que o dado pode ser. Ex: o nome de um funcionario não pode se rum numero, o numero de um departamento não pode ser uma string.
* No nosso exemplo, a nossa base de dados relacional é um conjunto de esquemas (esquema do departamento e esquema dos funcionais) e as restrições de integridade

### Retomando

* o modelo relacional é constituido por esquemas de tabelas e suas instancias. As instancias das tabelas possuem linhas (tuplas) e colunas (atributos). Cada tupla deve ser unicamente identificada por uma chave primaria. Cada atributo tem um dominio e pode referenciar outra tabela (chave estrangeira). Os atributos possuem também restrições de integridade. O conjunto de restrições e o conjunto de esquemas definem uma base de dados relacional.