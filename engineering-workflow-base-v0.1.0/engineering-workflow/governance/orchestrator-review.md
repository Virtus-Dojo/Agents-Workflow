---
id: REVIEW-ORCHESTRATOR
type: review-package
version: "0.1.0"
status: DRAFT
owner: workflow-governance
sources: [AGENT-ORCHESTRATOR, ACCEPTANCE-ORCHESTRATOR, DEC-003, DEC-006, DEC-009, DEC-010]
---
# Pacote de revisão do orquestrador

Revisar agents/orchestrator.md 0.2.0 e tests/acceptance.md 0.2.0, ambos DRAFT. Esta é revisão da governança, não H1/H2/H3 de uma Feature. Não altera DEC-001 a DEC-010, não aprova negócio do piloto nem autoriza implementação ou publicação externa.

## Escolhas propostas para decisão

| ID | Recomendação | Consequência |
|---|---|---|
| PROP-ORC-01 | Precedência BLOCK, REWORK, REQUEST_APPROVAL e ADVANCE; preservar todos os achados | Pendência de aprovação não encobre contrato inválido |
| PROP-ORC-02 | Diferenciar pedido de aprovação de tentativa de atravessar gate | Pacote apto gera REQUEST_APPROVAL; avanço sem aprovação gera BLOCK |
| PROP-ORC-03 | Aprovação vinculada a projeto, gate, aprovador designado e versões, com evidência resolúvel | Flags, silêncio e término de tarefa não autorizam avanço |
| PROP-ORC-04 | Edição de conteúdo aprovado gera candidata sem herança automática da aprovação | Preservar histórico, analisar impacto e obter aprovações aplicáveis |
| PROP-ORC-05 | Reconciliar estado, artefatos e evidências ao retomar; conferir efeitos externos antes de repetir | Divergências críticas suspendem operações dependentes |
| PROP-ORC-06 | Não definir retry automático nesta fase | Novas tentativas registradas e condicionadas à conferência do resultado anterior |
| PROP-ORC-07 | Aceitação inicial por execução manual dos 30 casos | Verificar comportamento antes de investir em runtime; sem comprovação de controles técnicos |

Nenhuma proposta é aprovada pela criação deste pacote. Registrar decisão humana explícita e referência à manifestação antes de promover status. Aprovação documental não é autorização genérica para publicar ou fazer merge.

## Decisão humana registrada em 2026-11-04

PROP-ORC-01 a PROP-ORC-07: **APPROVED**, conforme `approval-orchestrator-2026-11-04.md` (APPROVAL-ORC-2026-11-04 1.0.0). Esta anotação registra a decisão sobre as sete propostas sem promover integralmente o contrato, os schemas ou as pendências abaixo. O pacote mantém DRAFT por conter conteúdo ainda não deliberado.

## Pendências fora desta revisão

- Schemas definitivos e formato dos registros de tentativa, decisão e aprovação. Os cinco YAMLs continuam exemplos 0.1.0 e não cobrem todo o contrato proposto.
- Severidades individuais do catálogo, ainda propostas. Os casos usam o catálogo como fixture de comportamento, sem aprová-lo.
- Política de cancelamento e encerramento da execução após PR/merge, além dos limites presentes no contrato.
- Granularidade física de Technical Spec/Plan e Functional Spec/Acceptance Criteria, metadados e templates completos.
- Contratos dos três especialistas (Analista de Negócio, Arquiteto de Software e Desenvolvedor), além da revisão do Orquestrador, e designação de responsáveis aprovadores por projeto. A composição atual de quatro agentes no total está registrada em `direcao-do-produto.md`; substitui a previsão anterior de Analista de Sistemas separado.
- Canal de execução no Codex, armazenamento, controles técnicos, release e mecanismo de adoção pelo piloto.

## Estado real

As sete propostas têm aprovação humana registrada. Resultados da rodada assistida estão em `../tests/runs/2026-11-04-manual.md`; não há runtime, schemas automatizados, agentes especializados, CI ou integração implementados. O registro das dez decisões permanece preservado.
