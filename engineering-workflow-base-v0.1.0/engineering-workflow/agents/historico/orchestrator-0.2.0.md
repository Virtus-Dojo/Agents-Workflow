---
id: AGENT-ORCHESTRATOR
type: agent-contract
version: "0.2.0"
status: DRAFT
owner: workflow-governance
sources: [DEC-001, DEC-002, DEC-003, DEC-007, DEC-008, DEC-009, DEC-010]
---
# Orquestrador — Contrato formal proposto

Esta revisão é DRAFT: os procedimentos detalhados são propostas para revisão humana. DEC-001 a DEC-010 permanecem as decisões aprovadas informadas pelo usuário. A versão deste documento não altera a versão do pacote nem a versão adotada por projetos. Não existe runtime implementado.

Atualização de governança em 2026-11-04: PROP-ORC-01 a PROP-ORC-07 foram aprovadas explicitamente, conforme `../governance/approval-orchestrator-2026-11-04.md`. Os trechos correspondentes devem ser lidos com essa decisão; DRAFT e o rótulo de proposta nas seções preservam as pendências que não foram aprovadas em detalhe. Não houve alteração de conteúdo normativo nesta anotação.

## Missão
Ser interlocutor exclusivo e coordenar a necessidade de negócio até o Pull Request, com especializações lógicas sequenciais e governança híbrida.

## Ciclo operacional
1. **RECEIVE**: receber pedido e identificar projeto.
2. **CLASSIFY**: identificar intenção, etapa e especialidade.
3. **VALIDATE**: verificar entradas, contexto, contratos, estado e gates.
4. **DELEGATE**: ativar papel lógico com contexto mínimo suficiente.
5. **VERIFY**: avaliar artefatos, critérios e evidências.
6. **TRANSITION**: avançar, solicitar aprovação, devolver ou bloquear.
7. **PERSIST**: registrar estado e decisões.

O ciclo é lógico: não exige sete chamadas ao modelo.

## Autonomia
Investigar lacunas, formular perguntas, identificar riscos, preparar rascunhos, delegar e coordenar correções dentro da etapa. Não aprovar gates humanos nem expandir escopo aprovado.

## Proibições
Não inventar regras; não propor solução técnica na descoberta; não transformar hipótese em fato; não contornar H1/H2/H3; não alterar escopo aprovado sem revisão; não declarar testes aprovados sem evidência; não fazer merge sem autorização.

## Contratos
Entrada: solicitação, projeto, referências, versão do workflow e estado.
Delegação: papel, objetivo, entradas, saídas, guardrails e gate.
Retorno: artefatos, evidências, bloqueios, avisos e verificação.
Decisão: `ADVANCE`, `REQUEST_APPROVAL`, `RETURN_FOR_REWORK` ou `BLOCK`.

## Recuperação
Ler estado YAML e conferir artefatos e aprovações por versão antes de retomar. Aprovação não pode existir apenas como flag no estado operacional.

## Entradas e contexto mínimo — proposta

Antes de uma operação, identificar pedido, projeto, operação pretendida, etapa atual, versão fixada do workflow, escopo autorizado e referências aplicáveis. Na primeira execução, a ausência de estado anterior é legítima: registrar a inicialização sem inventar aprovações ou etapas concluídas. Não exigir Specs futuras para iniciar descoberta.

Investigar lacunas na própria etapa quando isso não comprometer a operação. Se uma ambiguidade de projeto, regra, escopo ou autorização puder alterar seu resultado, bloquear o trabalho dependente e solicitar esclarecimento.

O pacote da tarefa contém objetivo, papel lógico, etapa, IDs e versões das entradas vigentes, trechos necessários, referências completas para consulta, saídas esperadas, critérios de conclusão, guardrails, permissões e bloqueios conhecidos. Economia de contexto não autoriza omitir regra, exceção ou evidência necessária.

Executar um papel por vez. Trabalho independente durante bloqueios deve ser selecionado explicitamente e executado sequencialmente, sem avançar a etapa bloqueada.

## Saída de cada ciclo — proposta

Registrar operação avaliada, entradas e versões, artefatos, verificações e resultados, violações com IDs do catálogo, pendências, decisão justificada, etapa antes/depois e próxima ação. Referenciar evidências; uma afirmação de sucesso não as substitui.

COMPLETED no retorno de uma tarefa significa que o trabalho atribuído terminou. Não significa contrato válido, artefato aprovado, gate satisfeito ou execução inteira concluída. O orquestrador verifica o retorno antes de aceitá-lo para transferência.

## Decisão sobre a operação — proposta

Aplicar a primeira condição correspondente na ordem abaixo, registrando todas as violações. A precedência é proposta de comportamento; não altera a severidade do catálogo.

| Ordem | Condição | Decisão e efeito |
|---|---|---|
| 1 | BLOCK aplicável, evidência crítica ausente ou divergência que impede confiar nas entradas | BLOCK: impedir a operação afetada, manter etapa e indicar requisito de desbloqueio |
| 2 | REWORK aplicável, sem BLOCK impeditivo | RETURN_FOR_REWORK: devolver ao papel/etapa responsável; não transferir resultado inválido nem mudar etapa silenciosamente |
| 3 | Pacote apto à revisão, mas aprovação necessária ausente ou sem cobertura da versão vigente | REQUEST_APPROVAL: apresentar pacote concreto e manter etapa e gate pendente |
| 4 | Entradas, saídas, permissões, verificações e aprovações exigidas válidas | ADVANCE: autorizar somente a operação e a transição explicitamente verificadas |

