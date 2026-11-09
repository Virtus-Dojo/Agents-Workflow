---
id: BUS-JJ-REAL-001
tipo: contexto-de-negocio
versao: "2.0.0"
data_consolidacao: "2026-11-08"
status: Consolidado para conferência do usuário
responsavel: Analista de negócios, papel exercido pelo Codex
fontes: [HISTORICO-FONTE-JJ-001, PLANILHA-VIRTUS-001, ANALISE-XLSX-JJ-001, CONVERSA-DE-DESCOBERTA-ATE-2026-11-08]
aprovacao:
  marco: H1
  status: Aguardando conferência do usuário; não aprovado formalmente
  evidencia: null
---

# Virtus Dojo Jiu-Jitsu — contexto do negócio real

## 1. Finalidade e fontes

Consolidar as regras confirmadas pelo usuário para conferência e posterior elaboração da solução em outra pasta. O documento distingue operação atual e comportamento desejado. Não define arquitetura, tecnologia ou autorização de implantação. A consolidação não equivale à aprovação formal do usuário.

Fontes:

- Conversa histórica recuperada, transcrita em `historico-consultado.md`, e esclarecimentos deste chat até 08/11/2026. Respostas posteriores prevalecem sobre entendimentos anteriores corrigidos.
- `Aluno Virtus.xlsx`, em `C:/Users/wwwpe/Downloads/Aluno Virtus.xlsx`, e inventário em `analise-planilha.md`.
- Site: https://virtusdojojiujitsu.com.br/. Os comportamentos de agendamento abaixo foram informados pelo usuário; o conteúdo do site não pôde ser inspecionado nesta consulta.
- Referência de graduação: CBJJ/IBJJF, https://cbjj.com.br/graduation-system e https://ibjjf.com/graduation-system. A aplicação interna e as exceções confirmadas estão descritas abaixo; controle interno e reconhecimento federativo não são equivalentes.

**A planilha serve somente como fonte dos tipos de dados que a academia utiliza e guarda. Seus números, fórmulas, estrutura, ajustes, cores e inconsistências não são regras da nova solução. O trabalho será reformulado do zero.** Não se presume migração automática de dados ou fórmulas.

Os exercícios fictícios da pasta são históricos, não evidências de problemas reais. Apesar do nome `execucoes-ficticias`, este documento trata do negócio real.

## 2. Objetivos e problemas atuais

Devolver tempo ao empresário/professor reduzindo a alimentação manual da planilha, consultas para responder aos alunos e esforço de organização da empresa. Melhorar a experiência dos alunos com visibilidade de evolução e estímulo ao engajamento.

Problemas relatados:

- O professor alimenta a planilha e responde perguntas cujas informações estão nela.
- Alunos perguntam quantas aulas fizeram e quanto falta para graus/faixas. Na nova solução, o progresso principal solicitado é de aulas restantes para a próxima faixa.
- Em treinos com substitutos, o professor identifica participantes por fotos. Alunos que saem antes podem não aparecer. O repasse complementar é esquecido e muitas dessas presenças acabam não registradas.
- Quando o professor conduz, normalmente sabe quem participou e não relata o mesmo problema no lançamento posterior.
- A organização financeira também consome trabalho, mas seu detalhamento foi adiado.

Não foram quantificados horas gastas, frequência de omissões, perdas financeiras nem metas de engajamento. Não há benefícios numéricos prometidos.

## 3. Primeira versão e responsabilidades

- Atendimento a partir de **12 anos**, incluindo 12–15 anos, 16–17 anos e adultos.
- Perfis: professor, aluno e pais/responsáveis. Sem outros funcionários ou administradores.
- Experimentais e visitantes não têm acesso antes de matrícula confirmada e registro no sistema.
- Núcleo definido: cadastro, matrícula, responsáveis, presença, evolução, metas, graduação, calendário, cancelamentos e reposições.
- Financeiro pendente. Consulta de mensalidades, vencimentos e pagamentos está confirmada, mas as regras do módulo ainda não estão especificadas.

Rotinas administrativas podem ser automatizadas sem exigir o professor em tudo. Permanecem as exceções expressas: confirmação de primeira matrícula e reativação, correção de nascimento, confirmação de presença e decisões de aula/graduação. Preservam-se as automações específicas, como calendário e estados de progresso.

## 4. Aulas, espaço e substituição

O negócio aluga espaço dentro de outra academia. Há um professor. Todos participam da mesma aula no mesmo tatame. O professor divide iniciantes e mais experientes por experiência e nível técnico durante o treino, com instruções específicas. A divisão pode mudar a cada aula; não há grupo fixo por aluno.

