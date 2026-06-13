# Relatório — Assistente 1 · v1 (pesquisa inicial)

- **Ferramenta:** Claude Sonnet 4.6 (Deep Research)
- **Data:** 2026-06-13
- **Prompt usado:** ver `A_meta_prompt.md`
- **Link da conversa:** https://claude.ai/public/artifacts/1bd98614-5021-4082-8c51-41dd400a37b3

# Relatório de Insumos para Service Blueprint AS-IS — Atendimento ao Seguro-Desemprego e a hipótese da "URA da Caixa"

## 1. Resumo executivo

**Achado central:** A hipótese de uma "URA da Caixa específica para Seguro-Desemprego" NÃO se confirma em fonte pública oficial. O que existe, comprovadamente, são dois canais telefônicos distintos com responsabilidades separadas: (a) a **Central Alô Trabalho 158**, do Ministério do Trabalho e Emprego (MTE), responsável por informação, orientação, agendamento e suporte sobre habilitação/concessão/recurso do benefício; e (b) o **Atendimento CAIXA ao Cidadão 0800 726 0207**, da Caixa Econômica Federal, que trata "PIS, Benefícios Sociais, FGTS e Cartão Social" — onde o seguro-desemprego aparece apenas como um dos assuntos genéricos de "benefícios sociais", relacionado a **pagamento/saque/crédito**, e não à habilitação.

**Confirmações principais:**
- A Caixa atua como **Agente Pagador** do seguro-desemprego (recursos do FAT, Lei nº 7.998/1990); não habilita, defere, indefere nem julga recurso.
- A habilitação/concessão é do **MTE**, com triagem automatizada operada pela **DATAPREV** (cruzamento com CNIS, CAGED, eSocial e base CAIXA).
- A Caixa **possui** infraestrutura de contact center/telesserviços com servidores de URA (comprovado em Acórdão TCU 1151/2018-Plenário), mas **não há documentação pública** da árvore de decisão/menu dessa URA nem de opção nominal "seguro-desemprego".

**Lacunas críticas para o blueprint:** menu/árvore da URA da Caixa; existência de transbordo específico para seguro-desemprego; uso de ASR/NLP/bot no fluxo de voz; integração entre canal telefônico da Caixa e sistemas de retaguarda do seguro-desemprego; scripts e SLAs; dados de fila/abandono.

**Implicação para o desenho AS-IS:** O blueprint deve ser desenhado com DUAS raias institucionais paralelas (MTE/158 e Caixa/0800), explicitando a "zona de fronteira" onde ocorre o "jogo de empurra" — fenômeno documentado em reclamações reais (cidadão direcionado de um canal a outro). A camada telefônica da Caixa para seguro-desemprego deve ser representada majoritariamente como zona de inferência/lacuna, não como fato.

## 2. Delimitação do objeto

### 2.1 Comprovadamente MTE / Central 158
- A Central Alô Trabalho 158 é o canal oficial do MTE para informações sobre seguro-desemprego, abono salarial, CTPS Digital, CAGED e legislação trabalhista. Gerida pela Ouvidoria-Geral do MTE.
- **Horário:** conforme nota oficial do MTE (gov.br, publicada em 21/03/2024): "o atendimento da Central Alô Trabalho 158 teve alterado seu horário de funcionamento a partir do dia 20 de março (quarta-feira) passando a funcionar de 7h às 22h, de segunda-feira a sábado, ampliando seu horário de atendimento que era de 7h às 19h." Gratuita de telefone fixo; chamadas de celular podem ser tarifadas.
- Atendimento eletrônico (menu pré-gravado) com opção de transbordo a atendente humano: "O atendimento eletrônico é realizado por meio de informações pré-gravadas onde o usuário utiliza um menu para escolher a opção desejada. Caso não encontre a informação, o cidadão terá a opção de falar com um atendente."
- **Capacidade da central:** segundo dados institucionais do MTE divulgados na inauguração (30/04/2015, via Legisweb), a Central 158 "pode receber até 26 mil ligações diárias e 780 mil por mês" e opera com "157 Posições de Atendimento (PAs), operando simultaneamente 12 horas por dia"; em três anos e meio somou 21.614.493 atendimentos.
- **Volume de demanda por assunto:** nota do TRT-7/MTE sobre a inauguração da Central 158 (abril/2015) registrava que "as informações mais procuradas pelos cidadãos através da Central são sobre seguro-desemprego, com mais de 70% do total de ligações recebidas... Diariamente, em média 36 mil pessoas procuram o 158". Dado mais recente diverge: no 1º semestre de 2025, o Abono Salarial liderou com 48% e o Seguro-Desemprego respondeu por 23% das demandas (Agência Gov, ago/2025, 1.726.914 atendimentos) — o que sinaliza ao analista do blueprint que o peso relativo do seguro-desemprego na URA do 158 oscila por sazonalidade e calendário de outros benefícios.
- O 158 também faz **agendamento** de atendimento presencial nas Superintendências Regionais do Trabalho (SRT) e é canal para empregado doméstico (que não solicita pelo portal).
- A página oficial gov.br "Solicitar o Seguro-Desemprego" (última modificação 15/12/2025) lista o telefone 158 como canal de prestação; legislação citada: Lei nº 7.998/1990 e Resolução CODEFAT nº 957/2022.

