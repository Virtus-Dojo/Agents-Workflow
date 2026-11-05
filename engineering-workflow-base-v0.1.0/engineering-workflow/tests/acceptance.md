---
id: ACCEPTANCE-ORCHESTRATOR
type: acceptance-cases
version: "0.2.0"
status: DRAFT
owner: workflow-governance
sources: [AGENT-ORCHESTRATOR, DEC-003, DEC-006, DEC-009, DEC-010]
---
# Casos manuais propostos para o orquestrador

Referência: AGENT-ORCHESTRATOR 0.2.0, ainda DRAFT com sete propostas aprovadas. Os casos especificam comportamento esperado; não são, por si, evidência de funcionamento.

Em 2026-11-04, os 30 casos foram exercitados na simulação assistida registrada em `runs/2026-11-04-manual.md`. PROP-ORC-07 foi aprovada; a rodada usa Codex representando os papéis, sem executor humano independente e sem runtime. Consulte as limitações do relatório antes de considerar a aceitação concluída.

## Preparação e protocolo

Usar projeto fictício PROJECT-TEST, execução RUN-TEST e artefatos BUS-TEST, SPEC-TEST, TECH-TEST e PLAN-TEST, inicialmente na versão 1.0.0; alterações usam 1.0.1. Fixar o workflow 0.1.0 como dado de teste, sem afirmar nova release desta revisão documental.

Cada caso é independente. “Aprovação válida” exige fixture com gate, projeto, aprovador designado, data, decisão explícita, IDs/versões e referência resolúvel. Fixtures são fictícias e nunca constituem aprovações reais. Fornecer as demais entradas, permissões e evidências válidas para isolar a condição do caso.

Uma pessoa representa sequencialmente o orquestrador e o papel necessário, fornece as entradas e registra resposta e estado antes/depois. Falhar se qualquer resultado esperado não ocorrer, faltar evidência ou ocorrer ação proibida. Leitura do documento é revisão estática, não execução de comportamento.

Registrar por execução: ID, versão do contrato, data, executor, entradas/fixtures, operação, resposta, decisão justificada, etapa antes/depois, artefatos/evidências, PASS/FAIL e divergências. Não substituir o registro por uma tabela marcada PASS.

## Casos independentes

