# Modelando um Banco de Dados para Oficina

## Objetivo

Criar o esquema conceitual para o contexto de oficina com base na narrativa fornecida.

## Narrativa

- Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica;
- Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas;
- Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega;
- A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra;
- O valor de cada peça também irá compor a OS, cliente autoriza a execução dos serviços;
- A mesma equipe avalia e executa os serviços;
- Os mecânicos possuem código, nome, endereço e especialidade;
- Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

## Diagrama EER

![diagrama](https://github.com/devcaiada/oficina-db-EER/blob/main/assets/Oficina%20DB.png?raw=true)

## Destrinchando o projeto

Com base na narrativa fornecida, podemos identificar as seguintes entidades e seus relacionamentos:

1. **Entidades**:

- Cliente: Representa os clientes que levam seus veículos à oficina.
- Veículo: Representa os veículos que precisam de reparos ou revisões.
- Equipe de Mecânicos: Representa as equipes de mecânicos responsáveis pelos serviços.
- Mecânico: Representa os próprios mecânicos.
- Ordem de Serviço (OS): Representa cada ordem de serviço emitida para um veículo.
- Peça: Representa as peças utilizadas nos serviços.
- Tabela de Referência de Mão-de-Obra: Representa a tabela usada para calcular o valor dos serviços.

2. **Relacionamentos**:

- Cliente → Veículo: Relação de propriedade, pois um cliente possui um ou mais veículos.
- Veículo → Equipe de Mecânicos: Relação de atribuição, pois cada veículo é designado a uma equipe de mecânicos.
- Equipe de Mecânicos → Mecânico: Relação de composição, pois uma equipe é composta por vários mecânicos.
- Ordem de Serviço → Veículo: Relação de atribuição, pois cada OS está associada a um veículo.
- Ordem de Serviço → Peça: Relação de uso, pois uma OS inclui várias peças.
- Cliente → Ordem de Serviço: Relação de autorização, pois o cliente autoriza a execução dos serviços.
- Equipe de Mecânicos → Ordem de Serviço: Relação de execução, pois a mesma equipe avalia e executa os serviços.
- Mecânico → Tabela de Referência de Mão-de-Obra: Relação de consulta, pois o mecânico consulta a tabela para calcular o valor dos serviços.

3. **Atributos**:

- Cliente: código, nome, endereço.
- Veículo: n°, data de entrega.
- Mecânico: código, nome, endereço, especialidade.
- Ordem de Serviço: n°, data de emissão, valor, status, data para conclusão.
- Peça: código, descrição, valor.
- Tabela de Referência de Mão-de-Obra: código, descrição, valor.