### 2.2 Comprovadamente Caixa / pagamento
- A Caixa é **Agente Pagador** (Lei nº 7.998/1990; a operacionalização e o pagamento das parcelas competem aos bancos oficiais federais). Não habilita o benefício.
- Canal telefônico: **0800 726 0207** ("Atendimento CAIXA ao Cidadão"), descrito no site oficial como "Atendimento referente a PIS, Benefícios Sociais, FGTS e Cartão Social". Atendimento eletrônico 24h/7; atendimento humano de segunda a sexta, das 8h às 21h, e sábados das 10h às 16h. Lançado em 2012 com cerca de 1.500 operadores (gerente nacional de Telesserviços citado à época: Ricardo Vieira; expectativa de 250 mil ligações/dia).
- Formas de pagamento: crédito em conta indicada (Caixa ou outro banco via TED); crédito em conta Caixa individual selecionada automaticamente; conta Poupança Social Digital (aberta automaticamente, movimentada pelo app CAIXA Tem, limite mensal de R$ 5.000,00, regida pela Lei nº 14.075/2020); saque com Cartão Cidadão e senha em autoatendimento, lotéricas e Correspondentes CAIXA Aqui; saque em agência com documento.
- Apps Caixa relacionados: CAIXA Tem, Benefícios Sociais CAIXA, CAIXA Trabalhador.
- Outros canais Caixa: SAC 0800 726 0101; Ouvidoria 0800 725 7474; atendimento PcD auditiva 0800 726 2492; WhatsApp 0800 104 0104.

### 2.3 Lacuna sobre "URA da Caixa para Seguro-Desemprego"
- **Comprovado:** a Caixa tem solução de contact center/telesserviços com servidores de URA. O Acórdão TCU 1151/2018-Plenário (sessão de 23/05/2018, rel. Min. José Múcio Monteiro), referente à Representação sobre o Pregão Eletrônico 59/7066-2017-Gilog/BR (vencedora **CTIS Tecnologia S.A.**, proposta de R$ 11.398.497,84; Contrato 8629/2017), trata da "contratação de empresa para a prestação de serviço de suporte, operação, monitoração e manutenção... para a solução de contact center da Caixa – telesserviços". O documento cita verbatim a existência de "servidores de contact centers, servidores de gravação, servidores de URA" nas unidades de atendimento, as **CERATs** (Centrais de Relacionamento) e o "projeto denominado Centralização dos Telesserviços" em Data Centers (CTC – Brasília/DF e CEPTISP – Osasco/SP). Há também o Pregão Eletrônico 013/5688-2024 (processo 5688.01.1522.0/2023), cujo objeto é atendimento multisites/multimeios por 12 meses.
- **NÃO comprovado (lacuna):** menu/árvore de decisão da URA, opção nominal "seguro-desemprego", existência de ASR/NLP/voicebot, regras de transbordo, integração com sistemas do seguro-desemprego, e a empresa atualmente operadora (homologação do Pregão 013/5688-2024 não localizada). Nenhum edital/contrato 2020–2025 de IA de voz para o 0800 da Caixa foi localizado.

