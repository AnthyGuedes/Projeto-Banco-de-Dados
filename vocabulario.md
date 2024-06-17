AVALIAÇÃO FINAL:

1)
SGBD - Software responsavel pelo gerenciamento e controle de um ou mais banco de dados, um exemplo seria o MySql.

RESTRIÇÕES - São regras que o Mecanismo de Banco de Dados do SQL Server. Um exemplo seria a restrição UNIQUE, para que não hava duplicatas, podendo ser aplicado em casos para variaveis como CPF e Email. 

MODELO RACIONAL - Serua um modelo de dados representativo, onde na visão de um Sistema Gerenciador de Banco de Dados se baseia no princípio de dados armazenados em tabelas.

MODELAGEM CONCEITUAL - Utilizada em fases inciais de um Banco de Dados, onde acaba sendo trabalhado e introduzido conceitos da regras de negócio.

MODELAGEM LÓGICA - A modelagem lógica de dados utiliza da estrutura do modelo conceitual e adiciona outras informações para lógica do sistema. Utilizando elementos como entidades, relacionamentos, atributos, e chaves tanto primarias como estrangeiras. 

MODELAGEM FÍSICA - Onde é aplicado em um SGBD, fornecem detalhes para os que possuem controle e e administram o banco de dados, a implementar a lógica de negócios em um banco de dados físico.

LINGUAGEM SQL - Uma linguagem desenvolvida para gerenciar dados  em um sistema de gerenciamento de banco de dados (SGBD).

DDL- DDL ou Data Definition Language, permite que o usuário defina as novas tabelas e os elementos que serão associados. Responsável por comandos de criação e alteração no banco de dados, como CREATE, ALTER e DROP.

DML - DML ou Data Manipulation Language, permire que o usuário faça a inclusão, remoção e modificação de informações em bancos de dados. Alguns de seus comandos são: INSERT, UPDATE e DELETE.

BOAS PRÁTICAS - Tenha um DBA(Database Administrator), cuide da estrutura do seu banco de dados, divida bem o que pode ser feito pela parte do front-end, como opções de selecionar para o usuário, sempre que possível. Invés dele ter que inserir o dado.

2)
# Todos os clientes armazenados no sistema:
select *
from cliente

# Exiba os veículos que tenham final 3 no número da placa
SELECT * 
FROM veiculo 
WHERE placa LIKE '%3';

# Mostre os clientes que residem no RS e que não possuam telefone
select *
from cliente
where cliente.uf_cnh = 'RS' and cliente.telefone IS NULL;

# Exiba o código dos clientes que alugaram veículos por mais de 90 dias.
SELECT id_cliente 
FROM contrato_aluguel 
where duracao > 90;

# Quantos veículos há cadastrados no sistema
select * 
from veiculo;

# Mostre o veículo alugado por Alexandre Zamberlan.
select * 
from veiculo
join contrato_aluguel ON veiculo.id_veiculo = contrato_aluguel.id_veiculo
join cliente ON contrato_aluguel.id_cliente = cliente.id_cliente
where cliente.nome = 'Alexandre Zamberlan';

# Mostre os clientes e os escritórios associados no contrato de aluguel.