| Dias | Horário regular |
|---|---|
| Segunda, terça, quinta e sexta | 19h30–21h |
| Sábado | 8h–11h |

Há uma única aula regular por dia, inclusive no sábado. O sistema cria automaticamente o calendário conforme dias e horários configurados. Feriados não cancelam aulas automaticamente: elas continuam previstas até decisão do professor.

Na ausência do professor, ele escolhe um aluno experiente para conduzir o treino. O substituto não assume o registro de presenças. O treino conta normalmente para graduação, mediante presença confirmada.

### Cancelamentos e reposições

O professor deve informar o motivo do cancelamento.

| Motivo | Reposição |
|---|---|
| Ausência do professor sem substituto | Obrigatória |
| Indisponibilidade dos alunos para comparecer | Não há |
| Outros motivos, como feriado ou indisponibilidade do espaço | Professor decide |

Professor combina dia/horário com os alunos; participação é opcional. A reposição fica vinculada à aula cancelada que gerou a obrigação.

Cancelar uma reposição mantém a obrigação pendente até outra acontecer. Se o professor estiver presente e disponível para conduzi-la, a obrigação é cumprida, mesmo que alguns ou todos os alunos não compareçam. O professor marca o cumprimento no sistema para encerrar a obrigação.

Cancelamento de aula e agendamento de reposição geram notificações automáticas a alunos e responsáveis com acesso. A primeira versão usa avisos no sistema, e-mail e WhatsApp. A distribuição exata por canal/destinatário ainda não foi definida.

## 5. Presenças

### Registro, recusa e revisão

- Atualmente o professor registra depois de cada aula. Com substituto, usa fotos e confirma com quem conduziu quando alguém não aparece.
- O professor pode lançar diretamente uma presença já confirmada, sem depender do aluno.
- Aluno ativo pode informar participação em qualquer aula passada, sem prazo limite. Só conta após confirmação do professor.
- Responsáveis podem informar participação do menor nas mesmas condições.
- Não há duração mínima de participação. O professor decide se a participação foi suficiente, inclusive com atraso ou saída antecipada.
- Sábado vale uma presença, apesar das três horas. Reposição e treino com substituto também valem uma presença por aula realizada e confirmada.
- O sistema impede presenças duplicadas do mesmo aluno na mesma aula, independentemente da origem.
- O professor pode corrigir presença indevida, retirando-a da contagem.
- Aluno vê participações pendentes separadas das confirmadas. Recusa exige motivo do professor, visível ao aluno.
- Aluno ou responsável pode solicitar nova análise de recusa com justificativa obrigatória. A decisão final continua com o professor.

As permissões de solicitação/alteração acima se aplicam a alunos ativos. Acesso de inativos é de consulta, com exceções de retorno da seção 11.

### Contagens por grau e por faixa

| Contagem | Regra |
|---|---|
| Próxima faixa | Todas as presenças confirmadas da faixa atual; não zera nos graus |
| Próximo grau/etapa | Somente aulas posteriores ao dia de recebimento do último grau |

Se o professor adiar a concessão de um grau, aulas durante a espera ficam no histórico e no total da faixa, mas não são carregadas para o grau seguinte. A regra vale também do 4º grau até a troca de faixa.

**A data da aula determina a etapa, independentemente da data da confirmação.** Presença antiga confirmada depois fica no histórico da etapa correspondente.

A aula do dia da concessão pertence à etapa concluída. No dia da troca de faixa, pertence à faixa anterior. A nova etapa/faixa recebe aulas do dia seguinte em diante. Todo o histórico é preservado.

## 6. Metas, graduação e avaliação

Graduação considera aulas, nível técnico, evolução e conduta. A decisão é do professor; atingir meta não gera promoção automática.

### Metas configuradas do zero

- Professor define uma meta padrão de aulas por faixa antes de exibi-la aos alunos.
- Pode ajustar individualmente conforme histórico/evolução. Quantidade de aulas é referência flexível da academia, não mínimo federativo.
- Aluno vê a meta vigente e aulas restantes para a próxima faixa, atualizadas após ajustes.
- Alterar padrão da faixa afeta também alunos já nela, mantendo as metas individuais previamente ajustadas.
- Sem configuração, exibir “Meta de aulas ainda não definida”, mantendo consulta de presença/histórico. Não presumir zero ou copiar números da planilha.
- Intervalos de graus são flexíveis. Um grau por semestre na azul e intervalos como quatro meses na roxa foram exemplos, não regras fechadas.
- Caminho habitual exige quatro graus antes da faixa seguinte, inclusive de 12 a 15 anos. Há exceção de experiência anterior descrita na seção 7.