### 2.4 Como isso afeta o blueprint
O blueprint AS-IS deve refletir: (1) fronteira institucional dupla; (2) o canal de pagamento da Caixa como majoritariamente informativo/consultivo (status de parcela, saque), não resolutivo da habilitação; (3) marcação explícita de níveis de evidência em cada elemento do frontstage/backstage telefônico da Caixa.

## 3. Tabela da jornada do cidadão

| ID | Etapa | Objetivo do cidadão | Canal | Ação do cidadão | Resposta percebida | Evidência física/digital | Resultado possível | Fonte | Nível de evidência |
|----|-------|--------------------|-------|-----------------|-------------------|--------------------------|-------------------|-------|---------------------|
| J1 | Dispensa sem justa causa | Obter requerimento | Empregador / Empregador Web | Recebe formulário (dígitos iniciais "77") | Documento de Requerimento do Seguro-Desemprego | Requerimento físico/digital, TRCT | Tem ou não o requerimento | gov.br; trabalho.pr.gov.br | Comprovado |
| J2 | Busca de informação | Saber se tem direito | 158 / gov.br / app CTPS Digital / busca web | Liga 158 ou consulta portal | Menu pré-gravado; orientação | Áudio URA 158; tela FAQ | Orientação | gov.br; Agência Gov | Comprovado |
| J3 | Acesso ao canal de solicitação | Requerer benefício | gov.br / app CTPS Digital / SINE Fácil | Login gov.br (Bronze/Prata/Ouro) | Tela de login e serviço | Conta gov.br | Autenticado ou bloqueado | gov.br (serviço) | Comprovado |
| J4 | Identificação/autenticação | Provar identidade | gov.br | Informa CPF/senha; nº do requerimento | Validação | Token gov.br | Prossegue ou falha | gov.br | Comprovado |
| J5 | Solicitação | Dar entrada | gov.br / app | Informa nº requerimento; aceita termos | "Solicitação realizada com sucesso" + parcelas | Tela de confirmação; termo de aceite | Habilitado/notificado | gov.br FAQ | Comprovado |
| J6 | Verificação automática | — (bastidor) | DATAPREV/sistemas | Nenhuma (automático) | Resultado imediato | — | Deferido/indeferido/exigência | dataprev.gov.br; IBGE metadados | Comprovado |
| J7 | Resultado | Saber decisão | gov.br / app | Consulta status | Notificação (deferimento/indeferimento/pendência) | Notificação digital | 5 desfechos possíveis | Res. CODEFAT 957/2022 | Comprovado |
| J8 | Acompanhar parcelas | Ver datas/valores | app CTPS Digital / gov.br / 158 / 0800 Caixa | Consulta calendário | Quantidade e datas de parcelas | Tela de parcelas | Acompanhamento | gov.br; Caixa | Comprovado |
| J9 | Recebimento/pagamento | Receber dinheiro | Conta / Caixa Tem / lotérica / agência | Verifica conta; saca | Crédito ou "parcela emitida não creditada" | Extrato; comprovante saque | Pago ou falha de crédito | Caixa; gov.br FAQ | Comprovado |
| J10 | Falha de crédito | Resolver não-pagamento | 0800 726 0207 / agência Caixa / 158 | Liga, vai à agência | Orientação; "ir à agência" | Protocolo (não documentado) | Resolução, orientação ou empurra | Reclame Aqui; Caixa | Evidência indireta |
| J11 | Recurso | Reverter indeferimento | gov.br / app / SRT presencial | Cadastra recurso; anexa docs | Análise; resultado | Tela de recurso; anexos JPG/PNG/PDF ≤1MB | Deferido/indeferido | gov.br FAQ; Res. 957/2022 | Comprovado |
| J12 | Presencialização | Corrigir divergência | SRT / SINE (agendado pelo 158) | Comparece com documentos | Atendimento humano | Senha declaratória; protocolo | Correção ou nova pendência | gov.br FAQ; Res. 957/2022 | Comprovado |
| J13 | Manifestação | Reclamar/denunciar | Fala.BR / Ouvidoria MTE / Ouvidoria Caixa 0800 725 7474 | Registra manifestação | Protocolo; resposta em até 30 dias | Protocolo Fala.BR | Resposta/encaminhamento | Lei 13.460/2017; CGU | Comprovado |

