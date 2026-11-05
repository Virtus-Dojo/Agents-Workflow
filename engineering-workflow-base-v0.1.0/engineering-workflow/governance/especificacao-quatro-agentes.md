---
id: PACOTE-QUATRO-AGENTES-001
tipo: pacote-de-especificacao
versao: "0.1.0"
status: Em revisão
responsavel: Governança do workflow
fontes: [DIRECAO-PRODUTO-001]
---
# Especificações dos quatro agentes

## Ordem determinada pelo usuário
1. Definir claramente as especificações e comportamentos dos quatro agentes, incluindo sua comunicação.
2. Testar um cenário da academia de Jiu-Jitsu, acompanhando a troca entre os agentes e a entrega final.
3. Refinar a partir das evidências e testar novamente.

Fonte: mensagem do usuário neste chat 01a19e19-e626-70f2-9159-c9dd0a5176d5 iniciada por “Vamos l, você está perdido e vou lhe direcionar”. Esta ordem corrige o roteiro anterior; leitura de domínio e simulações anteriores não concluem qualquer dessas etapas.

## Pacote da primeira etapa
| Documento | Versão | Situação |
|---|---|---|
| ../agents/orchestrator.md | 0.3.0 | Comportamento aprovado |
| ../agents/analista-de-negocio.md | 0.2.0 | Em revisão |
| ../agents/fundamentos-analista-de-negocio.md | 0.1.0 | Em revisão |
| ../agents/arquiteto-de-software.md | 0.1.0 | Em revisão |
| ../agents/desenvolvedor.md | 0.1.0 | Em revisão |
| ../agents/comunicacao.md | 0.1.0 | Em revisão |

As dez decisões e as sete propostas já aprovadas são preservadas. Detalhes novos não são promovidos a aprovados pela escrita dos arquivos.

O comportamento do Orquestrador foi aprovado pelo usuário na revisão em chat. Evidência e limites em aprovacao-orquestrador-0.3.0.md. Próximo papel a revisar: Analista de Negócio. A aprovação não se estende automaticamente aos outros contratos ou aos formatos definitivos de mensagem/estado.

O usuário solicitou reforçar o Analista com fundamentos de levantamento de requisitos e práticas de grandes empresas de tecnologia. A proposta está na matriz fundamentos-analista-de-negocio.md, com referências públicas separadas de fundamentos profissionais e critérios observáveis de aplicação; a matriz ainda não foi aprovada nem testada.

## Escolhas de comportamento apresentadas nesta revisão
- O Analista de Negócio prepara descoberta e especificação funcional em momentos separados por H1, mantendo H2 para o comportamento.
- O Arquiteto prepara solução e plano para H3 e decompõe tarefas executáveis após aprovação.
- O Desenvolvedor implementa e produz evidências; o Orquestrador confere vínculo com critérios e coordena correções.
- Os especialistas recebem e respondem mensagens uns dos outros por intermédio do Orquestrador, sequencialmente.
- Contratos incluem entradas, saídas, autonomia, impedimentos, comunicação e critérios para conferir a entrega.

## Quando a primeira etapa estará concluída
Responsabilidades e comunicação revisadas, funções essenciais atribuídas, conflitos e alterações necessários resolvidos e decisão do usuário sobre os comportamentos registrada. A conferência estática apenas demonstra presença e coerência documental, não agentes funcionando.

## Preparação da segunda etapa, depois da primeira
Escolher um recorte da academia com resultado esperado; identificar fontes e lacunas; definir o meio de executar os papéis e os arquivos de mensagens/estado. Registrar se os papéis são representados por um assistente ou executados separadamente. Não chamar simulação de integração.

Durante o cenário, demonstrar: encaminhamento, confirmação de entendimento, pergunta/objeção e resposta entre especialistas, correção quando necessária, H1/H2/H3 reais e evidência da entrega. O fim pode incluir software e PR conforme aprovações, permissões e ambiente; sem código executado não declarar solução funcionando.

As regras de domínio e a planilha ficam fora do núcleo genérico. Nenhum recorte da academia foi aprovado automaticamente por esta especificação.

## Refinamento e novo teste
Comparar comportamento observado com esperado, registrar defeitos e causas, versionar correções, repetir os pontos afetados e uma passagem completa do cenário quando as mudanças impactarem o percurso. O resultado da primeira rodada não deve ser reescrito para parecer que sempre funcionou.

## Situação atual
Primeira etapa: pacote documental preparado para revisão, não aprovado integralmente.
Segunda etapa: Não iniciada.
Terceira etapa: Não iniciada.