### Tempo na faixa

O marco interno é a data de recebimento da faixa, inclusive em outra academia. Pausas e períodos sem treino não interrompem o tempo. O professor considera afastamentos ao avaliar prontidão.

| Situação | Regra confirmada |
|---|---|
| Branca | Um ano é referência; professor pode conceder azul antes |
| Azul adulto, regra geral | Dois anos, ressalvadas exceções aplicáveis |
| Roxa adulto, regra geral | Um ano e seis meses, ressalvadas exceções |
| Marrom, regra geral | Um ano, ressalvadas exceções |
| Dos 12 aos 15 anos | Sem mínimo obrigatório; metas e avaliação |
| Azul recebida aos 16–17 | Sem mínimo, inclusive após completar 18 |
| Roxa recebida no juvenil | Marrom só a partir dos 18; dispensa do mínimo de um ano e meio |
| Azul no juvenil, roxa recebida aos 18 ou depois | Mínimo de um ano na roxa antes da marrom |

A academia também aplica dispensas/reduções CBJJ ligadas ao histórico infantil e títulos mundiais. Basta relato validado pelo professor, sem comprovação obrigatória. A matriz completa dessas exceções e idades deve ser anexada e versionada antes de automatização; não inferir regras ausentes.

Professor flexibiliza aulas, mas respeita o mínimo de tempo aplicável, consideradas as dispensas válidas. O marco interno de recebimento não substitui requisitos próprios de registro/reconhecimento federativo.

### Estados da próxima faixa

| Condição | Comportamento |
|---|---|
| Meta e mínimo de tempo aplicável cumpridos | Automaticamente “Aguardando avaliação do professor” |
| Mudança de meta faz cumprir critérios | Mesma entrada automática, exceto “Em desenvolvimento” |
| Correção ou aumento da meta faz deixar de cumprir critérios | Sai da espera de avaliação e volta ao acompanhamento de progresso |
| Professor flexibiliza aulas | Pode encaminhar manualmente à avaliação, respeitando mínimo aplicável |
| Sem meta definida | Só professor encaminha; exceção de transição por idade permanece |
| Professor avalia que ainda não está pronto | “Em desenvolvimento” até nova avaliação iniciada pelo professor |

Aluno vê mínimo de tempo aplicável e quanto falta. “Em desenvolvimento” não muda automaticamente só por cumprir metas. Apenas professor inicia nova avaliação e muda esse estado, ressalvada transição por idade e sua correção.

Se não conceder a próxima faixa, professor informa o que desenvolver. Registrar o conteúdo da orientação é opcional; no mínimo registra que comunicou o motivo ao aluno. Conteúdo registrado fica disponível para consulta posterior. O aluno não solicita pelo sistema nova avaliação de faixa; isso não se confunde com nova análise de presença recusada.

## 7. Alunos com experiência anterior

Professor conversa com o aluno e registra histórico relevante de faixas/graus, recebimento da faixa, tempo treinado fora e interrupções. Graus anteriores são mantidos. Histórico subsidia avaliação e exceções federativas.

Não se atribui quantidade de aulas a treinos externos. Contagem local de grau/faixa começa com os treinos na academia, incluindo visitas/experimentais confirmadas conforme seção 10. Começa com meta padrão da faixa, ajustável individualmente na entrada.

Para graduação atrasada, professor pode fazer troca direta de faixa ou conceder graus individualmente em intervalos menores até completar quatro. **Não está confirmada concessão de vários graus de uma vez.** Troca direta é exceção ao percurso habitual, respeitando tempo/idade aplicáveis.

## 8. Idades e transição

Dos 12 aos 15 anos: branca e famílias cinza, amarela, laranja e verde, com variantes com branco, lisa e com preto. Quatro graus por faixa, metas ajustáveis e sem mínimo de tempo.

O marco interno da transição é o aniversário de 16 anos, não o início do ano:

| Origem | Possibilidade |
|---|---|
| Branca | Permanecer na branca |
| Cinza/amarela/laranja e variantes | Azul |
| Verde e variantes | Azul ou roxa, conforme professor |

Nas famílias cinza/amarela/laranja/verde, aniversário de 16 gera automaticamente “Aguardando avaliação do professor para transição”, independentemente de meta/graus e mesmo sobre “Em desenvolvimento”. Professor define data efetiva da troca.

Presenças continuam na faixa de origem até o dia efetivo da transição, inclusive. Se correção de nascimento mostrar idade inferior a 16, retira-se automaticamente o estado de transição; restaura “Em desenvolvimento” se esse era o anterior.

## 9. Datas, correções e histórico de alterações