## 4. Tabela de processos de bastidor

| Etapa relacionada | Ator de bastidor | Tipo | Atividade interna | Sistema/base usada | Entrada | Saída | Visível ao cidadão? | Fonte | Nível de evidência |
|-------------------|------------------|------|-------------------|-------------------|---------|-------|---------------------|-------|---------------------|
| J1 | Empregador | Humano/sistema | Comunicação de dispensa; emissão de requerimento | Empregador Web / eSocial | Dados rescisão | Requerimento | Não | gov.br; Sebrae | Comprovado |
| J5-J6 | DATAPREV | IA/sistema | Triagem automatizada e habilitação | Sistema SD, CNIS, CAGED, eSocial, base CAIXA | RSD + dados | Deferimento/notificação | Não | dataprev.gov.br; IBGE | Comprovado |
| J6 | MTE/CGSAP | Humano | Análise de recursos centralizada | BGSD | Recurso | Decisão | Não | IBGE metadados; CGU | Comprovado |
| J7 | MTE | Sistema | Geração de notificação digital | Sistema SD | Resultado | Notificação | Parcialmente | Res. 957/2022 | Comprovado |
| J9 | Caixa (Agente Pagador) | Sistema/fundo | Crédito de parcelas; abertura de Poupança Social Digital | Sistemas Caixa; FAT | Ordem de pagamento | Crédito/saque | Parcialmente | Caixa; Lei 7.998/90 | Comprovado |
| J10 | Caixa CERAT/contact center | Humano/sistema | Atendimento telefônico de pagamento | URA + DAC/CTI; telesserviços | Ligação | Informação/orientação | Sim (voz) | Acórdão TCU 1151/2018 | Evidência indireta |
| J10 | Caixa URA | IA/sistema | Roteamento/triagem eletrônica | Servidores URA | Ligação | Menu/encaminhamento | Sim (voz) | TCU; inferência arquitetura | Inferido |
| J11 | MTE Secretaria de Trabalho | Humano | Julgamento do recurso (instância única) | Sistema SD | Recurso | Deferimento/indeferimento | Não | Res. 957/2022 art. 28 | Comprovado |
| J12 | SRT/SINE | Humano | Correção de dados; recepção presencial | SAA/sistemas MTE | Documentos | Correção | Sim | gov.br FAQ | Comprovado |
| J13 | Ouvidorias (MTE/Caixa/CGU) | Humano | Tratamento de manifestação | Fala.BR | Manifestação | Resposta | Parcialmente | Lei 13.460/2017 | Comprovado |
| Geral | CODEFAT/FAT | Governança/fundo | Normatização e financiamento | — | — | Resoluções; recursos | Não | Lei 7.998/90; Res. 957/2022 | Comprovado |

## 5. Tabela de evidências físicas e digitais

