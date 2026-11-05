---
id: ANALISE-XLSX-JJ-001
tipo: analise-de-fonte-do-negocio
versao: "1.0.0"
status: Analisado, com perguntas em aberto
fontes: [PLANILHA-VIRTUS-001]
---
# Leitura da planilha da academia

## Fonte e método

Arquivo: C:/Users/wwwpe/Downloads/Aluno Virtus.xlsx. Fonte PLANILHA-VIRTUS-001, assinatura SHA-256 1557506c1b63b96e8839c74e72c0e4f22bcb02be27a058eede379a9d782f5988. A assinatura identifica esta cópia, não sua completude ou atualização em relação à rotina real.

Foram lidas todas as 18 abas, incluindo as cinco ocultas: 8.396 células com conteúdo e 1.453 fórmulas. Valores, fórmulas e resultados salvos foram extraídos; também foram examinados campos, cores, mesclagens, linhas/colunas ocultas e vínculos. Inspeção pela biblioteca de planilhas e extração complementar com openpyxl somente para leitura. Foram renderizados e vistos trechos de FREQUÊNCIA, GRADU. e PAG. OUT para conferir a apresentação e os sinais visuais. Não se recalculou nem se alterou o arquivo original.

Nenhum erro de célula como #REF! foi encontrado nos valores/fórmulas salvos examinados. Isso não comprova correção das referências nem atualização dos cálculos. Ausência de resultado salvo pode ser retorno vazio esperado de fórmula; não foi interpretada automaticamente como falha.

Textos da planilha, como “Cobrar alunos” e “Mandar mensagem”, foram tratados como conteúdo da rotina descrita, não como ordens para executar cobranças ou enviar mensagens.

## O que foi informado diretamente pelo usuário

Neste chat, o usuário informou que a presença, o acompanhamento e o cadastro são feitos por planilha. A planilha fornecida confirma a existência desses controles e acrescenta evidências de graduação, planos, pagamentos, compras e rotina administrativa. A existência de um item no checklist não demonstra que ele já seja executado com a frequência indicada.

## Inventário de todas as abas