Professor registra nova faixa e data real da graduação; pode registrar graus/faixas retroativos e consultar o aluno para recuperar datas. Se exata desconhecida, admite estimativa definida pelo professor em conversa com aluno, identificada como estimativa.

Data estimada vale normalmente para tempo e separação das presenças, preservando indicação. Corrigir data da faixa recalcula tempo e redistribui presenças entre faixas. Corrigir data de grau redistribui presenças entre etapas. Aula do dia da concessão permanece na etapa anterior.

Se correção revelar graduação sem idade/tempo mínimo exigido, manter graduação e avisar professor; nunca desfazer automaticamente. Para resolver, professor registra decisão e justificativa no histórico. Isso não autoriza ignorar mínimos nas próximas graduações.

Professor consulta alterações de presenças, metas individuais, datas de graus/faixas e nascimento, sempre com valor anterior, novo e data/momento da alteração. Outros campos de auditoria não foram definidos.

## 10. Experimentais, visitantes e site

Ambos agendam previamente pelo site. Segundo usuário, site agenda/confirma automaticamente, insere compromisso nas agendas de professor e pessoa e envia e-mail a ambos. Pessoa informa se nunca treinou, já treinou ou treina atualmente.

- Chegada 30 minutos antes da aula: 19h em dias úteis de treino e 7h30 sábado.
- Recepção/orientações nesse período, depois participação na aula regular.
- Sem limite atualmente definido de pessoas agendadas por dia.
- Uma experimental gratuita por pessoa; professor pode autorizar mais.
- Falta ao agendamento não consome direito: pode remarcar.
- Visitante externo treina gratuitamente, sem limite definido de visitas, cada retorno com novo agendamento.
- Sem acesso ao sistema antes de matrícula confirmada e registro.

Na matrícula, professor informa manualmente início na data da experimental; esse ato gera automaticamente uma presença confirmada naquela aula. Pode lançar manualmente outras experimentais autorizadas/visitas anteriores. Todas as realizadas e confirmadas contam após matrícula, na etapa correspondente e sem duplicação. A data de início não gera presenças para todo o intervalo.

Não foi decidido reconstruir o site nem como integrar seu agendamento à nova solução.

## 11. Cadastro, matrícula e inativação

### Cadastro e confirmação

Obrigatórios: nome completo, nascimento, telefone/WhatsApp, e-mail, endereço, contato de emergência. Para menor sem telefone/e-mail próprios, esses contatos pessoais são opcionais, preservados os obrigatórios do responsável.

Emergência exige nome completo, telefone/WhatsApp e parentesco. Pode selecionar um dos pais cadastrados sem redigitação.

Para menores: nome completo, telefone/WhatsApp, e-mail e parentesco do responsável. Contatos próprios do menor não substituem esses dados. Cadastro fica incompleto enquanto faltarem dados obrigatórios do responsável.

**Primeira matrícula e reativação exigem cadastro completo, plano escolhido e confirmação do professor.** Essa decisão mais recente substitui a anterior confirmação automática de matrícula.

Aluno e responsáveis podem atualizar cadastro sem aprovação, exceto nascimento, que depende de confirmação do professor e fica no histórico. Ao confirmar, recalculam-se regras de idade, incluindo transição aos 16 e encerramento de acesso dos pais aos 18. Se correção mostrar menor de 18, restaura acesso dos pais automaticamente; graduações já feitas seguem análise de inconsistência sem reversão automática.

### Pausa, saída e retorno

| Ação | Regra |
|---|---|
| Pausa | Automática na data informada pelo aluno, sem professor |
| Encerrar pausa | Pelo sistema antes de voltar a treinar, sem professor |
| Cancelar matrícula | Direto no sistema, notificando professor |
| Reativar após saída | Solicitação, plano escolhido e confirmação do professor |

Pais/responsáveis também realizam essas ações para menores com as mesmas exigências. Cadastro e histórico são preservados.

Durante pausa ou após cancelamento, acesso fica restrito a consultar tudo que já foi registrado. Sem alterações, registros ou solicitações, inclusive presenças antigas. Exceções: encerrar pausa ou solicitar reativação. Novos treinos exigem retorno à situação ativa.

## 12. Acesso de aluno e responsáveis

Aluno consulta somente seus próprios dados: histórico de aulas, graus, faixas e datas, progresso, pendências/recusas e motivos. Consulta financeira própria está confirmada, com módulo pendente.

Menor possui acesso próprio, além do familiar. Sem contatos próprios, usa nome de usuário e senha. Professor e responsáveis autorizados podem criar/recuperar esse acesso.

### Acesso familiar