| Etapa | Evidência | Tipo | Quem gera | Quem recebe/consulta | Para que serve | Fonte | Nível de evidência |
|-------|-----------|------|-----------|---------------------|----------------|-------|---------------------|
| J1 | Requerimento do Seguro-Desemprego (nº 10 dígitos, inicia "77") | Documento | Empregador | Trabalhador/MTE | Dar entrada | gov.br FAQ | Comprovado |
| J2 | Áudio/menu URA 158 | Áudio/URA | MTE | Cidadão | Orientação | Agência Gov; Legisweb | Comprovado |
| J5 | Tela "Solicitação realizada com sucesso" | Tela | gov.br/MTE | Cidadão | Confirmação | gov.br FAQ | Comprovado |
| J7 | Notificação de deferimento/indeferimento/exigência | Notificação digital | MTE | Cidadão | Decisão | Res. 957/2022 | Comprovado |
| J8 | Calendário/quantidade de parcelas | Tela/extrato | MTE/DATAPREV | Cidadão | Acompanhamento | gov.br | Comprovado |
| J9 | Comprovante de crédito/saque; extrato CAIXA Tem | Comprovante/extrato | Caixa | Cidadão | Pagamento | Caixa | Comprovado |
| J9-J10 | Mensagem "parcela emitida"/não creditada | Mensagem/tela | Sistemas | Cidadão | Diagnóstico | Reclame Aqui; gov.br FAQ | Comprovado |
| J10 | Protocolo de atendimento telefônico Caixa | Protocolo/registro | Caixa URA/atendente | Cidadão | Rastreabilidade | Inferência arquitetura | Inferido |
| J11 | Tela/recurso + anexos | Tela/documento | MTE/cidadão | MTE | Reanálise | gov.br FAQ | Comprovado |
| J12 | Termo declaratório presencial | Documento | SRT/SINE | MTE | Habilitação presencial | Res. 957/2022 art. 6 | Comprovado |
| J13 | Protocolo Fala.BR | Manifestação | CGU/órgão | Cidadão | Controle social | Lei 13.460; CGU | Comprovado |
| J9 | Cartão Cidadão / Cartão Social | Comprovante físico | Caixa | Cidadão | Saque | gov.br; Caixa | Comprovado |

## 6. Matriz normativa

| Normativo/fonte | Órgão | Data | Dispositivo relevante | O que determina | Etapa impactada | Ator impactado | Link/citação | Observação |
|-----------------|-------|------|----------------------|-----------------|-----------------|----------------|--------------|------------|
| Lei nº 7.998 | Congresso/Planalto | 11/01/1990 | Programa SD; FAT | Cria o programa; define custeio; bancos oficiais como pagadores | Todas | MTE, Caixa, FAT | planalto.gov.br/ccivil_03/leis/l7998.htm | Lei-base |
| Resolução CODEFAT nº 957 | CODEFAT/MTE | 21/09/2022 (vigência 03/10/2022) | 69 artigos; concessão, processamento, pagamento | Unifica regras; revoga Res. 467/2005 e outras | Todas | MTE, Caixa, DATAPREV | portalfat.mte.gov.br | Norma central vigente |
| Res. 957/2022 art. 22 | CODEFAT | 2022 | Suspensão da habilitação | Hipóteses de suspensão (admissão, BPC, recusa de recolocação) | J7 | MTE | normaslegais.com.br | Comprovado |
| Res. 957/2022 art. 27 | CODEFAT | 2022 | Recurso administrativo | Cabe recurso em indeferimento, suspensão, cancelamento; prazo 120 dias | J11 | MTE | legisweb | Comprovado |
| Res. 957/2022 art. 28 | CODEFAT | 2022 | Julgamento do recurso | Instância única — Secretaria de Trabalho | J11 | MTE | sapiens.agu.gov.br | Comprovado |
| Res. 987/2023 | CODEFAT | 21/11/2023 | Altera 957/2022 | Bolsa qualificação e calamidade | J5 | MTE | legisweb | Comprovado |
| Lei Complementar nº 150 | Congresso | 01/06/2015 | SD doméstico | Base do SD doméstico | J5 | MTE | — | Comprovado |
| Lei nº 10.779 | Congresso | 25/11/2003 | SD pescador artesanal | Base do seguro-defeso | J5 | MTE | — | Comprovado |
| Lei nº 13.460 | Congresso | 26/06/2017 | Defesa do usuário; Carta de Serviços; ouvidoria | Direitos do usuário; prazos de ouvidoria (30 dias) | J13 | MTE, Caixa | planalto.gov.br | Comprovado |
| Lei nº 14.075 | Congresso | 22/10/2020 | Poupança Social Digital | Permite pagamento de benefícios via conta digital (limite R$ 5.000/mês) | J9 | Caixa | caixa.gov.br | Comprovado |
| Lei nº 10.048 | Congresso | 08/11/2000 | Atendimento prioritário | Prioridade a idosos, PcD, gestantes | J12 | MTE, Caixa | gov.br | Comprovado |
| Acórdão TCU 1151/2018-Plenário | TCU | 23/05/2018 | Contact center Caixa (PE 59/2017; CTIS) | Determina ajustes no edital de telesserviços; comprova URA/CERAT | J10 | Caixa | pesquisa.apps.tcu.gov.br (TC 023.621/2017-6) | Comprova URA/CERAT |

