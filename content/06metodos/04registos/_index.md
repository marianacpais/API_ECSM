+++
title = "Registos"
description = ""
weight = 4
+++

##  Exportação de Registos

**Designação**

*Export Records*

**Descrição**

Este método permite a exportação de um conjunto de registos de um projeto.

{{< panel title="Nota sobre privilégios de exportação" style="info" >}}
Importa referir que as permissões de exportação de dados se irão aplicar a esta operação. Isto é, se um utilizador não tiver permissão de exportação para o projeto (*"No Access"*), não ocorrerá exportação de dados pela API e será retornada uma mensagem de erro. Se o utilizador tiver permissões de exportação do tipo *"De-identified"* ou *"Remove All Identifier Fields"* alguns dos campos de dados poderão ser removidos e filtrados de acordo com estas configurações.
{{< /panel >}}

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `content` - `record`

  - `format` - `csv`, `json`, `xml` [default], `odm` ('odm' refere-se ao formato CDISC ODM XML, especificamente ao ODM versão 1.3.1)

  - `type`

    - `flat` - retorna um registo por linha [default]
    - `eav` - retorna um elemento de dados (*data point*) por linha. Assim, cada linha terá o "record ID", o "field_name" e o respetivo valor.
    
- **Opcionais**

  - `records` - um *array* de nomes de registos a especificar os que se pretende requerer (por defeito, todos os registos são exportados)

  - `fields` - um *array* de nomes de campos a especificar os que se pretende requerer (por defeito todos são exportados)

  - `forms` - um *array* de nomes de instrumentos em relação aos quais se pretende requerer os registos. Se o nome do instrumento tiver um espaço, este deve ser substituido por sum *underscore* (por defeito todos os registos são exportados)

  - `rawOrLabel` - `raw` [default], `label` - exporta ou os valores *raw* das variáveis codificadas ou as etiquetas (*labels*) das opções dos campos de escolha múltipla.

  - `rawOrLabelHeaders` - `raw` [default], `label` - (apenas para os formatos 'csv' e tipo 'flat') para os cabeçalhos de CSV, exporta os nomes das variáveis/campos (`raw`) ou as etiquetas dos campos (`label`)

  - `exportCheckboxLabel` - `true`, `false` [default] - especifica o formato dos valores de campos de *checkboxes* especificamente quando se exporta os dados como "labels" (insto é, quando `rawOrLabel`=`label`) no formato "flat" (isto é, quando `type`=`flat`). Quando se exportam "labels", por defeito todas as *checkboxes* terão ou o valor "Checked", se selecionadas, ou "Unchecked", se não selecionadas. No entanto, se `exportCheckboxLabel` for `true` o valor da *checkbox* na exportação corresponderá à etiqueta (*label*) se selecionada e estará vazia no caso de não ser selecionada. Se `rawOrLabel`=`false` ou se `type`=`eav` então `exportCheckboxLabel`será ignorado.

  - `returnFormat` - `csv`, `json`, `xml` - especifica o formato das mensagens de erro. Se não for especificado o formato selecionado será o mesmo do parâmetro `format`, que por defeito é 'xml'. A lista retornada conterá o nome original do campo (variável) e também o nome de exportação do mesmo.

  - `filterLogic` - *string* que define um filtro lógico (exemplo: [idade] > 30) para a filtragem dos dados que serão retornados pela API, em que esta apenas retornará os registos em que avaliação desta expressão seja `TRUE`. Este parâmetro permanece em branco por defeito. No caso de sintaxe errada na expressão inserida a API retorna uma mensagem de erro.

  - `dateRangeBegin` - retorna apenas os registos criados ou modificados após uma determinada data/hora, providenciado um *timestamp* no formato YYYY-MM-DD HH:MM:SS. Se não especificado não assume nenhum tempo de início.

  - `dateRangeEnd` - retorna apenas os registos criados ou modificados antes de uma determinada data/hora, providenciado um *timestamp* no formato YYYY-MM-DD HH:MM:SS. Se não especificado utiliza a data/hora atuais do servidor.

  - `csvDelimiter` - define o caracter delimitador utilizado para separar os valores num ficheiro de dados CSV (apenas para o formato CSV). As opções incluem: vírgula ',' [default], tabulação, ponto-e-vírgula ';', barra vertical (*pipe*) '|' ou sinal de chamada '^'. O caracter deve ser providênciado entre aspas.
 
  - `decimalCharacter` - se especificado, força todos os númerosque contenham parte decimal a ter o mesmo caracter decimal, o que será aplicado a todos os campos calculados e de texto com validação numérica. As opções incluem vírgula ',' ou ponto '.', mas quando este parâmetro é deixado em branco a exportação ocorre com a formatação decimal nativa.

  - `exportBlankForGrayFormStatus` - `true`, `false` [default] - especifica se é ou não exportado um valor para os campos de *status* de completitude de um instrumento (que apresentam um icon cinzento na interface *web*). Estes instrumentos podem ser exportados ou com um valor em branco para este campo ou com o valor "0" para "Incompleto". Recomenda-se a exportação de valores em branco se esta exportação tem como objetivo a re-importação.

