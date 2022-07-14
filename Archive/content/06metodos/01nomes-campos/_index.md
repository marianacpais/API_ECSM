+++
title = "Nomes dos Campos"
description = ""
weight = 1
+++

## <a name='ExportaodeListacomosNomesdosCampos'></a>Exportação de Lista com os Nomes dos Campos

**Designação**

*Export List of Export Field Names* (isto é, das variáveis utilizadas durante as exportações/importações).

**Descrição**

Este método retorna uma lista dos nomes de todos (ou de apenas um, se necessário) os campos de um projeto, na sua versão específica de exportação/importação.

A lista retornada contém os 3 seguintes atributos para cada um dos campos/escolhas:

- `original_field_name` 
- `choice_value` - representa o valor do código (*raw*) para uma escolha de *checkbox*; para campos que não *checkboxes* este atributo estará vazio.
- `export_field_name` - representa o nome do campo na sua versão específica de importação/exportação

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `content` - `exportFieldNames`

  - `format` - `csv`, `json`, `xml` [default]

- **Opcionais**

  - `field` - o nome da variável de um campo. Por defeito são exportados os nomes de todos os campos mas, se o campo for especificado, pode ser exportado o nome apenas desse campo. Se o nome especificado for inválido, é retornado um erro.

  - `returnFormat` - `csv`, `json`, `xml` - especifica o formato das mensagens de erro. Se não for especificado o formato selecionado será o mesmo do parâmetro `format`, que por defeito é 'xml'. A lista retornada conterá o nome original do campo (variável) e também o nome de exportação do mesmo.

**Resposta**

Retorna uma lista de nomes de campos na sua versão específica de exportação/importação para todos (ou apenas um) dos campos de um projeto utilizando o formato especificado e de acordo com a ordem dos campos.

A lista retornada contém os 3 seguintes atributos para cada um dos campos/escolhas:

- `original_field_name` 
- `choice_value` - representa o valor do código (*raw*) para uma escolha de *checkbox*; para campos que não *checkboxes* este atributo estará vazio.
- `export_field_name` - representa o nome do campo na sua versão específica de importação/exportação