## 7. Matriz de fail points

| ID | Fail point | Etapa | Descrição | Causa provável | Impacto no cidadão | Impacto operacional | Evidência | Nível de evidência | Possível métrica | Tipo |
|----|-----------|-------|-----------|----------------|--------------------|--------------------|-----------|---------------------|------------------|------|
| F1 | "Jogo de empurra" Caixa↔MTE | J10 | Cidadão é mandado da Caixa ao MTE e vice-versa | Fronteira institucional; pagamento vs. habilitação | Não-resolução; ansiedade | Retrabalho; reclamações | Reclame Aqui (caso verbatim: "Liguei na caixa eles pediram para ligar no ministério do trabalho... eles dizem que já foi emitido que tenho que falar com o banco") | Comprovado (relato) | Taxa de transferência entre canais | Comunicação institucional |
| F2 | Liga à Caixa para resolver habilitação | J2/J10 | Expectativa errada de canal | Confusão de papéis | Frustração | Chamada improdutiva | Reclame Aqui | Evidência indireta | % chamadas fora de escopo | Informação |
| F3 | Ausência de URA específica documentada | J10 | Sem menu nominal de SD | Não documentado publicamente | Navegação confusa | Não auditável | Lacuna (TCU só comprova URA genérica) | Pendente/lacuna | — | Roteamento |
| F4 | Dificuldade de autenticação gov.br | J4 | Conta insuficiente/sem acesso | Nível de conta; inclusão digital | Bloqueio de acesso | Migração ao presencial | gov.br FAQ (terminais BB/Caixa para criar acesso) | Comprovado | Taxa de falha de login | Autenticação |
| F5 | Dados inconsistentes CNIS/eSocial | J6 | Vínculo em duplicidade/divergência | Falha de integração de bases | Indeferimento/atraso | Recursos; carga MTE | taxpratico (falha eSocial/CNIS 2022, alerta INSS) | Comprovado | % requerimentos em pendência | Dados |
| F6 | Requerimento não localizado / divergência | J5/J12 | Nº ou dados divergentes | Erro empregador/cadastro | Presencialização obrigatória | Fila SRT/SINE | gov.br FAQ (pergunta 19) | Comprovado | % presencializações por divergência | Dados |
| F7 | Indeferimento sem compreensão | J7 | Cidadão não entende negativa | Linguagem; notificação digital | Perda de prazo | Recursos mal instruídos | gov.br FAQ; Relatório CGU (BGSD 2022) | Evidência indireta | Taxa de recursos por indeferimento | Decisão automática |
| F8 | Recurso online menos efetivo que presencial | J11 | Deferimento online muito menor | Ausência de apoio no protocolo | Perda de benefício | Iniquidade de canal | Relatório de Avaliação da CGU (base 2022): "Para aqueles que realizam o protocolo do processo presencialmente, o percentual de deferimento é significativamente superior do que para aqueles que o fazem pela via online (67,4% e 18,6%, respectivamente)." Em 2022: 431.373 recursos — 228.753 online (18,6% deferidos) e 202.620 presenciais (67,4% deferidos) | Comprovado | % deferimento por canal | Canal |
| F9 | Falha de crédito em conta | J9 | "Parcela emitida" não cai | Dados bancários incorretos; conta inválida | Sem dinheiro | Atendimento Caixa | gov.br FAQ; Reclame Aqui | Comprovado | % falhas de crédito | Pagamento |
| F10 | Sem conta/senha/Cartão Cidadão | J9 | Não consegue sacar | Não bancarização | Atraso no saque | Ida à agência | gov.br FAQ (pergunta 26) | Comprovado | % saques presenciais | Pagamento |
| F11 | Fila/abandono 158 | J2 | "Todos operadores ocupados" | Capacidade da central (157 PAs; até 26 mil ligações/dia) | Não-atendimento | Sobrecarga | Reclame Aqui; relatos; Legisweb | Evidência indireta | Taxa de abandono/fila | Fila |
| F12 | Transbordo inadequado / atendente sem dados | J10 | Atendente Caixa não acessa dados de habilitação | Sistemas separados MTE/Caixa | Não-resolução | Reencaminhamento | Inferência arquitetura | Inferido | Taxa de resolução no 1º contato | Transbordo/integração |
| F13 | Linguagem difícil / siglas | J2/J7 | Baixa compreensão (CNIS, RSD, exigência) | Comunicação técnica | Erro de ação | Recursos | Inferência; CGU | Inferido | Índice de compreensão | Comunicação |
| F14 | Acessibilidade de público vulnerável | J2/J9 | Idoso/PcD sem canal adequado | Barreira digital | Exclusão | Demanda presencial | Lei 10.048; inferência | Inferido | Atendimentos prioritários | Acessibilidade |
| F15 | Falta de protocolo/rastreabilidade telefônica | J10 | Sem comprovante de orientação | Não documentado | Sem prova | Disputa | Lacuna | Pendente/lacuna | Existência de protocolo | Integração sistêmica |
| F16 | Perda de prazo (120 dias) | J11 | Recurso fora do prazo | Demora/desinformação | Perda definitiva | Litígio judicial | Res. 957 art. 27; TNU Tema 356 (prescrição quinquenal a partir da ciência do indeferimento) | Comprovado | % recursos intempestivos | Governança |

