+++
title = "Esquema Geral da Estrutura de Dados"
description = ""
weight = 5
+++

Os dados do **Repositório de Dados para Investigação das Equipa Comunitária de Saúde Mental** encontram-se organizados em 3 grandes grupos (corresponentes a "projetos" na hierarquia utilizada pelo REDCap).

Cada um destes projetos encontra-se ainda divido em "instrumentos", que são, no fundo, formulários de introdução de dados. Estes formam "sub-grupos" de variáveis, e estão organizados como se descreve na coluna "Instrumento" das tabelas das próximas secções.

Para efetuar operações de leitura ou escrita relativos a cada um destes grupos, é necessário utilizar uma chave de API ("token") diferente, ainda que esta operação possa ser efetuada pelo mesmo utilizador.

As variáveis e respetiva caracterização pertecentes a cada um destes grupos encontram-se descritas nas secções que se seguem:

- [Tabela "Utentes"](/05esquema-dados/01utentes)
  - Acesso utilizando a **chave de API "Utentes"**
  - Nome do projeto no REDCap: ECSM_Utentes
  - Inclui as variáveis correspondentes a cada um dos utentes (cada registo corresponde a um conjunto de dados relativo a um único utente)
- [Tabela "Equipas"](/05esquema-dados/02equipas/)
  - Acesso utilizando a **chave de API "Equipas"**
  - Nome do projeto no REDCap: ECSM_Equipa
  - Inclui as variáveis correspondentes a cada uma das Equipa Comunitária de Saúde Mental (cada registo corresponde a um conjunto de dados relativos a utentes, profissionais e atividades desenvolvidas por uma equipa de forma agregada)
- [Tabela "Inquérito aos Profissionais"](/05esquema-dados/03inquerito/)
  - Acesso utilizando a **chave de API "Inquérito"**
  - Nome do projeto no REDCap: ECSM_Inquérito Profissionais
  - Inclui as variáveis que contém os resultados do Inquérito aos Profissionais (cada registo corresponde a um inquérito a um determinado profissional)