**Resposta**

Retorna os dados de um projeto no formato e tipo especificados e ordenados pelo registo (chave primária do projeto).

**EAV XML:**

{{< code lang="xml" >}}<?xml version="1.0" encoding="UTF-8" ?>
<records>
    <item>
        <record></record>
        <field_name></field_name>
        <value></value>
        <redcap_event_name></redcap_event_name>
    </item>
</records>{{< /code >}}

**Flat XML:**

{{< code lang="xml" >}}<?xml version="1.0" encoding="UTF-8" ?>
<records>
    <item>
    cada "data point" como um elemento
    ...
    </item>
</records>{{< /code >}}

##  Importação de Registos

**Designação**

*Import Records*

**Descrição**

Este método permite a importação de um conjunto de registos para um projeto.

**URL**

    https://<URL_base>/api/

**Métodos de Chamada Compatíveis**

`POST`

**Parâmetros (sensível à capitulação)**

- **Obrigatórios**

  - `token` - Chave de API específica de um determinado  utilizador e projeto/grupo de variáveis (ver ["Esquema Geral da Estrutura de Dados"](../../05esquema-dados/)).

  - `content` - `record`

  - `format` - `csv`, `json`, `xml` [default], `odm` ('odm' refere-se ao formato CDISC ODM XML, especificamente ao ODM versão 1.3.1)

  - `type`

    - `flat` - retorna um registo por linha [default]
    - `eav` - retorna um elemento de dados (*data point*) por linha. Assim, cada linha terá o "record ID", o "field_name" e o respetivo valor.

  - `overwriteBehavior`

    - `normal` - os valores em branco/omissos são ignorados [default]
    - `overwrite` - os valores em branco/omissos são validos e reescritos sobre dados existentes

- `data` - dados formatados para serem importados.

**EAV XML:**

{{< code lang="xml" >}}<?xml version="1.0" encoding="UTF-8" ?>
<records>
    <item>
        <record></record>
        <field_name></field_name>
        <value></value>
        <redcap_event_name></redcap_event_name>
    </item>
</records>{{< /code >}}

**Flat XML:**

{{< code lang="xml" >}}<?xml version="1.0" encoding="UTF-8" ?>
<records>
    <item>
    cada "data point" como um elemento
    ...
    </item>
</records>{{< /code >}}

- **Opcionais:**

  - `dateFormat` - `MDY`, `DMY`, `YMD` [default] - especifica o formato dos valores de datas a serem importadas em campos de data ou data-tempo (M corresponde a mês, D a dia e Y a ano). Nota: o valor por defeito é YMD, que deve ser formatado com hífens (isto é, Y-M-D), enquanto que os formatos MDY e DMY desem ser sempre formatados com barras (isto é, M/D/Y ou D/M/Y respetivamente).

  - `csvDelimiter` - define o caracter delimitador utilizado para separar os valores num ficheiro de dados CSV (apenas para o formato CSV). As opções incluem: vírgula ',' [default], tabulação, ponto-e-vírgula ';', barra vertical (*pipe*) '|' ou sinal de chamada '^'. O caracter deve ser providênciado entre aspas.

  - `returnContent` - define a informação que é retornada: `count` [default] - retorna o número de registos inseridos e `id` retorna o uma lista com todos os `record_id` dos registos inseridos.

  - `returnFormat` - `csv`, `json`, `xml` - especifica o formato das mensagens de erro. Se não for especificado o formato selecionado será o mesmo do parâmetro `format`, que por defeito é 'xml'. A lista retornada conterá o nome original do campo (variável) e também o nome de exportação do mesmo.

**Resposta**

Retorna o conteúdo especificado em `returnContent`: o número de registos inseridos ou uma lista com todos os `record_id` dos registos inseridos.