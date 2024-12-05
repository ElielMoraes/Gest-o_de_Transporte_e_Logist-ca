GESTÃO DE TRANSPORTE E LOGÍSTICA
Este projeto consiste na criação e população de um banco de dados voltado para a gestão de transporte e logística. O objetivo principal é gerenciar informações relacionadas a motoristas, veículos, rotas, viagens, clientes e entregas de forma integrada e consistente.

ESTRUTURA DO BANCO DE DADOS
O banco de dados é composto pelas seguintes tabelas:

- MOTORISTAS: Armazena informações dos motoristas, como nome, CNH e telefone.
- VEICULOS: Contém dados dos veículos, incluindo placa, modelo, capacidade de carga e status.
- ROTAS: Registra as rotas disponíveis, com origem, destino e distância.
- VIAGENS: Gerencia as viagens realizadas, associando veículos, motoristas e rotas, além de registrar datas de partida e chegada e o status da viagem.
- CLIENTES: Guarda informações dos clientes, como nome, telefone, e-mail e endereço.
- ENTREGAS: Relaciona viagens com clientes, indicando o endereço de entrega e o status.


RELACIONAMENTOS ENTRE TABELAS

A tabela VIAGENS se relaciona com:
- MOTORISTAS (via MOTORISTA_ID)
- VEICULOS (via VEICULO_ID)
- ROTAS (via ROTA_ID)

A tabela ENTREGAS se relaciona com:
- VIAGENS (via VIAGEM_ID)
- CLIENTES (via CLIENTE_ID)

Esses relacionamentos garantem que todas as informações sejam consistentes, permitindo rastrear desde o motorista e veículo utilizados até o cliente e o status da entrega.

OBJETIVO DO BANCO DE DADOS

O objetivo do banco de dados é fornecer uma solução eficiente para gerenciar os processos logísticos, permitindo:

- Cadastrar e consultar motoristas, veículos e clientes.
- Planejar rotas e viagens.
- Registrar entregas realizadas e acompanhar o status.
- Obter informações detalhadas e rastreáveis sobre cada operação logística.


COMO XECUTAR OS SCRIPTS

Pré-requisitos

- Acesso a um ambiente Oracle Database (ex.: Oracle Live SQL, SQL Developer ou SQL*Plus).
- Permissão para criar usuários e tabelas.

Passos para execução

- Criação do Usuário
- Execute o seguinte script para criar o usuário e conceder os privilégios necessários:

CREATE USER USR_LOGISTICA IDENTIFIED BY 1234;
GRANT CONNECT, RESOURCE TO USR_LOGISTICA;
GRANT UNLIMITED TABLESPACE TO USR_LOGISTICA;
ALTER SESSION SET CURRENT_SCHEMA = USR_LOGISTICA;


CRIAÇÃO DAS TABELAS E RELACIONAMENTOS
Execute o script de criação das tabelas e definições de chaves, garantindo que todas as tabelas sejam criadas corretamente com o usuário USR_LOGISTICA.

CRIAÇÃO DE SEQUENCES E INSERÇÃO DE DADOS
Execute o script de criação de sequences para os IDs e, em seguida, o script de inserção de dados para popular o banco com exemplos consistentes.

CONSULTANDO OS DADOS
Use os comandos SELECT fornecidos para consultar as tabelas e validar os dados:

SELECT * FROM USR_LOGISTICA.MOTORISTAS;
SELECT * FROM USR_LOGISTICA.VEICULOS;
SELECT * FROM USR_LOGISTICA.ROTAS;
SELECT * FROM USR_LOGISTICA.VIAGENS;
SELECT * FROM USR_LOGISTICA.CLIENTES;
SELECT * FROM USR_LOGISTICA.ENTREGAS;
