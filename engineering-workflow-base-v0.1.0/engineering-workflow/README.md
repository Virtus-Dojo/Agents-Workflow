# Engineering Workflow — Base contextual v0.1.0

Este pacote é a **especificação inicial**, não uma implementação operacional. A esteira é reutilizável e independente do projeto-piloto de academia de Jiu-Jitsu.

## Leia nesta ordem
Direção atual: `governance/direcao-do-produto.md` — primeiro especificar os quatro agentes e sua comunicação; depois testar um cenário da academia; por fim refinar e testar novamente. Pacote de especificação: `governance/especificacao-quatro-agentes.md`, com contratos dos quatro papéis e de comunicação, em revisão.

1. `governance/decisions.md` — decisões aprovadas.
2. `agents/orchestrator.md` — contrato do orquestrador.
3. `governance/lifecycle.md` — etapas e gates.
4. `guardrails/orchestrator.md` — restrições.
5. `contracts/execution/` — exemplos de entradas, saídas e estado.
6. `tests/acceptance.md` — validação antes da implementação.
7. `governance/orchestrator-review.md` — pacote de revisão e escolhas pendentes.

## Princípios
- Um interlocutor com o usuário; especializações lógicas sequenciais.
- Descoberta investiga negócio sem antecipar solução técnica.
- H1, H2 e H3 são obrigatórios; não presumir aprovação.
- Conhecimento persistente, versionado e rastreável.
- Um repositório para o workflow, outros para cada produto.
- Não inventar regras de negócio da academia.

## Status
DEC-001 a DEC-010 foram aprovadas na conversa. Formatos concretos de arquivos, severidades por regra e detalhes de integração são **propostas**, não decisões aprovadas. Não há código, agentes executáveis, GitHub ou CI configurados.

O comportamento do Orquestrador 0.3.0 está Aprovado, com evidência e limites em `governance/aprovacao-orquestrador-0.3.0.md`; sua operação ainda não foi comprovada. PROP-ORC-01 a PROP-ORC-07 são preservadas como aprovadas. A candidata anterior 0.2.0 está em `agents/historico/orchestrator-0.2.0.md`; os casos anteriores continuam vinculados àquela versão. Evidência das sete propostas: `governance/approval-orchestrator-2026-11-04.md`. Os três especialistas e o contrato de comunicação estão em 0.1.0, Em revisão. Isso não publica nova versão do pacote v0.1.0; os YAMLs continuam exemplos iniciais.

Os 30 casos foram exercitados como simulação textual assistida pelo Codex, com 30 PASS-SIM nas ramificações registradas em `tests/runs/2026-11-04-manual.md`. Não houve runtime ou executor humano independente; aceitação independente e validação operacional continuam pendentes.

Na revisão atual, o Analista de Negócio está em 0.2.0, com matriz de fundamentos 0.1.0 em `agents/fundamentos-analista-de-negocio.md`, ambos Em revisão. O pacote `governance/especificacao-quatro-agentes.md` indica as versões correntes de cada documento.
