+++
title = "Códigos de Erro e Respostas da API"
description = ""
weight = 3
+++

## Códigos de Estado (status codes) HTTP

As chamadas à API são acompanhadas pelo retorno de códigos de estado HTTP apropriados. No que se segue apresentamos uma lista de códigos HTTP possíveis e o seu significado:

{{< panel title="Status Codes" style="primary" >}}
        200 OK: Success!

        400 Bad Request: The request was invalid. An accompanying message will explain why.

        401 Unauthorized: API token was missing or incorrect.

        403 Forbidden: You do not have permissions to use the API.

        404 Not Found: The URI you requested is invalid or the resource does not exist.

        406 Not Acceptable: The data being imported was formatted incorrectly.

        500 Internal Server Error: The server encountered an error processing your request.

        501 Not Implemented: The requested method is not implemented.
{{< /panel >}}

## Mensagens de Erro

Quando a API retorna uma mensagem de erro, esta surge no formato especificado na chamada à API (ou no formato definido por defeito, no caso de nenhum formato ter sido especificado).

Para efetuar a especificação do formato deve ser utilizado o parâmetro `returnFormat` para cada método explicitado na secção ["Métodos Suportados"](../06metodos/).

Apresentamos um exemplo para um código de erro no formato XML:

{{< code lang="xml" >}}<?xml version="1.0" encoding="UTF-8" ?>
<hash>
    <error>detailed error message</error>
</hash>
{{< /code >}}