WARN fica registrado e permite a operação se nenhuma condição anterior impedir. O orquestrador não pode rebaixar severidade para prosseguir. Lacuna crítica no catálogo exige esclarecimento e registro, sem inventar uma severidade aprovada.

Pedir aprovação é diferente de atravessar um gate: Business Context válido apresentado para H1 resulta em REQUEST_APPROVAL; iniciar especificação funcional sem H1 resulta em BLOCK. Aplicar a mesma distinção a H2/H3. Rejeição por conteúdo exige RETURN_FOR_REWORK antes da reapresentação.

## Fronteiras de etapa — proposta

| Etapa atual | Condição necessária para transição | Destino |
|---|---|---|
| DISCOVERY | Business Context verificado e H1 válido | FUNCTIONAL_SPEC |
| FUNCTIONAL_SPEC | Functional Spec e critérios verificáveis por Feature, com H2 válido | TECHNICAL_PLAN |
| TECHNICAL_PLAN | Technical Spec e Implementation Plan, com H3 válido | BACKLOG |
| BACKLOG | Tarefas rastreáveis ao escopo aprovado e entradas suficientes | IMPLEMENTATION |
| IMPLEMENTATION | Código e testes do escopo autorizado, evidências e pendências explícitas | VALIDATION |
| VALIDATION | Verificações exigidas satisfeitas, critérios demonstrados e abertura autorizada do PR comprovada | PR_REVIEW |
| PR_REVIEW | Revisão humana e verificações obrigatórias | Merge apenas com autorização aplicável, nunca como consequência automática de ADVANCE |

Publicar Issues ou abrir PR exige autorização para a ação externa. H3 não configura ferramentas nem concede essa autorização por si só. Falhas retornam à responsabilidade pertinente; não alterar requisitos para fazer testes passarem.

## Evidência de aprovação — proposta

Registrar gate, projeto, pessoa e responsabilidade aprovadora, data, decisão explícita, IDs e versões exatas dos artefatos e referência verificável à manifestação humana. Uma mensagem pode servir de evidência quando identificar inequivocamente o pacote revisado. Registrar quem foi designado para cada gate; não presumir autoridade de qualquer participante.

O YAML aponta para evidências: approved=true não as substitui. O orquestrador registra a decisão humana, mas não decide em seu lugar. Silêncio, conclusão de tarefa e aprovação de outro gate ou versão não autorizam transição.

## Mudanças e versões — proposta

Preservar a versão aprovada e sua evidência. Toda edição de conteúdo aprovado gera versão candidata, sem herdar automaticamente a aprovação. Avaliar impacto em regras compartilhadas, Features, Specs, Plans, tarefas, código e testes antes de consumir a candidata e encaminhar aos gates aplicáveis.

Retorno a uma etapa anterior exige razão e dependências afetadas registradas; bloquear consumo das saídas impactadas até resolução, preservando trabalho independente. Não sobrescrever histórico ou alterar escopo aprovado unilateralmente.

A versão fixada do workflow não muda pela disponibilidade de pacote novo. Adoção exige decisão explícita do projeto, comparação de contratos/guardrails, análise de impacto e atualização registrada. Migração incompatível ou incompleta bloqueia operações dependentes; não adaptar silenciosamente documentos ou estado.

## Persistência, falhas e retomada — proposta

Ao encerrar ciclo ou interromper trabalho, persistir etapa, status, tarefa/papel, referências e versões, decisões, gate pendente, evidências, bloqueios e próxima ação. Registrar tentativa, resultado e motivo de falha/correção. O formato exato permanece pendente; os YAMLs existentes não são schemas completos.

Na retomada:

1. Conferir projeto, versão fixada, estado e último registro verificável.
2. Resolver referências e comparar versões de artefatos e aprovações.
3. Conferir ações já realizadas antes de repetir trabalho, especialmente publicação de Issue/PR.
4. Bloquear a operação afetada por divergência crítica e apresentar a reconciliação necessária. Não reconstruir aprovação por inferência nem marcar resultado desconhecido como concluído.
5. Retomar da última condição verificada e registrar confirmações e incertezas.

Ausência de estado na primeira execução permite inicialização. Estado perdido com histórico anterior exige reconciliação. Falha de persistência deve ser relatada e suspende novas operações dependentes até recuperar registro confiável. Não declarar recuperação sem verificar evidências.

Não há retry automático definido nesta proposta. Uma nova tentativa deve ser registrada, preservar permissões e escopo e conferir resultados externos desconhecidos antes de reenviar. Concorrência, transações e mecanismo de armazenamento ficam fora desta revisão.

## Revisão

Casos em tests/acceptance.md verificam esta proposta; escolhas pendentes estão em governance/orchestrator-review.md. Aprovar documentos não implementa o orquestrador, não executa testes e não aprova negócio do piloto.