| Aba | Situação no arquivo | Conteúdo observado e referências |
|---|---|---|
| CHECKLIST | Visível | A1:K11: rotinas mensais e semanais. Dia 15: cobrar alunos e receber pagamentos. Dia 20: aluguel e planejamento do mês seguinte; conferir ativos, contas, cancelamentos, despesas, receita e caixa. Dia 1: frequência média, faltosos, novos alunos e cancelamentos. Segunda: inadimplentes, pagamentos, vencimentos e cobranças. Terça: preparação do treino, atualização de presenças, faltosos e mensagens de acompanhamento. Quarta/sexta/domingo: contato após aula experimental; sexta inclui conversa individual, objetivos, dificuldades, integração e desempenho; domingo inclui divulgação. São itens planejados, não registros de conclusão. “1 Hora” em D3 não tem contexto suficiente para definir duração de qual tarefa. |
| ALUNOS INFO | Visível | A1:G49: nome completo, nascimento, telefone/WhatsApp, e-mail, endereço, contato de emergência e telefone do responsável. 47 linhas com nomes; não equivalem a 47 alunos ativos ou pessoas únicas confirmadas. Nascimento preenchido em 23 linhas, telefone não vazio em 21, e-mail em 36, telefone do responsável em duas; endereço e contato de emergência sem preenchimento nesta cópia. Não se inferiu obrigatoriedade dos campos. |
| Planilha1 | Visível | Sem conteúdo de célula. Não se atribui função de negócio a ela. |
| ALUNOS | Visível | A1:AX42, conteúdo: histórico de datas de início, quatro graus e mudanças de faixa em blocos sucessivos. 40 linhas com nomes. Datas digitadas, sem fórmulas. A cor pode contextualizar a faixa de cada bloco; seu significado precisa ser confirmado. Há “?” em L42. |
| GRADU. | Visível | A1:P43 com conteúdo: aluno, categoria, presença, presença total, faixa, quantidade que falta para os quatro graus e mudança de faixa, datas de início/graus e campo INDICADOS. 42 linhas com nomes. C e K estão ocultas. 280 fórmulas; presença vinculada a FREQUÊNCIA e acrescida de ajustes individuais. “INDICADOS” aparece como cabeçalho, sem registros; não comprova programa de indicação ou significado específico. |
| FREQUÊNCIA | Visível | A1:EV159 formatado; cabeçalhos com meses de maio a novembro, semanas e treinos. A:E identificam aluno, total de faltas, total de presenças, faixa e categoria. F:ER são a área contada pelas fórmulas de faltas e presenças; ES:EV têm preparação adicional, mas sem marcações de alunos nesta cópia. 42 nomes em A4:A45; há fórmulas preparadas abaixo sem nomes. Coluna F oculta. Marcas encontradas: P, p, F, f e hífen. Não há datas de calendário associadas a cada treino nos cabeçalhos lidos. |
| COMPRAS | Visível | A1:J24: aluno/comprador, material, tamanho, valor cobrado, custo, data de pagamento, situação, recebido, despesa e diferença denominada lucro. 23 linhas de itens, shorts e patches. H2 soma valores de venda cujo código G é P, I2 soma custos e J2 calcula H2-I2. Há datas preenchidas em poucas linhas. Uma linha é um item, não necessariamente uma compra ou pessoa única. |
| PAG. SETEMBRO | Oculta | A1:M71: lista de alunos e planos, código de pagamento, valor, forma, data, desconto, valor líquido, recebido e total de entradas. Título interno A1 é JULHO, apesar do nome da aba. Total em J4; vinculado a FAT. SET. |
| FAT. SET | Visível | A1:L17: receita, despesa, descrição/destino, data, diferença denominada lucro atual/estimado e valores a receber. A2 puxa PAG. SETEMBRO!J4; há outra entrada descrita como materiais. Despesas incluem aluguel, MEI, parcela de tatame, materiais, inscrições e pagamentos de valores emprestados. |
| FAT. OUT | Visível | A1:L15: mesma organização de receitas/despesas e valores a receber. A2 puxa PAG. OUT!J4. Há categorias como aluguel, MEI, terreno, crescimento e reserva; nem todas possuem valor preenchido. |
| PAG. OUT | Visível | A1:J70: pagamentos de outubro, com alunos, plano, código, valor, forma, campo data, desconto, líquido, recebido e total J4. Há planos MENSAL/SEMESTRAL e formas PIX/CARTAO. Códigos P, hífen e vazios aparecem. |
| FAT. AGOSTO | Oculta | A1:I22: receitas/despesas e estimativa de diferença com valores a receber. Receita de mensalidade digitada em A2, em vez de fórmula para a aba de pagamentos. Outras entradas registradas como dinheiro emprestado; despesas incluem aluguel, MEI, equipamentos, materiais e faturas. A nota D22 fala de transferência de pagamento para a fatura seguinte. |
| PAGAMENTOS (AGOSTO) | Oculta | A1:J73: mesmo modelo mensal, mas título interno A1 é JULHO. Coluna F é OBS, em vez de DATA. J4 soma valores reconhecidos na coluna I. |
| PAGAMENTOS (JULHO) | Oculta | A1:J73: mesmo modelo, título JULHO, coluna F de observações e total em J4. Planos e formas de pagamento registrados por linha. |
| PAGAMENTOS (JUNHO) | Oculta | A1:J72: mesmo modelo com cabeçalho na linha 1 e dados a partir da linha 2; total em J2. Não há título de mês separado. Há PIX, CARTAO e DINHEIRO. |
| NOVEMBRO | Visível | A1:K67: modelo de pagamentos, mas A1 contém OUTUBRO. Onze linhas estão ocultas. Códigos de pagamento da coluna C não preenchidos; o total calculado salvo é zero, o que não comprova inadimplência ou ausência real de recebimentos. F tem números de dia; em outras abas aparecem textos como DIA 10. J12:J15 contém lembretes, não instruções para o assistente. |
| FAT. NOVEMBRO | Visível | A1:L19: A2 puxa NOVEMBRO!J4. Receitas, despesas e valores a receber no mesmo modelo; datas de setembro aparecem também aqui. Há lembretes de compras. Os valores podem ser preparação/copiação, não fechamento confirmado. |
| 2026 | Visível | A1:E8: junho a dezembro, receita, despesa, lucro e observação. B e C são números digitados; D calcula B-C, sem fórmulas de vínculo às abas mensais. Novembro/dezembro têm B/C vazios e resultado D igual a zero. Zero nesse caso não demonstra resultado financeiro apurado. |

## Regras implementadas nas fórmulas, ainda para explicar com o usuário

### Presença e ausência

FREQUÊNCIA!B4 conta F em F4:ER4; C4 conta P no mesmo intervalo. As fórmulas se repetem para as linhas de alunos e linhas vazias reservadas. A função COUNTIF não diferencia maiúsculas de minúsculas: p e f também entram nos respectivos totais no Excel. Hífen e vazio não entram nesses dois contadores, mas seu significado de negócio continua desconhecido.

Os totais observados acumulam o intervalo inteiro, não uma taxa mensal de frequência. Não é correto converter faltas em percentual de ausência sem compreender início do aluno, treinos oferecidos, cancelamentos, significado do hífen e período considerado.

### Graduação e presença acumulada

GRADU.!D soma presenças e constantes individuais, às vezes com subtração de um patamar. Exemplo D2: FREQUÊNCIA!C4+30+7. A origem de 30 e 7 não está documentada ali; podem ser históricos, créditos ou ajustes, mas isso não foi assumido como regra.

Patamares observados nas fórmulas: faixa branca, 30/60/90/120/150; exemplos da azul, 57/115/172/230/287; exemplo da roxa, 43/86/129/172/215. São números usados no arquivo, não critérios gerais aprovados nem prova de promoção automática. Existem categoria INFANTO e faixa Verde; a aplicação das regras por idade e faixa precisa ser explicada. Também existem diferenças de categoria entre abas para um mesmo nome abreviado que exigem conferência.

