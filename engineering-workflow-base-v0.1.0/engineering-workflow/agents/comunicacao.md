---
id: CONTRATO-COMUNICACAO-001
tipo: contrato-de-comunicacao
versao: "0.1.0"
status: Em revisão
responsavel: Governança do workflow
fontes: [DIRECAO-PRODUTO-001, DEC-003, DEC-007, DEC-010]
---
# Comunicação entre os quatro agentes

## Modelo proposto
Usuário conversa com Orquestrador. Orquestrador encaminha tarefas, perguntas, respostas, objeções e correções entre Analista de Negócio, Arquiteto de Software e Desenvolvedor. Todos usam referências aos mesmos artefatos vigentes; um papel lógico é executado por vez.

“Escutar” significa ler a entrada e as respostas anteriores pertinentes, confirmar o entendimento e responder aos pontos abertos. Encaminhar uma mensagem não significa que o destinatário já a leu ou aceitou. Registrar separadamente envio, recebimento e resposta. O Orquestrador não altera o sentido da mensagem para encobrir conflito.

A execução sequencial preserva DEC-007; não implica processos independentes. A forma de acionar tecnicamente cada papel será escolhida antes do teste, sem confundir esses contratos com agentes instalados.

## Conteúdo mínimo de uma tarefa ou mensagem
| Campo | Conteúdo |
|---|---|
| Identificação | ID da mensagem, execução, projeto e tarefa, quando aplicável |
| Origem e destino | Papel de origem, papel destinatário e encaminhamento do Orquestrador |
| Tipo | Tarefa, Pergunta, Resposta, Correção ou Impedimento |
| Etapa e objetivo | O que se pede agora e qual resultado é esperado |
| Contexto | Fontes, artefatos e versões; referência de aprovações exigidas |
| Conteúdo | Instrução autorizada, pergunta exata ou resposta fundamentada |
| Limites | Escopo, permissões, guardrails e ações não liberadas |
| Conclusão esperada | Saída e critérios verificáveis para aceitar a resposta |
| Continuidade | ID ao qual responde, perguntas abertas e próxima ação |

Para dúvida pontual, referenciar o pacote já salvo em vez de copiar todos os documentos. Nunca omitir exceção ou evidência essencial para economizar contexto. Campos sem aplicação devem ser marcados como Não se aplica, com explicação quando necessário.

## Resposta mínima do agente
Referenciar a mensagem/tarefa; registrar seu entendimento; informar resultado e situação; listar documentos produzidos com IDs/versões, verificações/evidências, perguntas, impedimentos, pontos respondidos e recomendação de próxima ação. Não é o especialista quem autoriza transição ou aprova gate.

O Orquestrador confere se a resposta corresponde à pergunta e à versão das entradas, resolve referências e registra aceite para transferência ou devolução. Uma resposta incompatível com a especificação não vira requisito automaticamente.

## Situações em português
Tarefa: Pendente, Em andamento, Concluído, Precisa de correção, Bloqueado ou Cancelado.
Documento: Rascunho, Em revisão, Aprovado, Rejeitado ou Substituído.
Execução: Em andamento, Aguardando esclarecimento, Aguardando sua aprovação, Bloqueado, Concluído ou Cancelado.
Mensagem: Preparada, Encaminhada, Recebida ou Respondida.

São vocabulários candidatos para esta revisão. A situação da tarefa não substitui a do documento, da mensagem ou da execução. Mensagem respondida pode conter impedimento. Documento aprovado não conclui a melhoria.

## Percurso normal
1. Usuário → Orquestrador: problema ou necessidade.
2. Orquestrador → Analista: descoberta; Analista retorna contexto e perguntas.
3. Orquestrador ↔ usuário: esclarecimentos e H1 sobre versão identificada.
4. Orquestrador → Analista: especificação funcional; retorno com critérios.
5. Orquestrador ↔ usuário: H2.
6. Orquestrador → Arquiteto: solução e plano; retorno com alternativas e riscos.
7. Orquestrador ↔ usuário: H3.
8. Orquestrador → Arquiteto: tarefas aprovadas; depois → Desenvolvedor: implementação.
9. Desenvolvedor → Orquestrador: código, testes e evidências; conferência dos critérios e retorno para correção se necessário.
10. Entrega para revisão humana, com publicação externa quando autorizada. Não há merge automático.

## Percurso de dúvida e correção
Após H2, Arquiteto → Orquestrador → Analista: pergunta com critério, contexto e impacto. Analista responde com fonte ou pede decisão humana. O Orquestrador devolve a resposta e a referência ao Arquiteto; o Arquiteto registra o entendimento e efeito no plano.

Após H3, Desenvolvedor → Orquestrador → Arquiteto: impedimento técnico com evidência. Se houver mudança de regra, o Orquestrador envolve o Analista e o usuário. Mudanças aprovadas geram nova versão; trabalho dependente aguarda a aprovação aplicável. Não resolver conflito por maioria de agentes ou pela última resposta.

Antes dos gates, o percurso não autoriza produção antecipada de solução técnica. Pedido que extrapola etapa é impedido e encaminhado à responsabilidade correta.

## Estado e retomada
Salvar última mensagem processada, mensagens pendentes, tarefa, papel, etapa, referências, aprovações e próxima ação. Na retomada, conferir conteúdo e versões antes de reenviar. Resultado desconhecido de publicação deve ser investigado para evitar duplicação.

Formato definitivo de YAML e validador serão definidos na preparação do teste. Este contrato especifica comportamento e conteúdo; não declara transporte ou automação implementados.

## Critérios de comunicação
O destinatário certo recebe contexto suficiente; versões coincidem; respostas resolvem ou explicam pendências; discordância fica visível; aprovação humana é preservada; estado permite identificar o próximo passo sem depender da memória do chat.