- Pais compartilham um único login; isso substitui acessos separados de pai/mãe discutidos antes.
- Um login pode acompanhar vários filhos vinculados.
- Permite consultar presença/evolução, mensalidades/vencimentos/pagamentos dos menores; informar presença, pedir revisão com justificativa e realizar ações permitidas de matrícula.
- Confirmação vai ao e-mail ou WhatsApp informado. Basta confirmar o contato de um dos pais para ativar login compartilhado, sem aprovação manual do professor.
- No aniversário de 18, encerra acesso apenas ao filho que atingiu maioridade; mantém outros filhos menores.
- Responsável não pode encerrar voluntariamente o próprio acesso antes dos 18.

### Substituição

Aluno solicita alteração do responsável pelo sistema, sem professor. Novo responsável confirma contato. Até confirmação, pedido fica pendente e anterior mantém acesso. Ao confirmar, substituição termina, acesso anterior àquele aluno é encerrado e anterior é notificado. Outros filhos mantêm seus vínculos.

Aluno pode cancelar pedido pendente, preservando responsável atual. Isso não equivale ao encerramento voluntário pelo responsável, que não é permitido.

## 13. Financeiro — pendente por decisão do usuário

Confirmado: aluno e responsáveis consultam mensalidades, vencimentos e pagamentos dos alunos aos quais têm acesso. Reduzir esforço financeiro do professor é objetivo. O restante será informado depois.

Ainda indefinidos: planos/preços, vigência, vencimento, pagamento/baixa, descontos, bolsas/isenções, parcelamento, inadimplência, cobrança, efeitos de pausa/cancelamento/retorno, estorno e gestão de receitas/despesas. Não inferir regras das fórmulas da planilha.

Plano escolhido é requisito já confirmado para matrícula/reativação. Catálogo mínimo deve ser definido antes de liberar esse fluxo, ainda que o financeiro completo seja posterior.

Planilha registra também vendas de materiais, compras e controles financeiros. A existência desses dados não aprova automaticamente tais módulos para a primeira versão.

## 14. Pendências delimitadas

Não preencher silenciosamente estas lacunas na elaboração da solução:

1. Financeiro e catálogo mínimo de planos (seção 13).
2. Matriz versionada completa da CBJJ/IBJJF: idades, histórico infantil, títulos, faixas superiores e exceções, antes de automatização. Preservar os marcos internos explicitamente confirmados.
3. Cancelamento por indisponibilidade dos alunos: quórum/consulta não definidos; não automatizar decisão por suposição.
4. Integração com site e agendas, identificação das pessoas agendadas sem acesso e preservação do fluxo existente.
5. Distribuição exata de notificações por canal/destinatário, incluindo inativos, e regras de falha/reenvio. Os três canais foram pedidos, mas não desenhados.
6. Efeito de corrigir a data de início sobre presença automática da experimental; não confundir com correção de graduação.
7. Autenticação, recuperação, integridade de datas, duplicidade de pessoas e vínculo do login familiar: detalhamento de solução ainda necessário, respeitando permissões confirmadas.
8. Valores das metas iniciais por faixa, a configurar pelo professor. Não importar números da planilha nem supor quantidade fixa por grau.
9. Indicadores e valores de sucesso: tempo poupado, confiabilidade das presenças e engajamento ainda sem referência numérica aprovada.

## 15. Correções consolidadas e estado da entrega

Prevalecem sobre versões anteriores:

- Sexta-feira incluída; uma aula por dia.
- Problemas e objetivos agora conhecidos; antiga pendência de descobrir a dor está superada.
- Planilha como fonte de tipos de dados, sem herdar regras/fórmulas.
- Grau reinicia contagem da etapa; faixa acumula todas as aulas confirmadas na faixa.
- Metas de aulas flexíveis; mínimos de tempo aplicáveis obrigatórios, com dispensas válidas.
- Um ano na branca é referência, não mínimo.
- Primeira versão a partir dos 12 anos.
- Login compartilhado dos pais, com múltiplos filhos; validação por contato, não aprovação do professor para acesso familiar.
- Primeira matrícula e reativação dependem do professor.
- Inativos em consulta, exceto ações de retorno.

Versão 2.0.0 consolidada para conferência, sem aprovação formal. Versão 1.1.0 preservada em `contexto-negocio-real-v1.1.0.md`; versão 1.0.0 permanece disponível. Financeiro explicitamente pendente. Aprovação de exercícios fictícios não é aprovação deste contexto.

Próximo passo: usuário revisar esta consolidação. Após conferência, utilizar regras confirmadas na elaboração da solução em outra pasta, carregando as pendências sem inventar respostas.
