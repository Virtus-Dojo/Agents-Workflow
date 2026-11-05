---
id: DIRECAO-PRODUTO-001
tipo: direcao-e-plano-de-trabalho
versao: "1.1.0"
status: Em andamento
responsavel: Governança do workflow
fontes: [DEC-001, DEC-003, DEC-006, DEC-007, DIRECIONAMENTO-QUATRO-AGENTES, PACOTE-QUATRO-AGENTES-001]
---
# Direção do produto

## Objetivo definido pelo usuário
Construir Orquestrador, Analista de Negócio, Arquiteto de Software e Desenvolvedor para criar soluções para problemas de negócio. O usuário fala com o Orquestrador; os quatro papéis trocam contexto e respondem uns aos outros. A academia de Jiu-Jitsu é o cenário de teste, separado do núcleo genérico.

## Ordem de trabalho definida pelo usuário
1. **Especificar:** definir comportamento, responsabilidade, entrada, saída, limites e comunicação de cada agente.
2. **Testar:** executar um cenário da academia e observar as trocas e o que é produzido ao final.
3. **Refinar e testar novamente:** corrigir a partir do resultado observado, versionar as mudanças e repetir a execução.

Fonte: mensagens deste chat Codex 01a19e19-e626-70f2-9159-c9dd0a5176d5. O usuário primeiro listou os quatro agentes e depois explicitou a sequência na mensagem iniciada por “Vamos l, você está perdido e vou lhe direcionar”. A versão 1.1.0 substitui o roteiro de cinco marcos proposto anteriormente, sem declarar aprovação de detalhes novos dos contratos.

## Entrega da primeira etapa
O pacote governance/especificacao-quatro-agentes.md reúne os quatro contratos e o contrato de comunicação. A proposta distribui especificação funcional ao Analista de Negócio, planejamento técnico e tarefas ao Arquiteto, implementação e evidências ao Desenvolvedor, coordenação e conferência ao Orquestrador.

H1, H2 e H3 permanecem separados. Especializações começam como papéis lógicos sequenciais conforme DEC-007. Troca de mensagens não requer processos paralelos; a tecnologia de execução será definida na preparação do teste.

## Ponto atual
**Primeira etapa — Em revisão.** Os documentos foram preparados; o comportamento completo ainda depende de revisão e decisão do usuário. A segunda e a terceira etapas ainda não foram iniciadas.

A documentação do Orquestrador é uma candidata 0.3.0; as sete propostas já aprovadas foram preservadas. Sua versão 0.2.0 foi mantida em agents/historico/orchestrator-0.2.0.md. Os outros três contratos e o contrato de comunicação estão em 0.1.0.

Os 30 cenários textuais anteriores, a leitura da planilha e os arquivos do exercício anterior são insumos e histórico. Não equivalem ao teste integrado definido nesta sequência.

## Critério de chegada
Depois de revisar os contratos, executar uma melhoria delimitada da academia pelas etapas aprovadas, com comunicação rastreável, decisões humanas e resultado demonstrável. Quando houver implementação, verificar o código e seus critérios de aceitação; texto, arquivo salvo ou simulação não comprovam software funcionando.

## Próximo passo
Revisar os comportamentos do pacote dos quatro agentes e resolver os pontos de responsabilidade e comunicação. Não avançar descoberta/implementação do cenário como substituto dessa revisão.
