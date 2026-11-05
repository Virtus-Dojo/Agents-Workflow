---
id: EXERCICIO-001
tipo: orientacao
versao: "1.0.0"
status: Em andamento
---
# Execução mínima — solicitações internas

Este exercício usa uma empresa inteiramente fictícia. Nenhum dado pertence à academia. Codex assume os papéis de orquestrador e analista de negócios, um por vez, nesta conversa. Os arquivos e suas leituras são reais; o negócio e suas métricas são inventados para o exercício.

## Etapas em linguagem simples

1. Receber o pedido: registrar o que se quer melhorar e a autorização para este exercício.
2. Entender o negócio: organizar problema, processo atual, evidências fictícias, hipóteses e oportunidades de melhoria.
3. Conferir o documento: verificar fontes, números, pendências e ausência de solução técnica antecipada.
4. Pedir sua aprovação H1: salvar o estado como **Aguardando sua aprovação**, mantendo a etapa **Descoberta do negócio**.
5. Retomar após sua resposta: registrar a decisão com a versão exata. Se aprovar H1, iniciar a especificação funcional; se pedir ajuste, corrigir e reapresentar. H2 e H3 continuam exigidos depois.

## Arquivos para acompanhar

- `solicitacao.md`: pedido e limites autorizados.
- `dados-ficticios.md`: única fonte dos dados inventados do negócio.
- `contexto-negocio.md`: documento BUS-FICT-001 1.0.0 apresentado para H1.
- `estado-inicial.yaml`: registro da inicialização, preservado como histórico.
- `estado.yaml`: situação atual, referências e próxima ação.
- `historico.md`: eventos efetivamente realizados, sem simular aprovação humana.
- `revisao-h1.md`: pacote apresentado para sua decisão.
- `verificacao.md`: resultados da releitura e conferência dos arquivos.

Os estados serão escritos em português. A versão de referência do pacote é 0.1.0, acrescida das sete propostas aprovadas na conversa, listadas no estado; isso não constitui nova release. O formato local do estado é experimental, não schema definitivo. Os arquivos `.yaml` usam a sintaxe JSON, que também é válida em YAML 1.2, para permitir releitura estruturada com ferramenta já disponível.

Para retomar, ler `estado.yaml`, conferir os documentos referenciados e `verificacao.md`, e procurar uma decisão humana real. Não confundir aprovação das sete propostas com H1 deste negócio fictício. Nenhuma aprovação H1 foi recebida na inicialização.

## Situação atual

Exercício substituído pelo da academia de Jiu-Jitsu a pedido do usuário. A revisão H1 deste exemplo está retirada. Arquivos anteriores permanecem como histórico; consultar ../academia-jiujitsu/LEIA-ME.md.
