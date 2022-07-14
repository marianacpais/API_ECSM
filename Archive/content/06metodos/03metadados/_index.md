+++
title = "Metadados"
description = ""
weight = 3
+++

##  Exportação de Metadados ("Data Dictionary")

**Designação**

*Export Metadata (Data Dictionary)*

**Descrição**

Este método permite a exportação dos metadados de um projeto.

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `content` - `metadata`

  - `format` - `csv`, `json`, `xml` [default]

- **Opcionais**

  - `fields` - *array* de nomes de campos especificando os campos que se pretende requerer (por defeito, todos os metadados são exportados)

  - `forms` - *array* de nomes que especificam os instrumentos de recolha de dados em relação aos quais se pretende requerer os metadados (por defeito, todos os metadados são exportados). Importa ressalvar que estes nomes de "forms" não correspondem aos valores mostrados nas insterfaces *web* mas sim aos nomes únicos disponíveis na segunda coluna (B) do *Data Dictionary*.

  - `returnFormat` - csv, json, xml - especifica o formato das mensagens de erro. Se não for especificado as mensagens surgirão de acordo com o formato especificado em `format` ('xml' por defeito)

**Resposta**

Retorna os metadados de um projeto (isto é, os valores do *Data Dictionary* no formato especificado e pela ordem em que os campos surgem.