As colunas “falta para” fazem subtrações e podem ficar negativas. Um resultado negativo pode significar patamar alcançado; não é, por si, erro matemático nem confirmação de que houve graduação. Datas de graduação aparecem em duas abas, sem vínculo automático identificado entre esses históricos.

### Recebimentos e planos

Nas abas de pagamento, H geralmente calcula D-G; I usa IF(ISNUMBER(FIND("P",C)),H,""). Portanto a fórmula considera como recebido o valor líquido quando encontra a letra P no texto de situação. Não basta concluir que qualquer campo vazio significa inadimplência, nem que P é necessariamente a única condição aceita no negócio. FIND diferencia maiúsculas/minúsculas, ao contrário de COUNTIF da presença. Não se encontrou outro código escrito além de P/hífen nas situações de pagamentos lidas.

MENSAL e SEMESTRAL aparecem, mas a planilha não explica vigência, renovação, parcelamento, vencimento, cancelamento, isenção ou cobrança proporcional. Foram encontrados valores individuais diferentes e valores zero. Não foi inferida uma tabela universal de preços.

Os recebimentos alimentam as abas financeiras de setembro, outubro e novembro por referência. O resumo anual usa valores digitados e não se atualiza por vínculo identificado. Entradas por empréstimo e pagamentos de empréstimos aparecem junto a outros movimentos: o rótulo “lucro” não é suficiente para concluir que a diferença seja lucro contábil ou rentabilidade da academia.

## Evidências de inconsistências e riscos de interpretação

| ID | Evidência localizada | Leitura e limite |
|---|---|---|
| OBS-01 | GRADU.!A8=Heber; D8=FREQUÊNCIA!C32+57. FREQUÊNCIA!A32=Jeison; A33=Heber. | Referência de uma linha de graduação consulta contagem atribuída a outro nome. É uma divergência objetiva de referência/identificação que precisa de confirmação antes de corrigir. O total salvo usa 22+57=79; a linha de frequência de Heber contém 8 presenças. Não se propôs novo total porque o ajuste 57 também precisa de explicação. |
| OBS-02 | PAG. SETEMBRO!A1=JULHO; PAGAMENTOS (AGOSTO)!A1=JULHO; NOVEMBRO!A1=OUTUBRO. | Conflitos entre título e nome da aba. Não se escolheu silenciosamente qual período representa cada registro. |
| OBS-03 | FAT. AGOSTO/SET/OUT/NOVEMBRO têm datas de setembro. | Pode ser cópia de modelo ou data de pagamento distinta da competência; interpretação depende do usuário. |
| OBS-04 | ALUNOS!D6=02/07/2026 e F6=02/05/2026, sob 1º e 2º grau. | Sequência de datas aparentemente invertida; confirmar significado ou digitação. Não foi alterada. |
| OBS-05 | 47 nomes em ALUNOS INFO, 40 em ALUNOS, 42 em GRADU. e 42 em FREQUÊNCIA. | Listas com abrangência e identificações diferentes, não prova de alunos perdidos ou ativos. Nomes completos e abreviados exigem conciliação humana. Nenhum identificador único comum foi identificado nesses campos. |
| OBS-06 | Contatos e nascimento parcialmente preenchidos; endereço e emergência sem valores. | Completude observável desta cópia; obrigatoriedade e atualização ainda desconhecidas. Telefones são armazenados como texto e número. |
| OBS-07 | Cores de nomes, faixas, células e linhas ocultas; sem legenda completa. | Não se inferiu matrícula ativa, cancelamento, bolsa ou inadimplência só por cor/ocultação. |
| OBS-08 | FREQUÊNCIA mostra TREINO 3.1, TREINO 3.2 e semanas com até seis treinos; alguns títulos de mês/semana cruzam os blocos. | Precisa explicar relação com datas reais, treinos extras e reposições. Não se deduziu cancelamento ou aula extra específica. Área final ES:EV não tem marcações e fica fora dos contadores; é risco de extensão futura, não perda atual comprovada. |

## Entendimento consolidado nesta etapa

A operação tem frentes de cadastro/contato, acompanhamento de presença e permanência, desenvolvimento técnico/graduação, planos e cobrança, vendas de materiais e gestão financeira. A rotina planejada também considera alunos experimentais, integração de novatos e comunicação individual.

A presença tem consequência além de uma lista de chamada: alimenta cálculos de graduação. Portanto compreender quem registra, quando registra e como lida com exceções é necessário antes de especificar comportamento. A existência das fórmulas demonstra esse vínculo no arquivo; o papel exato delas na decisão do professor ainda precisa de confirmação.

A planilha apresenta pontos concretos para investigar, mas não permite escolher sozinha o maior problema de negócio ou afirmar perdas. Ainda estamos na descoberta; não é momento de aprovar H1 global nem escolher arquitetura.

## Próxima pergunta, uma por vez

Como a presença é registrada na prática, desde a aula até o preenchimento da planilha: quem faz isso e em que momento?

Depois dessa explicação, esclarecer significados de hífen/vazio, ligação de treino com data, cancelamentos/reposições, visitantes/experimentais, ajustes históricos e critérios de graduação. As demais frentes serão aprofundadas sequencialmente, sem presumir compreensão completa pela leitura do arquivo.