## 8. Mapa de atores revisado

- **MTE (Ministério do Trabalho e Emprego):** confirmado como responsável por política, habilitação, concessão, recurso (instância única — Secretaria de Trabalho) e canal 158. Ator central frontstage/backstage.
- **Caixa Econômica Federal:** confirmado como Agente Pagador; canal 0800 726 0207; rede de pagamento (agências, lotéricas, CAIXA Aqui, Caixa Tem). NÃO habilita. Possui contact center com URA (Acórdão TCU 1151/2018).
- **DATAPREV:** confirmado como operador da triagem automatizada e habilitação; mantém/processa CNIS; Contrato 17/2021 com o MTE. Ator de backstage crítico.
- **CODEFAT/FAT:** governança normativa (Resoluções) e financiamento. Backstage.
- **SINE / SRT:** atendimento presencial, correção de divergências, recepção de recurso, fallback. Frontstage presencial.
- **Ouvidoria/CGU/Fala.BR:** manifestações e controle social (Lei 13.460/2017). Backstage de controle.
- **Empregador / Empregador Web:** gera requerimento e comunica dispensa. Ator de entrada.
- **Fornecedores de tecnologia (CTIS Tecnologia S.A. e sucessores):** confirmados como operadores da solução de contact center da Caixa (PE 59/2017; Contrato 8629/2017). Backstage tecnológico.
- **Reclassificação:** "URA da Caixa para Seguro-Desemprego" como ator/entidade específica — REMOVIDO como fato; mantido apenas como hipótese/lacuna.

## 9. Lacunas de evidência

1. **Menu/árvore de decisão da URA da Caixa (0800 726 0207)** — não há fonte pública. Só obtenível por teste de chamada (mystery caller) ou LAI.
2. **Opção nominal "seguro-desemprego" na URA da Caixa** — não documentada (figura apenas sob "benefícios sociais").
3. **Uso de ASR/NLP/voicebot no fluxo de voz da Caixa** — subagente não localizou contrato 2020-2025 de IA de voz. Lacuna.
4. **Regras de transbordo e SLA do 0800 e do 158** — não públicas.
5. **Integração técnica entre canal telefônico da Caixa e sistemas do seguro-desemprego (MTE/DATAPREV)** — não documentada; provável separação.
6. **Existência de protocolo/gravação/trilha de auditoria das chamadas** — inferida por arquitetura, não comprovada para o fluxo SD.
7. **Dados de fila, abandono e TMA específicos do assunto seguro-desemprego** — não públicos.
8. **Empresa atualmente operadora (homologação do Pregão 013/5688-2024)** — não localizada.
9. **Scripts/manuais de atendimento ao seguro-desemprego nos dois canais** — não públicos.

