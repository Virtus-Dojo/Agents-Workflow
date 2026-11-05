---
id: BUS-JJ-FICT-001
tipo: contexto-de-negocio
versao: "1.0.0"
status: Em revisão
responsavel: Analista de negócios, papel exercido pelo Codex
fontes: [FONTES-JJ-001, SOL-JJ-FICT-001]
dependencias: [FONTES-JJ-001]
aprovacao:
  marco: H1
  status: Aguardando sua aprovação
  evidencia: null
---
# Exercício da academia — cancelamentos e reposições

## Objetivo e limites

Usar situações fictícias da academia para verificar se o entendimento distingue quando uma reposição é devida e quando essa obrigação termina. Esse é o problema proposto para o exercício: evitar confusão entre motivos de cancelamento, reposições pendentes e obrigações já cumpridas. Não há evidência de que essa confusão já aconteça na academia real, nem medição de perdas, tempo ou frequência.

O professor e os alunos são as pessoas envolvidas. A aula regular é a que estava prevista; a reposição é um novo encontro combinado para cumprir uma obrigação originada por um cancelamento específico. Esse vínculo descreve o entendimento do negócio, sem escolher sistema ou tecnologia.

## Regras recuperadas, separadas dos fatos fictícios

FJ-01 a FJ-07 em fontes.md sustentam: horários regulares corrigidos; escolha de aluno experiente pelo professor quando ele falta; cancelamento com aviso quando não há substituto; reposição obrigatória se o motivo foi ausência do professor sem substituto; ausência de reposição quando o motivo foi indisponibilidade dos próprios alunos; combinação de dia e horário; cumprimento da obrigação após a reposição realizada, mesmo com ausência de alguns alunos.

## Cenário 1 — Falta do professor sem substituto

Situação inventada: numa segunda-feira, o professor não pode ir e nenhum aluno experiente está disponível para conduzir o treino. A aula das 19h30 às 21h é cancelada e os alunos são avisados.

Resultado esperado a partir de FJ-02/FJ-03/FJ-04: existe obrigação de repor essa aula. Combinar uma data futura não significa que a reposição já aconteceu.

Problema a tratar: manter claro qual aula gerou a obrigação e se a reposição ainda está pendente. Não se presume prazo ou penalidade.

## Cenário 2 — Cancelamento por indisponibilidade dos alunos

Situação inventada: numa quinta-feira, os alunos não conseguem comparecer, e a aula é cancelada por esse motivo.

Resultado esperado a partir de FJ-05: esse cancelamento não gera obrigação de reposição.

Problema a tratar: não concluir que toda aula cancelada precisa ser reposta. Não se define quantos alunos ausentes bastam para cancelar, quem decide ou como se consulta o grupo; o cenário começa com o cancelamento já decidido por esse motivo.

## Cenário 3 — Reposição realizada com ausência de alguns alunos

Situação inventada: para repor a aula do cenário 1, o professor combina com os alunos outro dia e horário. A reposição acontece, mas alguns alunos não comparecem.

Resultado esperado a partir de FJ-06/FJ-07: a obrigação daquela aula foi cumprida. A ausência de alguns alunos não gera uma nova reposição individual por esse mesmo motivo.

Problema a tratar: distinguir reposição combinada de reposição realizada e evitar manter a obrigação como pendente depois do encontro ocorrido.

Não se presume o resultado de um encontro sem nenhum aluno, nem o tratamento de uma reposição novamente cancelada.

## Oportunidade e valor a validar

Hipótese: distinguir o motivo do cancelamento e acompanhar o cumprimento da reposição pode reduzir dúvidas e retrabalho. Não há dados para quantificar o ganho nem afirmar que hoje se registra algo incorretamente.

Alternativas de organização a investigar: combinar uma forma clara de comunicar motivo do cancelamento, acompanhar os compromissos de reposição e confirmar que o encontro aconteceu. A escolha depende de entender como isso é feito hoje; não se pressupõe necessidade de software.

Indicadores possíveis, ainda propostos: quantidade de reposições devidas que continuam pendentes e tempo gasto esclarecendo dúvidas sobre reposição. Meta numérica depende de dados reais ou de novas premissas fictícias explicitamente aceitas, não fixadas nesta versão.

## Perguntas ainda abertas

- Como é decidido que a indisponibilidade dos alunos justifica cancelar a aula? Quem decide?
- Como o cancelamento e a data de reposição são comunicados atualmente?
- Existe prazo para repor? Como proceder se a reposição também for cancelada?
- Como se confirma que a reposição aconteceu? E se nenhum aluno comparecer?
- Há evidência de confusão ou perda de acompanhamento na rotina real? Qual seu impacto?

H1 aqui é limitado à adequação dos três cenários e ao entendimento das regras recuperadas. Não valida um problema observado ou benefício medido. As lacunas devem ser resolvidas antes de especificar comportamentos que dependam delas.
