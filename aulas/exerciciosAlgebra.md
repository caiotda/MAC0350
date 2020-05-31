# Exemplos de consulta



**Consulta 2**: 

Para todo projeto localizado em 'Stafford', listar o número do projeto, o número do departamento responsável, e o sobrenome, endereço e data de nascimento do gerente responsável pelo departamento.
$$
DEPARTAMENTO\_STAFFORD \leftarrow \sigma_{DLOCALIZACAO = ' Stafford'}(LOCAIS\_DEPTO)\\
N\_DEP\_STAFFORD = \Pi_{DNOME}(DEPARTAMENTO\_STANFORD) \\
GERENTES = EMPREGADO [X]_{NSS = GERNSS} DEPARTAMENTO \\
GERENTES\_STAFFORD = GERENTES \ (div) \ N\_DEP\_STAFFORD
$$
