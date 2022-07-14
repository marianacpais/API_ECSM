+++
title = "Tabela 'Equipas'"
description = ""
weight = 2
+++

A tabela que se segue descreve as variáveis constantes no projeto/grupo "Equipas". Este, inclui os seguintes instrumentos/"sub-grupos" de variáveis:

- Monitorização utentes e consultas
- Elementos administrativos

Para efetuar operações relativas a este grupo o utilizador precisa de utilizar a **chave de API "Equipas"**.

{{< table style="table-hover" >}}
|     Instrumento                              |     Nome da Variável                             |     Descrição                                                                                                                                                                                          |     Tipo de Dados     |     Codificação/ Validação    |
|--------------------------------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|------------------------------|
|     Monitorização utentes e   consultas    |     **numero_utentes_seguidos**                      |     Numero utentes seguidos     Popular em cada semestre com   o numero de utentes seguidos                                                                                                            |     Número inteiro    |     *Obrigatório             |
|     Monitorização utentes e   consultas    |     **numero_novos_utentes**                         |     Numero novos utentes     Popular em cada semestre com   o numero de novos utentes seguidos                                                                                                         |     Número inteiro    |     *Obrigatório             |
|     Monitorização utentes e   consultas    |     **numero_primeiras_consult     as**              |     Numero primeiras consultas realizadas     Popular com numero de primeiras consultas realizadas   em cada semestre     no final do mesmo                                                            |     Número inteiro    |     *Obrigatório             |
|     Monitorização utentes e   consultas    |     **numero_consultas_subsequ     entes**           |     Numero consultas subsequentes realizadas     Popular com numero de consultas subsequentes   realizadas em cada     semestre no final do mesmo                                                      |     Número inteiro    |     *Obrigatório             |
|     Monitorização utentes e   consultas    |     **numero_de_profissionais_     de**              |     Numero de profissionais de saúde por especialidade 1     Contagem a ser populada semestralmente por   especialidade. Replicar     formulário n vezes   necessárias                                 |     Número inteiro    |     *Obrigatório             |
|     Monitorização utentes e   consultas    |     **numero_de_profissionais_     de_2**            |     Horas de exclusividade dedicadas à ECSM por   profissional     de saúde 1     Contagem a ser populada semestralmente por   profissional de saúde.     Replicar formulário n vezes   necessárias    |     Número inteiro    |     *Obrigatório             |
|     Elementos administrativos              |     **despesa_rendas_equipamen     to**              |     Despesa rendas equipamento e mobiliário     Popular no início da entrada   em funcionamento da ECSM                                                                                                |     Número inteiro    |     *Obrigatório             |
|     Elementos administrativos              |     **despesa_transportes**                          |     Despesa aquisicao ou aluguer transportes para     profissionais e mobiliário     Popular no início da entrada   em funcionamento da ECSM                                                           |     Número inteiro    |     *Obrigatório             |
|     Elementos administrativos              |     **numero_profissionais_adm     inistrativos**    |     Numero profissionais administrativos     Popular no início da entrada em funcionamento da ECSM                                                                                                     |     Número inteiro    |     *Obrigatório             |
|     Elementos administrativos              |     **custo_formacao_profissio     nais_saude**      |     Custo de formacao profissionais saude     Popular no início da entrada   em funcionamento da ECSM                                                                                                  |     Número inteiro    |     *Obrigatório             |
|     Elementos administrativos              |     **custo_material_enfermage     m**               |     Custo material de enfermagem adquirido     Popular no início da entrada   em funcionamento da ECSM                                                                                                 |     Número inteiro    |     *Obrigatório             |
{{< /table >}}