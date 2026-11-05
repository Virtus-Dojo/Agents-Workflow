---
id: GR-CATALOG-ORCHESTRATOR
type: guardrail-catalog
version: "0.1.0"
status: DRAFT
sources: [DEC-003, DEC-008, DEC-009]
---
# Guardrails — catálogo proposto

A política BLOCK/REWORK/WARN está aprovada; a severidade individual abaixo é uma proposta a validar.

| ID | Regra | Tratamento |
|---|---|---|
| GR-B01 | Não antecipar solução técnica durante descoberta | BLOCK |
| GR-B02 | Não inventar regras de negócio | BLOCK |
| GR-B03 | Separar fatos, hipóteses e pendências | REWORK |
| GR-B04 | Investigar causas, objetivos e impactos | REWORK |
| GR-B05 | Priorizar valor, não somente automação do AS-IS | REWORK |
| GR-G01 | Não ultrapassar H1/H2/H3 sem aprovação explícita | BLOCK |
| GR-G02 | Não autoaprovar gates | BLOCK |
| GR-G03 | Não alterar escopo aprovado unilateralmente | BLOCK |
| GR-G04 | Registrar decisões e justificativas | REWORK |
| GR-D01 | Respeitar contratos documentais | BLOCK na transferência |
| GR-D02 | Preservar IDs, versões e rastreabilidade | REWORK |
| GR-D03 | Não tratar documento obsoleto como vigente | BLOCK |
| GR-D04 | Registrar origem e evidências | REWORK |
| GR-D05 | Analisar impactos de mudanças compartilhadas | REWORK |
| GR-E01 | Respeitar atividades autorizadas | BLOCK |
| GR-E02 | Não executar ações destrutivas sem autorização | BLOCK |
| GR-E03 | Bloquear trabalho dependente de ambiguidade crítica | BLOCK |
| GR-E04 | Usar contexto mínimo suficiente | WARN |
| GR-E05 | Registrar falhas, correções e resultados | REWORK |
| GR-E06 | Não declarar sucesso sem verificação | BLOCK |

`BLOCK` impede a operação; `REWORK` devolve para correção; `WARN` registra sem impedir trabalho independente. Regras críticas exigem reforço técnico posterior, não apenas prompts.