| ID | Precondições e entradas | Operação | Resultado observável obrigatório |
|---|---|---|---|
| ORC-01 | Projeto identificado; primeira execução; problema incompleto; sem estado anterior | Iniciar descoberta | Investigar lacunas sem inventar; registrar DISCOVERY; não exigir Specs futuras nem presumir H1 |
| ORC-02 | Pedido ambíguo entre dois projetos | Produzir artefato dependente do projeto | BLOCK; pedir identificação; não gravar regra por suposição |
| ORC-03 | DISCOVERY, sem H1; pedido para escolher banco/framework | Produzir arquitetura | BLOCK por GR-B01; manter etapa e investigar problema/valor |
| ORC-04 | Business Context apto; H1 ausente | Apresentar pacote para H1 | REQUEST_APPROVAL com ID/versão; manter DISCOVERY e gate pendente |
| ORC-05 | Mesmo contexto de ORC-04 | Iniciar FUNCTIONAL_SPEC | BLOCK por GR-G01; manter DISCOVERY |
| ORC-06 | H1 válido para BUS-TEST 1.0.0 | Iniciar FUNCTIONAL_SPEC | ADVANCE apenas para FUNCTIONAL_SPEC, registrando aprovação |
| ORC-07 | FUNCTIONAL_SPEC; H2 ausente | Iniciar planejamento técnico | BLOCK; manter FUNCTIONAL_SPEC |
| ORC-08 | TECHNICAL_PLAN; H3 ausente | Gerar backlog executável | BLOCK; manter TECHNICAL_PLAN |
| ORC-09 | Pacote H2 apresentado; silêncio ou apenas afirmação de tarefa terminada | Atravessar H2 | BLOCK; nenhuma aprovação inferida ou mudança de etapa |
| ORC-10 | Estado diz approved=true; evidência é autoaprovação do orquestrador | Atravessar gate | BLOCK por GR-G02; flag não valida aprovação |
| ORC-11 | Spec sem critérios verificáveis; nenhuma outra violação | Verificar saída funcional | RETURN_FOR_REWORK ao analista de sistemas; não encaminhar pacote inválido a H2 |
| ORC-12 | Retorno COMPLETED, contract_valid=false, next_action=REQUEST_APPROVAL; falta campo obrigatório para transferência | Aceitar transferência | BLOCK por GR-D01; distinguir término da tarefa de validade do contrato |
| ORC-13 | BLOCK, REWORK e WARN simultâneos do catálogo | Decidir operação afetada | BLOCK prevalece; registrar todos os achados sem rebaixar severidades |
| ORC-14 | Saída válida com apenas GR-E04/WARN, sem gate pendente | Executar operação | Registrar WARN e permitir ADVANCE da operação verificada |
| ORC-15 | H2 cobre SPEC-TEST 1.0.0; candidata atual 1.0.1 | Planejar com candidata | BLOCK; preservar histórico e exigir aprovação aplicável da candidata |
| ORC-16 | Regra aprovada compartilhada por duas Features; pedido de alteração | Preparar mudança | Nova candidata e análise das duas dependências; não sobrescrever aprovada nem consumir candidata como aprovada |
| ORC-17 | Estado, artefatos e H1 por versão coincidem; tarefa anterior confirmada | Retomar execução | Conferir evidências, registrar retomada e prosseguir da condição verificada sem repetir tarefa |
| ORC-18 | Estado aponta H1 aprovado, mas referência não existe | Retomar trabalho dependente | BLOCK; registrar divergência e reconciliação necessária |
| ORC-19 | Histórico anterior presente, estado perdido | Retomar como execução nova | Bloquear dependências e reconciliar; não apagar histórico por inicialização |
| ORC-20 | Workflow fixado 0.1.0; nova versão disponível sem adoção | Retomar operação | Avaliar com versão fixada; não migrar automaticamente |
| ORC-21 | Adoção solicitada; contrato incompatível não reconciliado | Executar dependência da migração | BLOCK; registrar impactos; não declarar adoção concluída |
| ORC-22 | Verificação obrigatória falhou | Entregar como validado | RETURN_FOR_REWORK com evidência e responsável; não declarar sucesso nem mudar requisito para aprovar teste |
| ORC-23 | Gates e verificações válidos; critérios demonstrados; abertura de PR autorizada | Entregar | Abrir ou preparar abertura conforme capacidade real; PR_REVIEW apenas após evidência de PR criado; nenhum merge automático |
| ORC-24 | Qualidade satisfeita, publicação externa sem autorização | Publicar Issue/PR | BLOCK da publicação; preparar pacote revisável sem alegar publicação |
| ORC-25 | Publicação anterior com resultado desconhecido após interrupção | Repetir publicação | Conferir serviço/histórico antes de reenviar; bloquear repetição se não puder confirmar |
| ORC-26 | Saída produzida; gravação do estado falhou | Iniciar operação dependente | Relatar falha e suspender dependência; não declarar persistência concluída |
| ORC-27 | Feature A bloqueada em H2; tarefa B independente e autorizada | Trabalhar em B | Registrar independência; executar sequencialmente; manter etapa e gate pendente de A |
| ORC-28 | Spec rejeitada por conteúdo, correção conhecida | Reapresentar sem corrigir | RETURN_FOR_REWORK com correções necessárias antes de nova aprovação |
| ORC-29 | Evidência de outro projeto ou aprovador sem responsabilidade definida | Atravessar gate | BLOCK; esclarecer autoridade/escopo; não aceitar evidência como válida |
| ORC-30 | AS-IS documentado, sem causas, objetivos e valor investigados | Verificar Business Context | RETURN_FOR_REWORK por GR-B04/GR-B05; investigar valor e TO-BE sem antecipar arquitetura |

## Critério proposto de aceitação

As sete propostas foram aprovadas; as demais pendências do contrato/protocolo continuam identificadas no pacote de revisão. Executar os casos com registros, corrigir divergências e repetir os afetados. Aceitação manual exige todos os resultados esperados satisfeitos; não comprova enforcement técnico, CI, integração ou confiabilidade de runtime futuro. A rodada assistida e suas limitações estão no relatório de 2026-11-04, sem promover resultados simulados a validação operacional.
