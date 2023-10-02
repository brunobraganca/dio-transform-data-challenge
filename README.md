# dio-transform-data-challenge

## Desafio "Processando e Transformando Dados com Power BI", do módulo 5 do curso de Ciência de Dados do Bootcamp Santander.

**Correções nos scripts para criação dos bancos:**
- alter table departament drop constraint departament_ibfk_1; -> solicitação de drop para constraint que ainda não existe;
- alter table dept_locations drop fk_dept_locations; -> faltou escrever "constraint" depois de drop;
- drop table dependent; -> aparece antes da table existir, não vai surtir efeito;
- use company_constraint; -> o nome certo é azure_company;

**Correções interpretativas:**
- james -> foi necessário colocar um ssn pra ele
remoção da constraint fk_employee antes de popular a tabela
adição da constraint fk_employee;

**Correções ao longo da transformação dos dados:**
(todas foram feitas via PowerBI)
- Separação da coluna de endereço de employee. À delimitador à esquerda para o número, e à direita para o estado.;
- Exclusão da coluna minit;
- Existe um projeto com zero horas de trabalho para um funcionário - **888665555** trabalha 0 horas no **projeto 20**, enquanto seus colegas de projeto estão com até 20 horas de trabalho. Ou a pessoa encontra-se em uma condição especial, tendo terminado as suas tarefas, ou existe um desequilíbrio na distribuição de tarefas.;
- Ao criar a consulta de departamento na tabela de employee, a coluna dnum fica sem funcionalidade, por isso, foi excluída.;
- Ao combinar as consultas e mesclar departament com dept_locations, foi necessária a readequadação das colunas, para evitar dados retoralimentados (dept_locations em departament e vice-e-versa) e dados repetidos (Dnumber). A coluna do departamento com a localização se chama - DeptCell
- A mesclagem dos nomes dos departamentos com as suas localizações se faz necessária por existem mais de uma localidade por departamento e também mais de um departamento para algumas localidades. Isso é necesário para a construção do modelo de estrela pois, para haver relevância, é necessário comparar a produtividade de cada célula de departamento em diferentes localidades.