## 10. Recomendações para a próxima etapa de pesquisa

1. **Mystery caller estruturado:** ligar 158 e 0800 726 0207 com roteiros idênticos (consulta de status, falha de crédito, recurso) e registrar menu, opções, transbordo, tempo de espera e resolução. É o único modo de mapear a URA real e validar/derrubar os elementos hoje classificados como "Inferido".
2. **Pedidos LAI (Lei 12.527/2011) via Fala.BR:** solicitar ao MTE a árvore do 158 e SLAs; à Caixa o termo de referência/edital do contact center vigente (Pregão 013/5688-2024) e o mapa de URA do 0800.
3. **Solicitar à CGU/TCU** os relatórios de auditoria do seguro-desemprego — em especial o Relatório de Avaliação da CGU sobre o Seguro-Desemprego (eaud.cgu.gov.br/relatorios/download/1421234, base 2022, elaborado pela CGSAP com apoio da Dataprev a partir da BGSD) e o Acórdão TCU pós-1151/2018 — e as bases do BGSD.
4. **Extrair dados do Fala.BR/Reclame Aqui** sobre seguro-desemprego para quantificar fail points (jogo de empurra, falha de crédito) — benchmark inicial: a divergência de deferimento por canal (67,4% presencial vs. 18,6% online em 2022).
5. **Entrevistas** com atendentes SRT/SINE e com gestores da CGSAP/DATAPREV sobre pontos de pendência e recurso.
6. **Analisar logs/relatórios de URA** (se obtidos via LAI) para roteamento e transbordo.

**Benchmarks que mudariam as conclusões:** se um TR/edital ou resposta-LAI revelar opção nominal de "seguro-desemprego" na URA da Caixa com integração ao sistema de retaguarda do MTE, os fail points F3/F12/F15 deixam de ser lacuna/inferência e o blueprint ganha uma raia resolutiva na Caixa; se o mystery caller confirmar que o 0800 só informa status de pagamento (sem resolver habilitação), consolida-se a leitura de canal meramente consultivo.

## 11. Checklist para construção posterior do Service Blueprint AS-IS

| Camada | A pesquisa permite preencher? | Observação |
|--------|------------------------------|------------|
| Ações do cidadão | Sim (alto) | Jornada bem documentada em fonte oficial |
| Evidências físicas | Sim (médio-alto) | Faltam evidências da camada telefônica Caixa |
| Frontstage | Parcial | 158 e canais digitais bem documentados; URA Caixa = lacuna |
| Backstage | Sim (médio-alto) | DATAPREV/MTE/Caixa documentados; integração telefônica = lacuna |
| Sistemas de suporte | Sim (médio) | CNIS/CAGED/eSocial/BGSD/sistemas Caixa confirmados; URA detalhada não |
| Regras/normativos | Sim (alto) | Matriz normativa completa |
| Fail points | Sim (médio-alto) | Mix de comprovado, indireto e inferido |
| Métricas operacionais | Não (baixo) | Fila, abandono, TMA, transbordo = lacuna; único dado robusto é deferimento por canal (CGU 2022) |
| Lacunas a validar | Sim | Mapeadas na seção 9 |

---

### Nota metodológica sobre níveis de evidência
- **Comprovado:** fontes oficiais diretas — gov.br (serviço e FAQ Seguro-Desemprego), caixa.gov.br, portalfat.mte.gov.br (Resolução CODEFAT 957/2022), planalto.gov.br (Leis 7.998/1990, 13.460/2017, 14.075/2020), dataprev.gov.br, relatório CGU (BGSD 2022), Acórdão TCU 1151/2018.
- **Evidência indireta:** relatos consistentes em Reclame Aqui e cobertura institucional que tangenciam o funcionamento operacional (ex.: jogo de empurra, fila no 158).
- **Inferido:** deduções de arquitetura típica de call center/URA (roteamento, transbordo, protocolo no fluxo Caixa-SD), sem fonte pública direta.
- **Pendente/lacuna:** elementos centrais não localizados em fonte confiável (menu da URA Caixa, integração telefônica com retaguarda, métricas de fila/abandono).