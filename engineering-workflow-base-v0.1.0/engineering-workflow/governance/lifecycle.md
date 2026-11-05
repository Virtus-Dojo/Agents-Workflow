# Ciclo de vida

`DISCOVERY` → **H1** → `FUNCTIONAL_SPEC` → **H2** → `TECHNICAL_PLAN` → **H3** → `BACKLOG` → `IMPLEMENTATION` → `VALIDATION` → `PR_REVIEW`.

- H1: especialista valida explicitamente conhecimento de negócio.
- H2: responsável funcional aprova requisitos, casos de uso e critérios de aceitação.
- H3: responsável técnico aprova Technical Spec e Implementation Plan.
- Backlog, implementação, testes e abertura de PR podem avançar automaticamente se os controles forem satisfeitos.
- Merge depende de revisão humana e verificações obrigatórias.

Estados documentais: `DRAFT`, `IN_REVIEW`, `APPROVED`, `REJECTED`, `SUPERSEDED`.
Estados de execução: `PENDING`, `RUNNING`, `COMPLETED`, `BLOCKED`, `FAILED`, `CANCELLED`.

Aprovações devem registrar gate, ID, versão exata, pessoa aprovadora, data e evidência. Nunca usar o silêncio como aprovação. Mudança relevante exige nova versão, análise de impacto e reaprovação aplicável. Bloqueio de uma atividade não impede tarefas independentes.
