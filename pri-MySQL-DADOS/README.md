Sistema de Gerenciamento Hospitalar - Banco de Dados
Visão Geral

Este projeto foca na criação de um banco de dados abrangente para um sistema de gerenciamento hospitalar. O banco de dados inclui informações sobre médicos, pacientes, consultas, especialidades médicas, provedores de seguros e acomodações hospitalares. Os dados abrangem o período de 1 de janeiro de 2015 a 1 de janeiro de 2022.
Estrutura do Banco de Dados
Entidades

    Médicos
        Pelo menos 10 médicos com diferentes especialidades, incluindo pediatria, clínica geral, gastroenterologia e dermatologia.

    Especialidades
        Sete especialidades, incluindo pediatria, clínica geral, gastroenterologia e dermatologia.

    Pacientes
        Pelo menos 15 pacientes.

    Consultas
        Registros de 20 consultas envolvendo diferentes pacientes e médicos. Dez consultas incluem prescrições com dois ou mais medicamentos.

    ProvedoresDeSeguro
        Informações sobre pelo menos quatro provedores de seguros. Associação com pelo menos cinco pacientes e cinco consultas.

    RelacaoMedicoEspecialidade
        Entidade que estabelece a relação entre médicos e suas especialidades.

    Internacoes
        Registros de pelo menos sete internações entre 1 de janeiro de 2015 e 1 de janeiro de 2022. Pelo menos dois pacientes foram internados mais de uma vez.

    Acomodacoes
        Três tipos de acomodações: apartamentos, quartos duplos e enfermarias. Cada um com custos associados diferentes.

    Enfermeiros
        Informações sobre dez profissionais de enfermagem.

    RelacaoInternacaoEnfermeiro
        Entidade que estabelece a relação entre internações e enfermeiros.

Relacionamentos

    Consulta - Relacionamento Médico/Paciente
        Chaves estrangeiras vinculando consultas a ambos médicos e pacientes.

    ProvedorDeSeguro - Relacionamento Médico
        Chaves estrangeiras corrigidas estabelecendo a relação entre provedores de seguros e médicos.

    Internacao - Relacionamento Paciente/Médico
        Chaves estrangeiras vinculando internações a ambos pacientes e médicos.

População de Dados

O banco de dados foi preenchido com dados realistas para simular a operação de um sistema de gerenciamento hospitalar. Os dados abrangem uma variedade de cenários, incluindo múltiplas consultas para alguns pacientes, diferentes tipos de acomodações e hospitalizações repetidas.
Como Utilizar

Para implementar este banco de dados, siga estes passos:

    Criação do Banco de Dados
        Execute os scripts SQL fornecidos na pasta 'sql_scripts' na ordem especificada.

    População de Dados








Parte 2:

Pensando no banco que já foi criado para o Projeto do Hospital, realize algumas alterações nas tabelas e nos dados usando comandos de atualização e exclusão:

Crie um script que adicione uma coluna “em_atividade” para os médicos, indicando se ele ainda está atuando no hospital ou não.

Crie um script para atualizar ao menos dois médicos como inativos e os demais em atividade.

comandos:

ALTER TABLE medicos ADD COLUMN em_atividade VARCHAR(4);

select * from medicos;

UPDATE medicos SET em_atividade = 'sim' where null;

UPDATE medicos SET em_atividade = 'não' where id_medicos = '7' and '9'






Parte 3:
SELECT AVG(valor_consulta) AS media_consultas FROM hospital WHERE YEAR(data_consulta) = 2020 OR convenio_consulta = 'Sim';

SELECT * FROM hospital WHERE data_alta_internacao < prevista_alta_internacao;

SELECT * FROM hospital WHERE id_consulta = (SELECT MIN(id_consulta) FROM hospital);

SELECT * FROM hospital WHERE convenio_consulta = 'Não' ORDER BY valor_consulta DESC LIMIT 1;

SELECT * FROM hospital WHERE convenio_consulta = 'Não' ORDER BY valor_consulta ASC LIMIT 1;

SELECT data_entrada_internacao, procedimento_internacao, id_quarto FROM hospital WHERE tipo_quarto = 'Apartamento';

SELECT nome_paciente, nome_medico, data_entrada_internacao, procedimento_internacao FROM hospital WHERE especialidade_medico = 'Gastroenterologia'

    
        Execute os scripts SQL para população de dados na pasta 'data_population'.

    Consultas e Relatórios
        Utilize as consultas SQL fornecidas na pasta 'queries' para diversos relatórios e análises.
