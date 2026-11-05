---
id: BUS-FICT-001
tipo: contexto-de-negocio
versao: "1.0.0"
status: Em revisão
responsavel: Analista de negócios, papel exercido pelo Codex
fontes: [SOL-FICT-001, DADOS-FICT-001]
dependencias: [DADOS-FICT-001]
aprovacao:
  marco: H1
  status: Aguardando sua aprovação
  evidencia: null
---
# Contexto do negócio fictício

## Problema e recorte

Pedidos rotineiros de manutenção da empresa Exemplo exigem cobranças para voltar a ser tratados. O exercício investiga perda de acompanhamento, não a velocidade da execução física do serviço. Abrange recebimento, organização, acompanhamento e comunicação de conclusão de pedidos rotineiros; emergências ficam fora do recorte (DF-07).

## Pessoas envolvidas

Funcionários solicitam manutenção; a coordenação organiza e combina prioridade e responsável; quem executa realiza o serviço. As responsabilidades descritas vêm de DF-01 e DF-05, não de uma definição técnica de permissões de sistema.

## Como acontece hoje

1. O funcionário relata a necessidade presencialmente ou por mensagem direta (DF-02).
2. A coordenação faz anotações pessoais e combina o atendimento (DF-02/DF-05).
3. Sem conferência compartilhada regular, alguns pedidos só voltam a ser tratados após cobrança (DF-02/DF-03).
4. Quem executa termina o serviço e a coordenação comunica a conclusão (DF-05).

O passo 3 descreve a coexistência das situações no cenário, não uma causa comprovada.

## Evidências do cenário e valor a investigar

Na semana fictícia, 8 de 40 pedidos exigiram cobrança: **20%**. O tempo somado nas cobranças foi 8 × 10 = **80 minutos por semana** (DF-03/DF-04).

Esses números são a linha de base inventada do exercício. Não representam resultado observado do workflow nem benefício já obtido. Não há dados para estimar economia financeira ou prazo médio dos serviços.

Objetivo proposto para discussão H1: reduzir para no máximo 10% a parcela de pedidos que exigem cobrança, durante quatro semanas comparáveis, sem aumentar a carga total de acompanhamento. Com 40 pedidos por semana, isso corresponde a no máximo 4 cobranças; mantendo 10 minutos por cobrança, a redução potencial seria 40 minutos por semana. O tempo adicional de acompanhamento precisa ser descontado: o ganho líquido ainda é desconhecido.

Indicadores propostos: pedidos recebidos, pedidos que exigiram ao menos uma cobrança por falta de acompanhamento, tempo das cobranças e tempo gasto na rotina de acompanhamento. Um pedido é contado uma única vez na taxa semanal, mesmo com várias cobranças. Medir o tempo das cobranças separadamente para não perder repetições.

## Regras conhecidas e limites do entendimento

- RB-01: a coordenação combina prioridade e responsável com quem executa, em vez de assumir prioridade automática (DF-05).
- RB-02: a conclusão deve ser comunicada ao solicitante conforme o processo descrito (DF-05).
- RB-03: emergências não são encaminhadas como pedidos rotineiros deste recorte (DF-07); o procedimento específico continua não descrito.

As regras acima são derivadas exclusivamente das premissas fictícias e continuam em revisão. Não foram definidas prioridades, prazos, permissões ou mecanismos de encaminhamento novos.

## Hipóteses e alternativas de melhoria

HIP-01: a dispersão das entradas e ausência de conferência contribuem para o esquecimento; investigar comparando os pedidos acompanhados com os que exigiram cobrança.

Alternativas de reorganização do negócio, sem escolher tecnologia: combinar um ponto de recebimento conhecido por todos; estabelecer conferência regular dos pedidos em aberto; esclarecer quem dá retorno ao solicitante. Comparar esforço e efeito das alternativas antes de decidir quais adotar. Apenas copiar as anotações atuais para outro meio não demonstra melhoria.

## Pendências explícitas

| ID | Pergunta | Quando precisa ser resolvida |
|---|---|---|
| P-01 | Quais situações definem prioridade entre pedidos rotineiros? | Antes de especificar comportamento de priorização. |
| P-02 | O que fazer quando não houver responsável disponível? | Antes de especificar encaminhamento e exceções. |
| P-03 | Qual rotina de conferência é viável sem custar mais do que as cobranças evitadas? | Antes de adotar uma alternativa de melhoria. |
| P-04 | O usuário aceita recorte, premissas e objetivo proposto deste exercício? | H1, antes de iniciar especificação funcional. |

H1 pode reconhecer P-01 a P-03 como limites conhecidos, mas não autoriza inventar respostas na etapa seguinte. Se forem críticas para a Feature escolhida, devem voltar à descoberta antes de especificar esse comportamento.

## Glossário

Pedido: necessidade de manutenção relatada por um funcionário. Cobrança: contato posterior necessário para recuperar acompanhamento, não uma cobrança financeira. Coordenação: pessoa que organiza atendimento. Conclusão: serviço terminado com retorno ao solicitante; nenhum mecanismo de aceite formal foi definido.
