+++
title = "Instrumentos"
description = ""
weight = 2
+++

## Exportação de Instrumentos (Formulários de Introdução de Dados)

**Designação**

*Export Instruments (Data Entry Forms)*

**Descrição**

Este método permite a exportação de uma lista de instrumentos de recolha de dados de um determinado projeto. O termo "instrumento", utilizado pela plataforma REDCap, refere-se, de uma forma geral, a um "formulário de introdução de dados". Assim, corresponde a "sub-grupos" de variáveis existentes em cada "projeto", tal como se pode perceber em maior detalhe na secção ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

A informação retornada inclui o nome único do instrumento e cada uma das etiquetas de variáveis correspondentes. Os instrumentos são enumerados na resposta pela ordem em que se encontram no projeto.

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `format` - `csv`, `json`, `xml` [default]

**Resposta**

Retorna os instrumentos de um projeto no formato especificado e pela ordem pela qual surgem no projeto.

##  Exportação de Ficheiro PDF dos Instrumentos

**Designação**

*Export PDF file of Data Collection Instruments* (quer em branco quer com dados)

**Descrição**

Este método permite a exportação de um ficheiro PDF para qualquer das seguintes situações:

1) Um único instrumento de recolha de dados (em branco)
2) Todos os instrumentos (em branco)
3) Um único instrumento (com os dados de um único registo)
4) Todos os instrumentos (com os dados de um único registo)
5) Todos os instrumentos (com os dados de todos os registos)

> NOTA: os privilégios de acesso de cada utilizador aplicam-se também aos dados exportados através destes PDFs. Assim, por exemplo os utilizadores que tenham privilégios de exportação de dados desidentificados irão ver alguns dos dados omissos nos campos do PDF e os utilizadores que não possuam permissão de exportação irão receber uma mensagem de erro.

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `content` - `pdf`

- **Opcionais**

  - `record` - o ID do registo (*record ID**). Por defeito, este valor está em branco e mesmo assim irá retornar um PDF em branco (isto é, sem dados). Se o ID de registo for especificado, irá retornar um instrumento/todos os instrumentos com os dados de apenas aquele registo.

  - `instrument` - nome único de um instrumento (corresponde à segunda coluna do *Data Dictionary*). Este valor encontra-se em branco por defeito, o que retorna todos os instrumentos. Se o `record`não estiver em branco e o `instrument` estiver em branco, retorna todos os instrumentos populados com dados desse determinado registo.

  - `allRecords` - o valor deste parâmetro não importa e é ignorado. Se este parâmetro tiver algum valor, todos os instrumentos serão retornados, populados com dados de todos os registos. Ou seja, se este parâmetro tiver algum valor, os parâmetros `record` e `instrument` são ignorados.
  
  - `compactDisplay` - colocar o valor `TRUE`para obter um PDF com formatação compactada que exclui campos que não tenham dados salvos e exclui escolhas múltiplas não selecionadas. Se atribuido o valor `FALSE`, todos os campos são mostrados normalmente.
  
- `returnFormat` - `csv`, `json`, `xml` [default] - este parâmetro apenas é utilizado em relação ao formato de qualquer mensagem de erro que possa ser retornada.

**Resposta**

Ficheiro PDF que contem todos os instrumentos de recolha de dados de um projeto, em que os instrumentos podem encontrar-se em branco (sem dados), com dados de apenas um registo ou dados de todos os registos do projeto.