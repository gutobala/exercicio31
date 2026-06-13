# Relatório — Assistente 1 · v2 (revisão após audit_v1)

- **Ferramenta:** Claude Sonnet 4.6
- **Data:** 2026-06-13
- **Link da conversa:** https://claude.ai/public/artifacts/c01fc3e9-04ec-4b12-8d9d-b961c4ce67c0


# Relatório de Insumos para Service Blueprint AS-IS — Atendimento ao Seguro-Desemprego por Canal Telefônico/URA
## **Versão 2.0 — Revisão pós-auditoria**

---

## REGISTRO DE TRATAMENTO DA AUDITORIA

Cada achado da auditoria (seções 2 a 8 do relatório de auditoria v1) recebeu um dos três tratamentos abaixo, indicado na coluna **Ação**:

- **(a) Corrigido** — conteúdo da v1 alterado com texto novo;
- **(b) Defendido** — conteúdo mantido com argumento e evidência adicionais;
- **(c) Em-aberto** — ponto válido da auditoria sem fonte suficiente para fechar; registrado explicitamente como lacuna/pendente.

| Ref. auditoria | Achado | Ação | Seção afetada |
|---|---|---|---|
| 2.1 | CAGED/"base Caixa" na habilitação | (a) Corrigido — removidos; substituídos por CNIS, GRF, GFIP, eSocial, doc. judicial conforme Res. 957/2022 | §2, §4 bastidor |
| 2.2 | "Resultado imediato" da verificação automática | (a) Corrigido — substituído por "verificação automática com resultado disponibilizado conforme processamento" | J6 |
| 2.3 | "Bronze/Prata/Ouro" como requisito comprovado | (a) Corrigido → pendente/lacuna | J3, J4 |
| 2.4 | Tela "sucesso + parcelas" classificada como comprovada | (a) Rebaixado para inferido | Tabela de evidências |
| 2.5 | "Anexos JPG/PNG/PDF ≤1MB" como comprovado | (a) Corrigido → pendente/a confirmar | Tabela de evidências |
| 2.6 | CGSAP como unidade operacional / BGSD como sistema de recurso | (a) Separado: normativo comprovado (Secretaria de Trabalho, Res. 957 art. 28); operacional (CGSAP/BGSD) → em-aberto | §4 bastidor |
| 2.7 | "CTIS e sucessores confirmados" | (a) Corrigido — removido "e sucessores"; CTIS restrita ao período 2017/2018 | §8 atores |
| 2.8 | Mensagem "parcela emitida/não creditada" como comprovada | (a) Rebaixado para evidência indireta/anedótica | Tabela de evidências |
| 3.1 | Reclame Aqui sustentando nível "comprovado" para F1 | (a) Rebaixado para evidência indireta; fenômeno também sustentado por argumento institucional (ver §7) | F1 |
| 3.2 | "taxpratico" como fonte comprovada para inconsistência CNIS/eSocial | (a) Substituída por Res. 957/2022 + referência CGU/TCU | F5 |
| 3.3 | Dados de capacidade do 158 de 2015 como AS-IS atual | (a) Marcados como baseline histórico; buscado dado mais recente (Agência Gov 2025 encontrado); dado de PAs/capacidade original marcado como histórico | §2, §3 |
| 3.4 | 0800 Caixa como canal comprovado de acompanhamento de parcelas | (a) Rebaixado → escopo exato do 0800 para SD a confirmar por teste ou fonte | J8 |
| 4.1 | Backstage do empregador: transmissão via Empregador Web com ICP-Brasil | (a) Adicionado novo registro B_EMP na tabela de bastidor | §4 bastidor |
| 4.2 | Termo declaratório/aceite como controle de elegibilidade | (a) Adicionado B_ACEITE e expandido J5 | §3 jornada, §4 bastidor |
| 4.3 | Notificação digital + presunção de ciência | (a) Adicionado J7a (nova etapa) e B_NOTIF | §3 jornada, §4 bastidor |
| 4.4 | Limites de mérito do recurso + necessidade de corrigir bases externas | (a) Adicionado B_RECURSO e J11a | §3 jornada, §4 bastidor |
| 4.5 | Lote de pagamento + comprovação arquivada pelo agente pagador | (a) Adicionado B_PAGTO_LOTE | §4 bastidor |
| 4.6 | Parcela disponível por prazo definido + devolução ao FAT + reemissão | (a) Adicionado B_PRAZO_FAT, J9a e F21 | §3, §4, §7 |
| 4.7 | Contestação de recebimento de parcela | (a) Adicionado B_CONTEST e F22 | §4 bastidor, §7 |
| 4.8 | AGU e documento judicial no fluxo de exceção | (a) Expandido B_AGU no bastidor | §4 bastidor |
| 5.1 | Registro eletrônico de pagamento arquivado pelo agente pagador | (a) Adicionado E_NEW_1 | §5 evidências |
| 5.2 | Data/hora de disponibilização da notificação digital | (a) Adicionado E_NEW_2 | §5 evidências |
| 5.3 | GRU de restituição | (a) Adicionado E_NEW_3 | §5 evidências |
| 5.4 | Gravação/log URA/tabulação — elementos a obter via LAI | (a) Expandido E_NEW_4; detalhados como lacuna | §5 evidências, §9 lacunas |
| 5.5 | Procuração, alvará judicial, representação | (a) Adicionado E_NEW_5 | §5 evidências |
| 6.1 | Res. CODEFAT/MTE nº 1027/2025 | (a) Adicionado na matriz normativa | §6 normativos |
| 6.2 | Lei 12.527/2011 — LAI | (a) Adicionado | §6 normativos |
| 6.3 | Lei 13.709/2018 — LGPD | (a) Adicionado | §6 normativos |
| 6.4 | Decreto 9.094/2017 | (a) Adicionado | §6 normativos |
| 6.5 | Normativos operacionais de ouvidoria | (a) Adicionado — Decreto 9.492/2018 | §6 normativos |
| 7.1 | F17 — Perda de prazo por presunção de notificação digital | (a) Adicionado | §7 fail points |
| 7.2 | F18 — Recurso indeferido por exigir correção em base de origem | (a) Adicionado | §7 fail points |
| 7.3 | F19 — Conta salário ou conta conjunta rejeitada | (a) Adicionado | §7 fail points |
| 7.4 | F20 — Dados bancários incorretos informados pelo cidadão | (a) Adicionado | §7 fail points |
| 7.5 | F21 — Parcela não sacada no prazo + devolução ao FAT | (a) Adicionado | §7 fail points |
| 7.6 | F22 — Contestação de recebimento de parcela | (a) Adicionado | §7 fail points |
| 7.7 | F23 — Trabalhador doméstico fora do fluxo digital comum | (a) Adicionado | §7 fail points |
| 7.8 | F24 — Falha de cadastro gov.br + dependência de terminal | (a) Expandido de F4 | §7 fail points |
| 7.9 | F25 — Falta de internet: desvio obrigatório para presencial | (a) Adicionado | §7 fail points |
| 7.10 | F26 — Suspensão por reemprego, BPC ou recusa de recolocação | (a) Adicionado | §7 fail points |
| 8.1 | J0 — Pré-jornada: rescisão, TRCT, transmissão pelo empregador | (a) Adicionado | §3 jornada |
| 8.2 | J7a — Ciência da notificação digital (etapa autônoma) | (a) Adicionado | §3 jornada |
| 8.3 | J11a — Correção de dados fora do MTE | (a) Adicionado | §3 jornada |
| 8.4 | J9 — Pagamento excepcional desdobrado em subetapas | (a) J9 expandido + J9a adicionado | §3 jornada |

---

## 1. Resumo executivo (v2)

**Achado central — mantido e reforçado:** A hipótese de uma "URA da Caixa específica para Seguro-Desemprego" **não se confirma** em fonte pública oficial. Existem dois canais telefônicos com responsabilidades separadas: (a) a **Central Alô Trabalho 158** (MTE), responsável por orientação, informação, suporte, agendamento e temas de habilitação/concessão/recurso; e (b) o **0800 726 0207** (Caixa Econômica Federal), que trata "PIS, Benefícios Sociais, FGTS e Cartão Social" — englobando seguro-desemprego apenas no âmbito de **pagamento/saque/crédito**.

**Correções materiais desta versão:**

- Os critérios de aferição automática da habilitação passam a citar apenas CNIS, GRF, GFIP, eSocial e documento judicial, conforme a Resolução CODEFAT nº 957/2022. CAGED e "base Caixa" foram removidos como elementos do fluxo ordinário de habilitação.
- A "verificação automática" da etapa J6 deixa de ser descrita como gerando "resultado imediato": o sistema verifica, mas o resultado é disponibilizado conforme processamento, podendo haver espera percebida pelo cidadão.
- A notificação digital ganha etapa autônoma (J7a), pois é o marco de início da contagem de prazo de recurso — falha crítica para o blueprint.
- A jornada de pagamento foi desdobrada em subetapas que incluem devolução ao FAT por prazo expirado, contestação de recebimento e vias de saque excepcionais.
- Dez novos fail points foram adicionados (F17 a F26), incluindo o mais crítico: perda de prazo de recurso por presunção de ciência de notificação digital (F17).
- A matriz normativa foi ampliada com LAI, LGPD, Decreto 9.094/2017, Decreto 9.492/2018 e Resolução CODEFAT nº 1027/2025.

**Confirmações mantidas:**
- MTE como responsável pela habilitação, concessão e recurso (instância única pela Secretaria de Trabalho).
- Caixa como agente pagador, sem competência de habilitação.
- 158 como canal telefônico oficial do MTE, com atendimento humano sob demanda a partir de menu eletrônico.
- A discrepância de deferimento de recursos por canal (67,4% presencial vs. 18,6% digital, CGU 2022) é o dado quantitativo mais robusto disponível publicamente para o blueprint.

**Lacunas críticas — sem alteração possível sem teste/LAI:**
- Menu real da URA da Caixa (0800) para seguro-desemprego;
- Nível de conta gov.br exigido para acesso ao serviço;
- Texto literal das telas de confirmação e de recurso;
- Dados de fila, abandono, TMA, transbordo no 158 e no 0800;
- Empresa atualmente operadora do contact center da Caixa;
- Prazo exato de disponibilidade da parcela (referido como ~67 dias, a confirmar no texto da Res. 957/2022 ou instrução operacional).
## 2. Delimitação do objeto (v2)

### 2.1 Comprovadamente MTE / Central 158

- A Central Alô Trabalho 158 é o canal oficial do MTE para informações sobre seguro-desemprego, abono salarial, CTPS Digital, CAGED e legislação trabalhista (Agência Gov, gov.br).
- **Horário atualizado:** a partir de 20/03/2024, 7h às 22h, segunda a sábado (ampliado de 7h–19h; nota oficial MTE, publicada 21/03/2024 em gov.br). Gratuita de telefone fixo; chamadas de celular podem ser tarifadas.
- Atendimento eletrônico com menu pré-gravado e opção de transbordo a atendente humano (gov.br).
- **Volume recente (2025):** no 1º semestre de 2025, a central registrou 1.726.914 atendimentos; seguro-desemprego respondeu por 23% e abono salarial por 48% (Agência Gov, ago/2025). _Dado de capacidade de 2015 (157 PAs, até 26 mil ligações/dia) é baseline histórico de inauguração — não representa o dimensionamento atual._
- Canal de **agendamento** para atendimento presencial nas SRTs e canal preferencial para trabalhador doméstico.

### 2.2 Comprovadamente Caixa / pagamento

- A Caixa é Agente Pagador por força da Lei nº 7.998/1990. Não habilita o benefício.
- Canal telefônico: **0800 726 0207**, descrito como "Atendimento CAIXA ao Cidadão — PIS, Benefícios Sociais, FGTS e Cartão Social". Atendimento eletrônico 24h/7; atendimento humano seg-sex 8h–21h, sab 10h–16h (caixa.gov.br, acessado 2025).
- Formas de pagamento comprovadas: conta indicada (TED); conta Caixa selecionada automaticamente; Poupança Social Digital (Caixa Tem, Lei nº 14.075/2020, limite R$ 5.000/mês); Cartão Cidadão + senha em autoatendimento/lotéricas/Correspondentes Caixa Aqui; saque em agência com documento.
- Outros canais Caixa: SAC 0800 726 0101; Ouvidoria 0800 725 7474; PcD auditiva 0800 726 2492; WhatsApp 0800 104 0104.
- **Escopo exato do 0800 para seguro-desemprego (além de pagamento/saque) está pendente de confirmação** por teste de chamada ou fonte específica.

### 2.3 Lacuna sobre "URA da Caixa para Seguro-Desemprego" — posição mantida e reforçada

- **Comprovado:** a Caixa tem solução de contact center/URA (Acórdão TCU 1151/2018-Plenário, TC 023.621/2017-6), com CERATs e dois Data Centers (Brasília e Osasco). O Pregão Eletrônico 013/5688-2024 demonstra contratação ativa, mas sua homologação e o operador atual **não foram localizados**.
- **CTIS Tecnologia S.A.:** confirmada apenas como vencedora do Pregão 59/7066-2017-Gilog/BR (Contrato 8629/2017). A expressão "e sucessores confirmados" da v1 foi removida.
- **NÃO comprovados (lacuna):** opção nominal "seguro-desemprego" no menu; árvore de decisão/URA; ASR/NLP/voicebot; regras de transbordo específicas para SD; integração com sistemas MTE/DATAPREV.

### 2.4 Como isso afeta o blueprint

O blueprint AS-IS deve manter DUAS raias institucionais (MTE/158 e Caixa/0800) com a zona de fronteira explícita. A camada de pagamento excepcional (devolução ao FAT, reemissão, contestação) deve aparecer como subprocesso de exceção na raia da Caixa. A notificação digital é a "linha de visibilidade interna" crítica entre o backstage de decisão e o frontstage do cidadão.

---

## 3. Tabela da jornada do cidadão (v2)

> **Nota:** etapas J0 (pré-jornada), J7a (ciência da notificação), J9a (pagamento excepcional) e J11a (correção em base externa) são novas nesta versão. Jornada de trabalhador doméstico é anotada como desvio em J3.

| ID | Etapa | Objetivo do cidadão | Canal | Ação do cidadão | Resposta percebida | Evidência física/digital | Resultado possível | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|
| **J0** | **Pré-jornada — rescisão e transmissão** | — | Empregador / Empregador Web | Empregador transmite rescisão (TRCT) e requerimento via Empregador Web com certificado ICP-Brasil; campos obrigatórios (tipo demissão, datas, salário, CBO) | Trabalhador recebe requerimento físico/digital com nº de 10 dígitos iniciando em "77" | Requerimento do SD; TRCT; aviso-prévio | Requerimento entregue corretamente, com divergência ou não entregue | gov.br FAQ; Res. 957/2022; MTE Empregador Web | Comprovado |
| **J1** | Dispensa — receber o requerimento | Obter documento para dar entrada | Empregador | Recebe formulário do Requerimento do SD | Documento físico/PDF com dados da rescisão | Requerimento; TRCT | Tem ou não o documento | gov.br; Res. 957/2022 | Comprovado |
| **J2** | Busca de informação | Saber se tem direito, como solicitar, prazos | 158 / gov.br / CTPS Digital / busca web | Liga 158 ou acessa portal; pergunta sobre prazo e documentos | Menu pré-gravado; orientação de atendente; FAQ digital | Áudio URA 158; tela FAQ | Orientação; agendamento; direcionamento a canal digital | gov.br FAQ; Agência Gov | Comprovado |
| **J3** | Acesso ao canal de solicitação | Requerer o benefício | gov.br / app CTPS Digital | Login com conta gov.br; _trabalhador doméstico: agendamento pelo 158_ | Tela de login ou confirmação de agendamento | Conta gov.br | Autenticado (segue); bloqueado por nível de conta insuficiente (F4, F24); trabalhador doméstico → agendamento presencial (F23) | gov.br (serviço "Solicitar o Seguro-Desemprego") | Comprovado |
| *(nível gov.br)* | *(detalhe de J3)* | Autenticar com nível exigido | gov.br | Fornece credenciais | Acesso liberado ou bloqueio | Token gov.br | Prossegue ou precisa subir nível da conta | gov.br | **Pendente/lacuna** — nível mínimo exigido (bronze/prata/ouro) não comprovado; a confirmar por teste ou FAQ oficial |
| **J4** | Informar número do requerimento e dados | Dar início à solicitação | gov.br / app | Informa nº do requerimento e confirma dados | Validação de dados; termo de aceite | Tela de validação; número do requerimento | Dados válidos → prossegue; divergência → J11a / J12 | gov.br FAQ | Comprovado |
| **J5** | Confirmação da solicitação e aceite do termo | Formalizar a solicitação | gov.br / app | Lê e confirma termo declaratório/aceite de que atende os requisitos; conclui envio | Tela de confirmação e informação sobre quantidade e prazo de parcelas | Tela de confirmação *(texto literal a confirmar)*; protocolo | Solicitação recebida pelo sistema; aguarda processamento | Res. 957/2022; gov.br FAQ | Tela de confirmação: **Inferido** — existência plausível; texto literal e exibição imediata de parcelas não comprovados |
| **J6** | Verificação automática (bastidor) | — (processo interno) | Sistema SD / DATAPREV | Nenhuma ação — processamento automático | Nada imediatamente visível; resultado disponibilizado após processamento | — | Deferido / indeferido / pendência / exigência; resultado aparece em consulta posterior | Res. 957/2022; dataprev.gov.br; IBGE metadados | Comprovado (verificação automática); prazo de disponibilização: **Evidência indireta** |
| **J7** | Consultar resultado | Ver se foi deferido | gov.br / app / 158 | Acessa o serviço ou liga | Notificação de deferimento, indeferimento, pendência, suspensão ou cancelamento | Notificação digital no ambiente do usuário | 5 desfechos: deferido; indeferido; pendência; suspenso; cancelado | Res. 957/2022; gov.br FAQ | Comprovado |
| **J7a** | **Ciência da notificação digital** *(etapa nova)* | Tomar conhecimento formal da decisão | gov.br / app / e-mail | Acessa notificação; data/hora de disponibilização é registrada pelo sistema | Conteúdo da decisão | Notificação com data/hora de disponibilização | Prazo de recurso (120 dias) começa a contar; perda de prazo se cidadão não acessar (F17) | Res. 957/2022 art. 27; Lei 9.784/1999 (processo administrativo) | **Evidência indireta** — presunção de ciência após disponibilização digital análoga à prevista em lei de processo administrativo; aplicação específica ao SD a confirmar |
| **J8** | Acompanhar parcelas | Ver datas e valores das parcelas | gov.br / app CTPS Digital / 158 | Consulta calendário | Quantidade e datas de parcelas | Tela de parcelas; extrato digital | Acompanhamento do calendário | gov.br; Caixa | Comprovado (gov.br e app); 0800 Caixa como canal de consulta: **escopo a confirmar** |
| **J9** | Receber pagamento | Ter a parcela creditada | Conta bancária / Poupança Social Digital / Caixa Tem | Verifica crédito em conta; abre Caixa Tem se não tiver conta ativa | Crédito na conta ou ausência de crédito | Extrato bancário; extrato Caixa Tem | Pago com sucesso; ou falha de crédito → J10 | Caixa; gov.br FAQ; Lei 14.075/2020 | Comprovado |
| **J9a** | **Pagamento excepcional / fallback de saque** *(etapa nova)* | Sacar parcela por via alternativa | Cartão Cidadão + lotérica/autoatendimento; agência Caixa | Saca com Cartão Cidadão e senha; ou comparece à agência com documento | Saque efetuado ou negado | Comprovante de saque; extrato | Saque realizado; ou parcela devolvida ao FAT por prazo expirado → reemissão necessária (F21) | Caixa; Res. 957/2022 | Comprovado (vias de saque); prazo de disponibilidade: **Evidência indireta** (prazo específico a confirmar) |
| **J10** | Resolver falha de crédito | Receber parcela não creditada | 0800 726 0207 (Caixa) / agência Caixa / 158 | Liga, vai à agência, informa dados da conta; corrige dados bancários | Orientação; "ir à agência"; ou jogo de empurra (F1) | Protocolo (existência inferida); nova tentativa de crédito | Resolução; reencaminhamento; correção de dados bancários | Caixa; Reclame Aqui (evidência indireta); gov.br FAQ | Evidência indireta |
| **J11** | Interpor recurso | Reverter indeferimento, suspensão ou cancelamento | gov.br / app / 158 para agendamento / SRT presencial | Acessa tela de recurso; preenche motivo; anexa documentos digitais; ou agenda atendimento presencial | Protocolo de recurso; aguarda análise | Tela de recurso; documentos anexados *(formatos e limites a confirmar)*; protocolo | Recurso em análise (Secretaria de Trabalho, Res. 957/2022 art. 28) | Res. 957/2022 arts. 27-28; gov.br FAQ | Comprovado (existência do recurso); formatos/limites de anexo: **Pendente/lacuna** |
| **J11a** | **Correção de dados em base externa** *(etapa nova)* | Corrigir dado incorreto que causou indeferimento | Empregador / Junta Comercial / Justiça do Trabalho / SINE/SRT | Solicita ao empregador retificação no eSocial/GFIP; ou busca documentação judicial; ou atende à exigência na SRT | Confirmação de retificação; novo processamento | Documentos de retificação; guias de GFIP corrigida; documento judicial | Reprocessamento automático após correção; ou recurso instruído com nova documentação | Res. 957/2022 arts. 6º, 27; gov.br FAQ (pergunta 19) | Comprovado (possibilidade de exigência e correção); fluxo operacional detalhado: **Inferido** |
| **J12** | Atendimento presencial | Corrigir divergência ou requerer pessoalmente (doméstico, documentação especial) | SRT / SINE (agendado pelo 158) | Comparece com documentos; preenche termo declaratório presencial | Atendimento humano; análise; orientação | Senha de atendimento; protocolo; termo declaratório | Correção; nova habilitação; nova pendência | gov.br FAQ; Res. 957/2022 arts. 6º, 18 | Comprovado |
| **J13** | Registrar manifestação | Reclamar, denunciar ou sugerir | Fala.BR / Ouvidoria MTE / Ouvidoria Caixa 0800 725 7474 | Registra manifestação com dados do atendimento | Protocolo; resposta em até 20 dias (prorrogável a 40) | Protocolo Fala.BR; resposta formal | Resposta; encaminhamento; providência | Lei 13.460/2017; Decreto 9.492/2018 | Comprovado |
## 4. Tabela de processos de bastidor (v2)

> **Nota:** entradas novas (B_EMP, B_ACEITE, B_NOTIF, B_RECURSO, B_PAGTO_LOTE, B_PRAZO_FAT, B_CONTEST, B_AGU) foram adicionadas conforme apontamentos da auditoria. O registro de DATAPREV foi corrigido para remover CAGED e "base Caixa" e para separar competência técnica de competência decisória.

| ID | Etapa relacionada | Ator de bastidor | Tipo | Atividade interna | Sistema/base usada | Entrada | Saída | Visível ao cidadão? | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|---|
| **B_EMP** | **J0** | **Empregador / Empregador Web** | **Humano/sistema** | **Transmissão eletrônica do requerimento com certificado digital ICP-Brasil; preenchimento de campos obrigatórios (tipo demissão, datas, CBO, remuneração); geração do número "77…"** | **Empregador Web (MTE); eSocial; CAGED (para informação de vínculo)** | **Dados da rescisão** | **Requerimento disponível para o trabalhador** | **Não** | **gov.br (Empregador Web); Res. 957/2022; MTE** | **Comprovado** |
| B_HABILITACAO | J5-J6 | DATAPREV (processamento técnico) / Sistema SD (competência decisória do MTE) | IA/sistema | Triagem automatizada: verifica critérios de habilitação com base em CNIS, GRF, GFIP, eSocial e documento judicial quando cabível. _DATAPREV atua como processador técnico; a competência de habilitação é do MTE._ | CNIS; GRF; GFIP; eSocial; documento judicial | Requerimento + dados do cidadão | Resultado: deferido / indeferido / pendência / exigência | Não | Res. 957/2022; dataprev.gov.br; IBGE metadados MTE | Comprovado (verificação automática); papel exato da DATAPREV vs. sistema SD: **Evidência indireta** |
| **B_ACEITE** | **J5** | **Sistema SD / MTE** | **Sistema/documento** | **Controle de elegibilidade via termo declaratório/aceite digital: o cidadão declara que atende os requisitos e não está em situação de suspensão/cancelamento. No presencial: assinatura de termo físico.** | **Sistema SD** | **Declaração do cidadão** | **Registro do aceite; parte do processo de habilitação** | **Parcialmente (o cidadão assina/clica, mas a verificação é backstage)** | **Res. 957/2022 art. 6º e equivalentes; inferência de fluxo digital** | **Inferido** |
| B_RECURSO_NORM | J11 | Secretaria de Trabalho / MTE | Humano | Julgamento do recurso em instância única (art. 28 da Res. 957/2022); análise restrita aos requisitos normativos passíveis de recurso | Sistema SD / sistema interno (unidade e sistema operacional: **em-aberto**) | Recurso instruído | Deferimento ou indeferimento do recurso | Não | Res. 957/2022 art. 28 | Comprovado (competência normativa); unidade interna (CGSAP?), sistema operacional (BGSD?): **Pendente/em-aberto** |
| **B_RECURSO** | **J11 / J11a** | **Sistema SD / MTE / Secretaria de Trabalho** | **Sistema/humano** | **Análise do mérito do recurso limitada aos requisitos legais. Se o problema estiver em base de origem (empregador, eSocial, GFIP), o recurso pode ser indeferido mesmo com razão substantiva do cidadão — exigindo correção na base pelo responsável (empregador, Justiça do Trabalho).** | **Bases externas: eSocial; CAGED; GFIP; documentação judicial** | **Recurso + documentos** | **Decisão de recurso; eventual exigência de correção externa** | **Não** | **Res. 957/2022 arts. 27-28; inferência técnica** | **Inferido** |
| B_NOTIF_J7 | J7 | Sistema SD / MTE | Sistema | Geração e disponibilização da notificação digital de resultado no ambiente do usuário (gov.br / app) | Sistema SD | Resultado da análise | Notificação com data/hora de disponibilização | Parcialmente | Res. 957/2022; Lei 9.784/1999 | Comprovado (existência da notificação) |
| **B_NOTIF** | **J7a** | **Sistema SD / MTE** | **Sistema/documento** | **Registro do momento de disponibilização da notificação digital. Presunção de ciência: o cidadão é considerado notificado a partir da data de disponibilização, independentemente de acesso efetivo. Prazo de recurso (120 dias) começa a correr a partir desse marco.** | **Sistema SD; ambiente gov.br** | **Notificação gerada** | **Registro de data/hora de ciência; início de contagem de prazo** | **Não** | **Res. 957/2022 art. 27; Lei 9.784/1999 art. 26 §3 (analogia); a confirmar aplicação específica ao SD** | **Evidência indireta** |
| B_PAGTO_LOTE | J9 | Caixa (Agente Pagador) + FAT/MTE | Sistema/fundo | Processamento em lote das ordens de pagamento das parcelas; crédito nas contas indicadas; emissão de autenticação/comprovante de pagamento arquivado pelo agente pagador | Sistemas Caixa; FAT | Ordem de pagamento do MTE | Crédito nas contas; registro de pagamento comprovado e arquivado | Não (bastidor) | Res. 957/2022; Lei 7.998/1990; inferência de arquitetura de agente pagador | Comprovado (lote de pagamento); período de arquivamento (referido como 5 anos): **Evidência indireta — prazo a confirmar** |
| **B_PRAZO_FAT** | **J9a** | **Caixa (Agente Pagador) / FAT** | **Sistema/fundo** | **Controle de prazo de disponibilidade da parcela para saque. Parcelas não sacadas dentro do prazo definido (referido como ~67 dias em documentação operacional) são devolvidas ao FAT. Reemissão posterior é possível mediante procedimento.** | **Sistemas Caixa; FAT** | **Parcela emitida não sacada** | **Devolução ao FAT; pedido de reemissão necessário** | **Não** | **Res. 957/2022 (prazo específico a confirmar no texto); inferência operacional** | **Evidência indireta** |
| **B_CONTEST** | **J10 / J9a** | **Caixa (Agente Pagador) / MTE** | **Humano/sistema** | **Tratamento de contestação de recebimento: trabalhador afirma não ter recebido parcela; agente pagador verifica registros de pagamento (autenticações arquivadas); inicia procedimento administrativo de contestação** | **Sistemas Caixa; registros de pagamento arquivados** | **Contestação do cidadão** | **Comprovação de pagamento ou reconhecimento de falha; procedimento de reemissão** | **Parcialmente** | **Res. 957/2022; inferência operacional de agente pagador** | **Inferido** |
| **B_AGU** | **J11 / J11a** | **AGU / órgão jurídico competente** | **Humano/documento** | **Validação da força executória de documento judicial apresentado para suprir ausência ou divergência de informação em base automática (vínculo, remuneração, período de trabalho). Necessário em casos excepcionais onde as bases CNIS/eSocial/GFIP são insuficientes.** | **Processo judicial; sistema jurídico** | **Decisão/sentença judicial** | **Documento validado para habilitação** | **Não** | **Res. 957/2022 (documento judicial como base alternativa); inferência de fluxo de exceção** | **Inferido** |
| B_SRT | J12 | SRT / SINE | Humano | Atendimento presencial; correção de dados; recepção de recurso presencial; orientação; agendamento | SAA/sistemas MTE; bases externas | Documentos do cidadão | Correção; habilitação; protocolo de atendimento | Sim | gov.br FAQ; Res. 957/2022 art. 6º | Comprovado |
| B_158_ATEND | J2 / J8 / J11 | Atendente humano da Central 158 (MTE) | Humano | Orientação; informação; agendamento; suporte ao recurso | Sistema de atendimento MTE; CRM (existência: inferida) | Ligação; dados do cidadão | Orientação; protocolo; agendamento | Sim (voz) | gov.br; Agência Gov | Comprovado |
| B_URA_158 | J2 | URA/sistema de atendimento eletrônico 158 | IA/sistema | Roteamento/triagem eletrônica com menu pré-gravado; opções por DTMF; transbordo a atendente sob demanda | Servidor de URA MTE | Ligação | Menu; informação pré-gravada; transbordo | Sim (voz) | gov.br (texto: "atendimento eletrônico por meio de informações pré-gravadas") | Comprovado |
| B_CAIXA_TELS | J10 | CERAT Caixa / contact center Caixa (0800) | Humano/sistema | Atendimento de benefícios sociais/pagamento; triagem por URA; transbordo a atendente | URA Caixa (comprovado como infraestrutura); integração com sistemas SD: **não comprovada** | Ligação | Orientação sobre pagamento/saque; encaminhamento | Sim (voz) | Acórdão TCU 1151/2018; Pregão 013/5688-2024 | URA: Comprovada (infraestrutura); menu/escopo SD: **Pendente/lacuna** |
| B_CODEFAT | Geral | CODEFAT / FAT | Governança/fundo | Normatização (Resoluções), aprovação de recursos, financiamento do benefício | — | — | Resoluções; repasse de recursos ao FAT | Não | Lei 7.998/1990; Res. 957/2022 | Comprovado |
| B_OUVIDORIA | J13 | Ouvidoria MTE / Ouvidoria Caixa / Fala.BR / CGU | Humano/sistema | Tratamento de manifestações; prazo de resposta até 20 dias (prorrogável a 40); encaminhamento a órgão responsável | Fala.BR; sistemas de ouvidoria | Manifestação | Resposta; providência; relatório de gestão | Parcialmente | Lei 13.460/2017; Decreto 9.492/2018 | Comprovado |
## 5. Tabela de evidências físicas e digitais (v2)

> **Correções v2:** tela de confirmação J5 e mensagem "parcela emitida" rebaixadas. **Adições:** E_NEW_1 a E_NEW_5. Limites/formatos de anexo mantidos como pendente.

| ID | Etapa | Evidência | Tipo | Quem gera | Quem recebe/consulta | Para que serve | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|
| E1 | J0/J1 | Requerimento do Seguro-Desemprego (10 dígitos, início "77") | Documento físico/PDF | Empregador (via Empregador Web) | Trabalhador/MTE/sistema | Dar entrada na solicitação; número-chave do processo | gov.br FAQ; Empregador Web | Comprovado |
| E2 | J0 | TRCT — Termo de Rescisão do Contrato de Trabalho | Documento | Empregador | Trabalhador | Comprovação da rescisão; dados de indenizações | CLT; Empregador Web | Comprovado |
| E3 | J2 | Áudio/menu URA da Central 158 | Áudio/URA | MTE | Cidadão | Orientação inicial; triagem de demanda | gov.br; Agência Gov | Comprovado |
| E4 | J3/J4 | Conta gov.br autenticada | Tela/registro digital | SERPRO/gov.br | Cidadão | Acesso ao serviço; autenticação | gov.br | Comprovado |
| E5 | J5 | Tela de confirmação da solicitação | Tela | Sistema SD / MTE | Cidadão | Confirmação de protocolo; indicação de parcelas e prazos | gov.br FAQ (referência genérica à confirmação) | **Inferido** — existência plausível; texto literal e exibição imediata de parcelas a confirmar por teste ou print oficial |
| **E5a** | **J5** | **Termo declaratório/aceite digital** | **Registro digital** | **Sistema SD / MTE** | **Cidadão / MTE** | **Controle de elegibilidade; marco formal da solicitação** | **Res. 957/2022; inferência de fluxo digital** | **Inferido** |
| **E_NEW_2** | **J7a** | **Notificação digital com data/hora de disponibilização** | **Notificação digital** | **Sistema SD / MTE** | **Cidadão** | **Marco de ciência formal da decisão; início da contagem do prazo de recurso (120 dias)** | **Res. 957/2022 art. 27; Lei 9.784/1999 (analogia)** | **Evidência indireta** |
| E7 | J7 | Notificação de deferimento / indeferimento / exigência / suspensão / cancelamento | Notificação digital | MTE/sistema SD | Cidadão | Comunicar a decisão; instruir próximas ações | Res. 957/2022; gov.br FAQ | Comprovado |
| E8 | J8 | Calendário/quantidade de parcelas | Tela/extrato digital | MTE/DATAPREV | Cidadão | Acompanhamento do benefício | gov.br | Comprovado |
| E9 | J9 | Extrato bancário / extrato Caixa Tem com crédito da parcela | Extrato | Caixa / banco indicado | Cidadão | Comprovação de recebimento | Caixa; Lei 14.075/2020 | Comprovado |
| **E_NEW_1** | **J9 / J9a** | **Registro eletrônico de autenticação de pagamento arquivado pelo agente pagador** | **Registro em sistema** | **Caixa (Agente Pagador)** | **MTE / Caixa (auditoria, contestação)** | **Evidência oficial de que o pagamento foi processado; base para contestação e auditoria** | **Res. 957/2022; inferência de operação de agente pagador** | **Evidência indireta** — existência provável por arquitetura de agente pagador; período de retenção a confirmar |
| E10 | J9 | Comprovante de saque (lotérica, autoatendimento, agência) | Comprovante físico/digital | Caixa / Correspondente | Cidadão | Comprovação do saque | Caixa | Comprovado |
| E11 | J9 | Cartão Cidadão / Cartão Social | Comprovante físico | Caixa | Cidadão | Instrumento de saque na rede física | gov.br; Caixa | Comprovado |
| E12 | J9-J10 | Mensagem de "parcela emitida" sem crédito na conta | Mensagem/tela | Sistemas (MTE ou Caixa) | Cidadão | Diagnóstico de falha de crédito | Reclame Aqui; gov.br FAQ (referência genérica) | **Evidência indireta/anedótica** — relato de usuários; texto exato e origem do sistema a confirmar |
| **E_NEW_3** | **J9a / restituição** | **GRU — Guia de Recolhimento da União (restituição de parcelas recebidas indevidamente)** | **Documento** | **MTE / Receita Federal** | **Cidadão (pagamento de restituição)** | **Devolução de valores recebidos sem direito; controle financeiro** | **Res. 957/2022; sistemática FAT** | **Evidência indireta** — previsão normativa provável; emissão de GRU específica para SD a confirmar |
| E13 | J11 | Protocolo de recurso + documentos anexados | Tela/documento digital | MTE/sistema SD / cidadão | MTE | Instrução do recurso | gov.br FAQ; Res. 957/2022 art. 27 | Comprovado (existência do recurso); formatos/limites de anexo: **Pendente/lacuna** |
| E14 | J12 | Termo declaratório presencial | Documento | SRT/SINE | MTE | Controle de elegibilidade presencial; habilitação | Res. 957/2022 art. 6º | Comprovado |
| E15 | J12 | Protocolo de atendimento presencial | Protocolo | SRT/SINE | Cidadão/MTE | Rastreabilidade do atendimento | gov.br FAQ; inferência | Inferido |
| E16 | J13 | Protocolo Fala.BR | Manifestação/registro | CGU/Fala.BR | Cidadão | Rastreabilidade da manifestação; controle social | Lei 13.460/2017; Decreto 9.492/2018 | Comprovado |
| **E_NEW_4** | **J10 / bastidor telefônico** | **Gravação de chamada; log de URA; tabulação do atendente; TMA; tempo de espera; motivo de contato; transferência; abandono; encerramento** | **Registro em sistema (a obter via LAI)** | **Operador do contact center / URA** | **Gestor da central; auditoria; pesquisa** | **Validação da operação real da URA e central; KPIs de atendimento; fail points** | **Acórdão TCU 1151/2018 (comprova gravação como componente); LAI** | **Pendente/lacuna** — elementos existentes por arquitetura comprovada; acesso restrito; obtível via LAI ou entrevista |
| **E_NEW_5** | **J11 / J12 (excepcionais)** | **Procuração; alvará judicial; documentos de representação de dependentes/sucessores** | **Documento** | **Cartório/Justiça / cidadão** | **MTE/SRT/cidadão** | **Representação de trabalhador incapacitado, falecido ou menor; fluxo de exceção** | **CLT; CC; inferência operacional** | **Inferido** |

---

## 6. Matriz normativa (v2)

> **Adições v2:** Lei 12.527/2011 (LAI); Lei 13.709/2018 (LGPD); Decreto 9.094/2017; Decreto 9.492/2018; Res. CODEFAT/MTE nº 1027/2025. Res. 957/2022 atualizada com referência às alterações posteriores.

| Normativo/fonte | Órgão | Data | Dispositivo relevante | O que determina | Etapa impactada | Ator impactado | Link/citação | Observação |
|---|---|---|---|---|---|---|---|---|
| Lei nº 7.998 | Congresso/Planalto | 11/01/1990 | Criação do SD; FAT; competência de bancos oficiais como pagadores | Institui o programa SD; define custeio pelo FAT; designa bancos oficiais federais como agentes pagadores | Todas | MTE, Caixa, FAT | planalto.gov.br/ccivil_03/leis/l7998.htm | Lei-base; múltiplas alterações posteriores |
| Resolução CODEFAT nº 957 (e alterações) | CODEFAT/MTE | 21/09/2022 (vigência 03/10/2022) | 69 artigos; concessão, processamento, pagamento, recurso, suspensão, cancelamento | Norma central vigente; unifica regras; revoga Res. 467/2005 e outras | Todas | MTE, Caixa, DATAPREV, cidadão | portalfat.mte.gov.br; normaslegais.com.br | Norma regulatória principal; **consultar alterações posteriores, inclusive Res. 1027/2025** |
| **Resolução CODEFAT/MTE nº 1027/2025** | **CODEFAT/MTE** | **2025** | **Altera dispositivos da Res. 957/2022** | **Atualiza regras do SD após 2022; conteúdo específico a confirmar** | **A confirmar** | **MTE, Caixa** | **portalfat.mte.gov.br** | **Evidência indireta — referida na auditoria; texto integral a verificar** |
| Res. 957/2022 art. 6º e equivalentes | CODEFAT | 2022 | Modalidades de solicitação e habilitação | Canais, documentação, termo declaratório | J0, J3, J5, J12 | MTE, cidadão | Res. 957/2022 | Comprovado |
| Res. 957/2022 art. 22 | CODEFAT | 2022 | Hipóteses de suspensão (admissão, BPC, recusa de recolocação) | Define quando o benefício é suspenso automaticamente | J7, J7a, F26 | MTE, DATAPREV | normaslegais.com.br | Comprovado |
| Res. 957/2022 art. 27 | CODEFAT | 2022 | Recurso administrativo; prazo de 120 dias | Garante direito de recurso; início do prazo a partir da ciência | J7a, J11, F16, F17 | MTE, cidadão | legisweb | Comprovado |
| Res. 957/2022 art. 28 | CODEFAT | 2022 | Julgamento do recurso em instância única pela Secretaria de Trabalho | Define competência decisória; sem segunda instância administrativa | J11 | MTE | Res. 957/2022 | Comprovado |
| Res. CODEFAT nº 987/2023 | CODEFAT/MTE | 21/11/2023 | Bolsa qualificação e situações de calamidade | Altera e amplia modalidades | J5 | MTE | legisweb | Comprovado |
| Lei Complementar nº 150/2015 | Congresso | 01/06/2015 | SD para trabalhador doméstico | Define regras específicas do SD doméstico; habilitação via 158/presencial | J3, F23 | MTE | planalto.gov.br | Comprovado |
| Lei nº 10.779/2003 | Congresso | 25/11/2003 | SD para pescador artesanal (seguro-defeso) | Define regras do seguro-defeso | J5 | MTE/IBAMA | planalto.gov.br | Comprovado |
| Lei nº 13.460/2017 | Congresso | 26/06/2017 | Direitos do usuário de serviço público; Carta de Serviços; ouvidoria | Garante direitos; define prazos de ouvidoria; exige Carta de Serviços | J13 | MTE, Caixa | planalto.gov.br | Comprovado |
| **Decreto nº 9.094/2017** | **Presidência da República** | **17/07/2017** | **Simplificação do atendimento ao usuário; dispensa de certidões; Carta de Serviços no âmbito do Executivo Federal** | **Simplificação administrativa; padrão de atendimento; integração de bases** | **J2, J3, J12** | **MTE, Caixa, SINE/SRT** | **planalto.gov.br** | **Comprovado** |
| **Decreto nº 9.492/2018** | **Presidência da República** | **05/09/2018** | **Regulamentação da Lei 13.460/2017; prazos e fluxos de ouvidoria** | **Prazo de resposta: 20 dias (prorrogável a 40); encaminhamento de manifestações** | **J13** | **MTE, Caixa, CGU** | **planalto.gov.br** | **Comprovado** |
| Lei nº 14.075/2020 | Congresso | 22/10/2020 | Poupança Social Digital | Permite pagamento de benefícios via conta digital; limite R$ 5.000/mês | J9 | Caixa | caixa.gov.br | Comprovado |
| Lei nº 10.048/2000 | Congresso | 08/11/2000 | Atendimento prioritário a idosos, PcD, gestantes | Prioridade em atendimento presencial | J12 | SRT/SINE, Caixa | gov.br | Comprovado |
| **Lei nº 12.527/2011 (LAI)** | **Congresso** | **18/11/2011** | **Acesso a informações públicas; prazo de 20 dias (prorrogável a 40) para resposta** | **Base legal para obtenção de documentos internos: árvore de URA, contratos, SLAs, logs, scripts, manuais, relatórios** | **Todas (instrumento de pesquisa)** | **MTE, Caixa, DATAPREV** | **planalto.gov.br** | **Comprovado — central para validação das lacunas desta pesquisa** |
| **Lei nº 13.709/2018 (LGPD)** | **Congresso** | **14/08/2018** | **Proteção de dados pessoais; base legal para tratamento; direitos do titular; uso de sistemas automatizados** | **Regula tratamento de CPF, NIS/PIS, dados trabalhistas, remuneração, dados bancários, gravações de voz; impõe transparência em decisões automatizadas** | **J4, J6, J10 (gravações)** | **MTE, Caixa, DATAPREV, fornecedores de IA/URA** | **planalto.gov.br** | **Comprovado — relevante especialmente se houver processamento automatizado e IA no fluxo** |
| Acórdão TCU 1151/2018-Plenário | TCU | 23/05/2018 | Contact center Caixa (PE 59/2017; CTIS; TC 023.621/2017-6) | Comprova infraestrutura URA/CERAT da Caixa; determina ajustes no edital | J10 | Caixa | pesquisa.apps.tcu.gov.br | Comprova URA/CERAT genérica; não comprova menu SD |
| Lei nº 9.784/1999 | Congresso | 29/01/1999 | Art. 26 §3 — notificação por via postal presumida após 5 dias úteis | Analogia para presunção de ciência de notificação digital (aplicação ao SD a confirmar) | J7a, F17 | MTE, cidadão | planalto.gov.br | **Evidência indireta** — norma de processo administrativo federal; aplicação ao canal digital do SD a confirmar por norma específica |
| TNU — Tema 356 | TNU | — | Prescrição quinquenal a partir da ciência do ato de indeferimento | Prazo de prescrição para ação judicial | J11, F16 | cidadão, AGU | TNU | Comprovado |
| Acórdão TCU 2154/2017-Plenário + Relatório CGU (BGSD 2022) | TCU/CGU | 2017/2022 | Auditoria de desempenho SD; taxa de deferimento por canal | Deferimento presencial 67,4% vs. digital 18,6% (2022; 431.373 recursos) | J11, F8 | MTE | eaud.cgu.gov.br | Comprovado — dado quantitativo mais robusto disponível |
## 7. Matriz de fail points (v2 — F1 a F26)

> **Correções v2:** F1 rebaixado de "comprovado" para "evidência indireta" (Reclame Aqui); F5 com fonte substituída por Res. 957/2022; F11 com dado de 2015 marcado como histórico; escopo do 0800 em F8 qualificado. **Adições:** F17 a F26.
>
> **Nota metodológica sobre F1:** embora a classificação do nível de evidência tenha sido rebaixada para "evidência indireta" por ausência de dados sistêmicos, o fenômeno é **estruturalmente previsível** pela arquitetura institucional — a Caixa não habilita e o MTE não credita. Qualquer cidadão que ligue para o canal errado será redirecionado. O rebaixamento do nível não diminui a relevância do fail point para o blueprint.

| ID | Fail point | Etapa | Tipo | Descrição | Causa provável | Impacto no cidadão | Impacto operacional | Evidência | Nível de evidência | Possível métrica | Fonte |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **F1** | **"Jogo de empurra" Caixa↔MTE** | J10 | Comunicação institucional | Cidadão é enviado do canal da Caixa ao canal do MTE e vice-versa sem resolução. Fenômeno estruturalmente esperado: cada canal responde apenas pelo seu escopo; cidadão com expectativa errada percebe ausência de resolutividade | Fronteira institucional não-explicada ao cidadão; confusão entre habilitação (MTE) e pagamento (Caixa) | Frustração; não-resolução; abandono | Retrabalho; reclamações em ouvidoria | Relatos em Reclame Aqui (anedóticos); estrutura institucional comprovada | **Evidência indireta — relatos individuais + inferência estrutural** | Taxa de transferência entre canais; % manifestações sobre o tema em Fala.BR | Reclame Aqui; Acórdão TCU; gov.br |
| F2 | Liga à Caixa esperando resolver habilitação | J2/J10 | Informação | Cidadão usa canal de pagamento (0800) esperando resolver habilitação, deferimento ou recurso | Confusão de papéis entre Caixa e MTE | Frustração; chamada improdutiva | Chamada fora de escopo; custo operacional | Estrutura institucional; relatos | Evidência indireta | % chamadas fora de escopo registradas | Estrutura MTE/Caixa |
| F3 | Ausência de URA/opção específica documentada para SD na Caixa | J10 | Roteamento | Não há evidência pública de opção nominal "Seguro-Desemprego" na URA da Caixa | Não documentado publicamente | Navegação confusa; tempo perdido em menu | Canal não auditável; blueprint incompleto | Lacuna confirmada | **Pendente/lacuna** | — | TCU; pesquisa v1+v2 |
| **F4** | Dificuldade de autenticação gov.br — bloqueio por nível de conta | J3/J4 | Autenticação | Conta gov.br com nível insuficiente para acessar o serviço; cidadão sem acesso a terminal bancário (BB/Caixa) para subir o nível | Nível exigido não comprovado (lacuna); inclusão digital | Bloqueio de acesso ao canal digital | Migração ao presencial (SINE/SRT) ou 158 para agendamento | gov.br FAQ (cita terminais BB/Caixa) | Comprovado (existência de barreira); nível exigido: **Pendente/lacuna** | Taxa de falha de autenticação | gov.br FAQ |
| F5 | Dados inconsistentes CNIS/eSocial/GFIP | J6 | Dados | Vínculo em duplicidade, salário divergente, data de demissão incorreta ou tipo de desligamento errado impedem habilitação automática | Falha de transmissão pelo empregador; erro de lançamento no eSocial/GFIP; inconsistência entre bases | Indeferimento automático; pendência; necessidade de recurso ou correção | Carga de recursos; fila em SRT; custo de análise manual | Res. 957/2022 (prevê que inconsistências impedem habilitação e geram exigência de correção) | **Comprovado** (previsão normativa de que inconsistências bloqueiam habilitação) | % requerimentos em pendência/exigência por inconsistência | Res. 957/2022; CGU/TCU |
| F6 | Requerimento não localizado ou com divergência | J5/J12 | Dados | Número do requerimento não encontrado ou dados do requerimento diferem dos registros do sistema | Erro de preenchimento pelo empregador; requerimento não transmitido; divergência de CPF/data | Bloqueio da solicitação; presencialização obrigatória | Fila na SRT/SINE | gov.br FAQ (pergunta 19) | Comprovado | % solicitações rejeitadas por requerimento inválido | gov.br FAQ |
| F7 | Indeferimento sem compreensão clara pelo cidadão | J7/J7a | Comunicação institucional | Notificação usa linguagem técnica/jurídica; cidadão não entende o motivo do indeferimento; não sabe se pode recorrer ou como | Comunicação institucional técnica; falta de linguagem simples | Inação; perda de prazo de recurso; busca de orientação no canal errado | Recursos mal instruídos; sobrecarga do 158 | CGU 2022 (relatório de avaliação); inferência | Evidência indireta | Taxa de recursos por indeferimento; índice de compreensão | CGU; gov.br FAQ |
| F8 | Recurso online com taxa de deferimento muito inferior ao presencial | J11 | Canal | Em 2022, o deferimento de recurso via digital foi de 18,6% (vs. 67,4% no presencial), em universo de 431.373 recursos. Cidadão online tem chance estruturalmente menor de reverter o indeferimento | Ausência de apoio humano no recurso digital; instrução documental inadequada; possível diferença de análise | Perda do benefício; iniquidade de acesso | Ineficiência do canal digital para recursos; pressão sobre o presencial | **Relatório de Avaliação CGU (BGSD 2022) — dado comprovado** | **Comprovado** | % deferimento de recurso por canal | CGU/BGSD 2022 |
| F9 | Falha de crédito em conta | J9 | Pagamento | Parcela emitida pelo sistema mas não creditada na conta indicada | Dados bancários incorretos; conta encerrada; banco rejeitou o TED; conta inválida | Cidadão fica sem o recurso no dia esperado | Atendimento Caixa; reprocessamento | gov.br FAQ; relatos | Comprovado | % falhas de crédito por parcela emitida | Caixa; gov.br FAQ |
| F10 | Cidadão sem Cartão Cidadão / sem senha / sem acesso digital | J9 | Pagamento | Cidadão não tem Cartão Cidadão, senha do cartão, acesso ao Caixa Tem ou conta bancária para receber | Não bancarização; perda/roubo do cartão; esquecimento de senha | Impossibilidade de saque; ida obrigatória à agência | Atendimento presencial; emissão de novo cartão | gov.br FAQ (pergunta 26); Caixa | Comprovado | % saques realizados na rede física vs. digital | Caixa; gov.br FAQ |
| F11 | Fila excessiva / abandono de chamada no 158 | J2 | Fila | Demanda supera capacidade da central; cidadão ouve "aguarde" ou "todos os atendentes ocupados" e abandona | Sazonalidade do benefício; eventos que geram pico de demanda; dimensionamento insuficiente | Não-atendimento; desinformação; frustração | Sobrecarga; indicadores de abandono | Relatos em Reclame Aqui; estrutura conhecida de centrais; _dado histórico de inauguração (2015): 157 PAs, ~26 mil ligações/dia — não representa capacidade atual_ | Evidência indireta | Taxa de abandono; TMA; % ligações atendidas vs. recebidas | Agência Gov 2025; Reclame Aqui |
| F12 | Transbordo inadequado / atendente sem acesso a dados de habilitação | J10 | Transbordo / integração sistêmica | Atendente do 0800 da Caixa não tem acesso aos sistemas de habilitação do MTE; só pode informar status de pagamento | Sistemas separados MTE/Caixa; não-integração de backstage | Não-resolução; cidadão reencaminhado | Custo de chamada transferida | Inferência arquitetura | Inferido | Taxa de resolução no primeiro contato (FCR) | Inferência |
| F13 | Linguagem difícil / siglas / baixa compreensão | J2/J7 | Comunicação institucional | Termos como CNIS, RSD, GRF, GFIP, exigência, suspensão, cancelamento não são compreendidos; cidadão age incorretamente | Comunicação técnica sem glossário; falta de UX writing | Erro de ação; perda de prazo; frustração | Recursos mal instruídos; sobrecarga de atendimento | CGU; inferência | Inferido | Pesquisa de satisfação; índice de compreensão | CGU; inferência |
| F14 | Acessibilidade para público vulnerável | J2/J9 | Acessibilidade | Idosos, PcD, pessoas sem alfabetização digital ou com dificuldade auditiva têm barreiras nos canais digitais e telefônicos | Barreira digital; falta de canal acessível alternativo | Exclusão; dependência de terceiros; ida presencial | Demanda presencial adicional | Lei 10.048/2000; inferência; canal PcD da Caixa (0800 726 2492) | Inferido | Atendimentos prioritários; % idosos e PcD que usam canal digital | Lei 10.048; Caixa |
| F15 | Falta de protocolo ou rastreabilidade no atendimento telefônico | J10 | Integração sistêmica | Cidadão não recebe comprovante do atendimento telefônico; não tem prova do que foi orientado ou prometido | Ausência de emissão de protocolo ao usuário; sistemas separados | Sem prova; disputa de orientações contraditórias | Litígio; reclamações | Lacuna — não comprovado para o fluxo SD | **Pendente/lacuna** | Existência de protocolo de atendimento ao usuário | Acórdão TCU; lacuna |
| F16 | Perda de prazo de recurso (120 dias) | J11 | Governança | Cidadão não recorre dentro do prazo de 120 dias contados da ciência do indeferimento | Desinformação sobre o prazo; demora em buscar orientação | Perda definitiva do benefício por via administrativa | Litígio judicial; demanda sobre TNU Tema 356 | Res. 957/2022 art. 27; TNU Tema 356 | Comprovado | % recursos intempestivos | Res. 957/2022; TNU |
| **F17** | **Perda de prazo por presunção de notificação digital** | **J7a** | **Decisão automática / governança** | **A notificação de indeferimento é disponibilizada digitalmente no ambiente do usuário. O prazo de recurso (120 dias) começa a correr a partir da disponibilização, independentemente de o cidadão ter acessado o sistema. Cidadão que não consulta regularmente perde o prazo sem saber.** | **Notificação digital sem proatividade suficiente (push/SMS/e-mail); baixa frequência de acesso ao portal** | **Perda definitiva do direito de recurso; perda do benefício** | **Demanda sobre TNU Tema 356; litígio** | **Res. 957/2022 art. 27; Lei 9.784/1999 art. 26 (analogia)** | **Evidência indireta** | **% recursos intempestivos; tempo médio entre notificação e protocolo de recurso** | **Res. 957/2022; CGU** |
| **F18** | **Recurso indeferido por exigir correção em base de origem** | **J11 / J11a** | **Dados / governança** | **O mérito do recurso é limitado a critérios normativos. Se o problema for em base externa (empregador não corrigiu eSocial/GFIP; vínculo não reconhecido judicialmente), o recurso é indeferido mesmo com razão substantiva. Cidadão precisa acionar o responsável pela base, não o MTE.** | **Erro em base de origem; empregador não retifica; dado judicial não inserido** | **Recurso indeferido; benefício não recebido; necessidade de ação judicial** | **Carga de recursos mal instruídos; análise manual desnecessária** | **Res. 957/2022 arts. 27-28; inferência técnica** | **Inferido** | **% recursos indeferidos por ausência de correção em base** | **Res. 957/2022; CGU** |
| **F19** | **Conta salário ou conta conjunta rejeitada** | **J9** | **Pagamento** | **Conta salário não aceita crédito de benefício social; conta conjunta pode ter restrições operacionais para pagamento de benefício. Parcela não é creditada.** | **Tipo de conta incompatível com o benefício** | **Parcela não creditada; necessidade de indicar nova conta ou usar via alternativa** | **Atendimento Caixa; reprocessamento** | **Res. 957/2022 (regras de conta para pagamento); inferência operacional** | **Inferido** | **% rejeições de crédito por tipo de conta** | **Res. 957/2022; Caixa** |
| **F20** | **Dados bancários incorretos informados pelo cidadão** | **J9** | **Pagamento** | **Cidadão informa banco, agência ou número de conta incorretos; TED é rejeitado; parcela não chega** | **Erro humano de digitação; conta encerrada não informada; desconhecimento do número correto** | **Parcela não recebida; necessidade de correção e reprocessamento** | **Atendimento Caixa; correção de dados; prazo para reprocessamento** | **gov.br FAQ; relatos; inferência operacional** | **Evidência indireta** | **% créditos rejeitados por dados bancários incorretos** | **gov.br FAQ; Caixa** |
| **F21** | **Parcela não sacada no prazo + devolução ao FAT** | **J9a** | **Pagamento** | **Parcela disponibilizada mas não sacada dentro do prazo definido (referido como ~67 dias) é devolvida ao FAT. Cidadão precisa solicitar reemissão por procedimento específico.** | **Desconhecimento do prazo; impossibilidade de saque; problema de saúde; falta de acesso** | **Perda imediata do acesso à parcela; necessidade de reemissão** | **Reemissão manual; carga operacional** | **Res. 957/2022 (prazo específico a confirmar no texto integral)** | **Evidência indireta — prazo específico (~67 dias) a confirmar** | **% parcelas devolvidas ao FAT por prazo expirado** | **Res. 957/2022; inferência operacional** |
| **F22** | **Contestação de recebimento de parcela** | **J9a / J10** | **Pagamento** | **Trabalhador afirma não ter recebido parcela que os sistemas registram como paga. Exige verificação de registro de autenticação arquivado pelo agente pagador e abertura de procedimento administrativo de contestação.** | **Erro bancário; fraude; crédito em conta que o cidadão não reconhece; problema de sistema** | **Cidadão sem o recurso; procedimento burocrático** | **Investigação interna Caixa; cruzamento de registros; possível ressarcimento** | **Res. 957/2022; inferência de operação de agente pagador** | **Inferido** | **Nº de contestações de recebimento por período** | **Res. 957/2022; Caixa** |
| **F23** | **Trabalhador doméstico fora do fluxo digital comum** | **J3 / J12** | **Canal / acessibilidade** | **Empregado doméstico não pode solicitar pelo portal gov.br da mesma forma que trabalhador formal. Depende de agendamento pelo 158 ou atendimento presencial, impondo barreira de canal e deslocamento.** | **LC 150/2015; fluxo operacional diferenciado** | **Impossibilidade de usar canal digital padrão; custo de deslocamento; fila presencial** | **Demanda presencial adicional; sobrecarga de SRT/SINE** | **LC 150/2015; gov.br FAQ** | **Comprovado** | **% trabalhadores domésticos atendidos por canal; tempo médio de atendimento** | **LC 150/2015; gov.br** |
| **F24** | **Falha de cadastro gov.br + dependência de terminal bancário** | **J3 / J4** | **Autenticação** | **Cidadão sem conta gov.br suficiente para acessar o serviço SD precisa ir a terminal de Banco do Brasil ou Caixa para elevar o nível da conta. Se estiver em município sem essas instituições, o acesso digital fica inviável.** | **Exclusão digital; ausência de infraestrutura bancária no município** | **Bloqueio de acesso ao canal digital; deslocamento; custo** | **Migração ao presencial; sobrecarga de SRT/SINE** | **gov.br FAQ (cita terminais BB/Caixa como alternativa)** | **Comprovado** | **% solicitações feitas por canal digital vs. presencial por região/município** | **gov.br FAQ** |
| **F25** | **Falta de internet — desvio obrigatório para presencial** | **J3 / J5 / J11** | **Canal / acessibilidade** | **Cidadão sem acesso à internet em casa ou em local próximo não consegue usar o canal digital (gov.br/app); é forçado ao atendimento presencial com custos de deslocamento e fila** | **Exclusão digital; concentração de infraestrutura** | **Custo de deslocamento; fila; perda de dia de trabalho eventual** | **Demanda presencial adicional; custo de atendimento por cidadão superior** | **Inferência de exclusão digital; gov.br FAQ (cita necessidade de acesso digital)** | **Inferido** | **% solicitações presenciais vs. digitais por região; taxa de domicílios sem internet por município** | **IBGE; CGU; gov.br** |
| **F26** | **Suspensão por reemprego, BPC ou recusa de recolocação — sem compreensão** | **J7 / J7a** | **Decisão automática / comunicação** | **O benefício é suspenso automaticamente quando o sistema detecta reemprego, concessão de BPC ou recusa de proposta de emprego adequada (Res. 957/2022 art. 22). Cidadão pode desconhecer o motivo; acreditar que é erro; buscar recurso de forma inadequada.** | **Cruzamento automático de bases (eSocial/CAGED/INSS/SINE); comunicação insuficiente do motivo** | **Perda da parcela; confusão; recurso desnecessário; busca no canal errado** | **Recursos infundados; carga da Secretaria de Trabalho** | **Res. 957/2022 art. 22** | **Comprovado (hipótese normativa); ocorrência real: evidência indireta** | **Nº de suspensões por motivo; % suspensões contestadas** | **Res. 957/2022; CGU** |
## 8. Mapa de atores revisado (v2)

### Atores confirmados — mantidos com ajustes

**MTE (Ministério do Trabalho e Emprego):** confirmado como responsável por política, habilitação, concessão, recurso (instância única via Secretaria de Trabalho, Res. 957/2022 art. 28) e canal 158. Ator central frontstage/backstage.

**Caixa Econômica Federal:** confirmada como Agente Pagador (Lei 7.998/1990); canal 0800 726 0207; rede de pagamento (agências, lotéricas, CAIXA Aqui, Caixa Tem, Cartão Cidadão). **Não habilita.** Possui contact center com URA (Acórdão TCU 1151/2018). Outros SAC: 0800 726 0101; Ouvidoria 0800 725 7474; PcD 0800 726 2492; WhatsApp 0800 104 0104.

**DATAPREV:** ator tecnológico/processador técnico da triagem automatizada; mantém e processa CNIS. Contrato com MTE. **Competência decisória de habilitação é do MTE, não da DATAPREV.** (Correção da v1.)

**CODEFAT/FAT:** governança normativa (Resoluções CODEFAT) e financiamento. Backstage.

**SINE/SRT:** atendimento presencial, correção de divergências, recurso presencial, fallback. Frontstage presencial.

**Ouvidoria/CGU/Fala.BR:** manifestações e controle social (Lei 13.460/2017; Decreto 9.492/2018). Backstage de controle.

**Empregador / Empregador Web:** gera e transmite requerimento; erro nessa etapa é causa-raiz de vários fail points (F5, F6, F18). Ator de entrada crítico.

**AGU / órgão jurídico competente:** validação de documento judicial em fluxos de exceção (J11a). Backstage de exceção.

**SERPRO / infraestrutura gov.br:** autenticação e acesso ao canal digital. Backstage tecnológico.

### Atores reclassificados

**CTIS Tecnologia S.A.:** confirmada como operadora de contact center da Caixa **apenas no período do Contrato 8629/2017 (PE 59/2017-Gilog/BR)**. A expressão "e sucessores confirmados" foi removida. **Operador atual: pendente/em-aberto** (Pregão 013/5688-2024 não homologado localizado publicamente).

**"URA da Caixa para Seguro-Desemprego":** **removida como entidade específica** confirmada. Mantida como **hipótese/lacuna**. A infraestrutura de URA da Caixa existe (TCU 1151/2018), mas a opção nominal, o menu específico e a integração com o fluxo de SD **não são comprovados**.

### Atores novos adicionados nesta versão

**Sistema SD / DATAPREV — distinção:** separação entre competência técnica (DATAPREV como processador) e competência decisória (MTE via Sistema SD). Ambos são atores de backstider mas com papéis distintos.

**Secretaria de Trabalho (MTE):** ator específico de backstider para julgamento de recursos administrativos (instância única, Res. 957/2022 art. 28). Unidade interna responsável operacionalmente: **em-aberto**.

**Banco do Brasil (terminal gov.br):** identificado como alternativa para elevação de nível da conta gov.br quando cidadão não tem acesso digital suficiente (F24). Ator periférico mas relevante para fail point de autenticação.

---

## 9. Lacunas de evidência (v2)

As lacunas abaixo são questões que **só podem ser respondidas** por entrevista, LAI, observação, teste de chamada (mystery caller), auditoria interna ou documentação não pública.

| # | Lacuna | Por que é crítica para o blueprint | Como obter |
|---|---|---|---|
| L1 | Menu/árvore de decisão real da URA da Caixa (0800 726 0207) | Sem ela, a raia telefônica da Caixa no blueprint é lacunar | Mystery caller estruturado; LAI; pedido de TR do Pregão 013/5688-2024 |
| L2 | Opção nominal "seguro-desemprego" no menu da Caixa | Define se há roteamento específico ou genérico para SD | Mystery caller; LAI |
| L3 | Uso de ASR/NLP/voicebot na Caixa ou no 158 | Define se há IA no frontstage e quais fail points de reconhecimento/intenção se aplicam | LAI; edital; entrevista com gestores |
| L4 | Integração técnica entre 0800 Caixa e sistemas de retaguarda do SD (MTE/DATAPREV) | Determina o escopo resolutivo do canal da Caixa para SD | Entrevista; LAI; análise de TR |
| L5 | Nível de conta gov.br exigido para acesso ao serviço SD | Afeta fail point F4 e F24; determina a barreira real de autenticação | Teste de tela; FAQ oficial; Carta de Serviços |
| L6 | Texto literal das telas de confirmação (J5) e de recurso (J11) | Afeta as evidências físicas do frontstage digital | Teste de tela; print oficial; manual de sistema |
| L7 | Formatos e limites de tamanho de anexos no recurso digital (J11) | Fail point operacional para instrução do recurso | Teste de tela; FAQ; manual |
| L8 | Dados de fila, TMA, abandono e transbordo do 158 e do 0800 — atuais | KPIs essenciais para o blueprint e para dimensionamento | LAI ao MTE e à Caixa; relatório de gestão de contratos |
| L9 | Empresa atualmente operadora do contact center da Caixa (pós Pregão 013/5688-2024) | Ator de bastider tecnológico não identificado | LAI; COMPRASNET; DOU |
| L10 | Prazo exato de disponibilidade da parcela antes da devolução ao FAT (~67 dias) | Determina fail point F21 e o design do fluxo de pagamento excepcional | Texto integral da Res. 957/2022; instruções operacionais; LAI |
| L11 | Período de retenção de registros de autenticação de pagamento pelo agente pagador | Determina fail point F22 e a rastreabilidade de contestações | Texto regulatório; LAI; contrato com Caixa |
| L12 | Aplicação específica da presunção de ciência digital ao SD (análogo ao art. 26 da Lei 9.784/1999) | Fail point F17 — perda de prazo por notificação | Norma específica; instrução normativa; LAI ao MTE |
| L13 | Scripts/manuais de atendimento nos dois canais | Padronização do frontstage; identificação de falhas de orientação | LAI; entrevistas |
| L14 | Gravações de chamada; logs de URA; tabulações e motivos de contato | Validação do blueprint telefônico; cálculo de fail points por tipo | LAI; análise de contrato; acesso negociado |
| L15 | Unidade interna responsável pelo julgamento de recursos (CGSAP?) e sistema operacional usado (BGSD?) | Ator e sistema de backstider do recurso — imprescindível para o blueprint | LAI; entrevista com gestores MTE |

---

## 10. Recomendações para a próxima etapa de pesquisa

_(Sem desenho de solução. Foco na validação do AS-IS.)_

**1. Mystery caller estruturado (prioridade máxima)**
Ligar para 158 e 0800 726 0207 com roteiros idênticos cobrindo:
- Consulta de status de habilitação;
- Consulta de data/valor de parcela;
- Situação de falha de crédito;
- Intenção de interpor recurso.
Registrar: opções de menu, tempo de espera, transbordo, protocolo emitido, resolução ou encaminhamento.

**2. Pedidos LAI via Fala.BR (prioridade alta)**
- Ao **MTE:** árvore do menu 158; SLAs; dados de fila/TMA/abandono; unidade responsável por recursos; sistema operacional de análise; texto da instrução de notificação digital.
- À **Caixa:** TR/edital Pregão 013/5688-2024; menu da URA 0800; script de atendimento para SD; TMA; abandono; taxa de FCR.
- À **DATAPREV:** detalhe do papel técnico no processamento de habilitação.

**3. Extrair dados de reclamações (Fala.BR + Reclame Aqui) para F1 e F8**
Quantificar, por assunto e canal, o fail point de "jogo de empurra" e a baixa taxa de deferimento de recurso digital. O dado de 18,6% vs. 67,4% (CGU 2022) deve ser atualizado para o período corrente.

**4. Entrevistas com gestores e atendentes**
- Gestores da CGSAP/MTE sobre fluxo de análise de recurso, sistema operacional e gargalos.
- Atendentes do 158 sobre casos típicos, fail points e transbordo.
- Atendentes de SRT/SINE sobre os casos mais frequentes de presencialização involuntária.

**5. Teste de tela no portal gov.br (serviço SD)**
Documentar: tela de login, requisitos de nível de conta, tela de confirmação (J5), tela de notificação (J7a), tela de recurso (J11) — capturas de tela com data.

**6. Análise do texto integral da Resolução CODEFAT nº 957/2022 e Res. 1027/2025**
Localizar: artigo sobre prazo de disponibilidade de parcela (~67 dias?); regras de presunção de ciência; procedimento de contestação de recebimento; período de retenção de registros.

**7. Cruzamento com Acórdãos TCU posteriores a 2018**
Buscar acórdãos sobre contact center Caixa e seguro-desemprego pós-2018 no sítio do TCU.

**8. Verificar Carta de Serviços da Caixa e do MTE**
Documentos obrigatórios pela Lei 13.460/2017 e Decreto 9.094/2017; podem conter SLAs, canais, prazos e etapas do serviço de forma padronizada.

---

## 11. Checklist para construção posterior do Service Blueprint AS-IS

| Camada do blueprint | A pesquisa (v2) permite preencher? | Observação |
|---|---|---|
| Ações do cidadão (frontstage) | **Sim (alto)** | Jornada J0–J13 bem documentada em fonte oficial; sub-etapas de pagamento expandidas |
| Evidências físicas — canal digital | **Sim (médio-alto)** | Requerimento, notificação, extrato, comprovante: comprovados; tela de confirmação e tela de recurso: inferidas |
| Evidências físicas — canal telefônico Caixa | **Não (baixo)** | Menu, protocolo, log: lacuna — mystery caller e LAI necessários |
| Frontstage — canal 158 | **Sim (médio-alto)** | Menu eletrônico + transbordo documentados; TMA/abandono/scripts: lacuna |
| Frontstage — canal 0800 Caixa | **Parcial** | Canal confirmado para pagamento/SD; opção específica e escopo: lacuna |
| Backstage — MTE/DATAPREV | **Sim (médio-alto)** | Verificação automática, bases, recurso, notificação: documentados; sistema operacional e unidade de recurso: em-aberto |
| Backstage — Caixa (pagamento) | **Sim (médio-alto)** | Lote, Caixa Tem, saque, arquivamento: documentados; prazo específico e contestação: inferidos |
| Backstage — contact center Caixa | **Não (baixo)** | Infraestrutura URA comprovada; operação específica SD: lacuna |
| Sistemas de suporte | **Sim (médio)** | CNIS/eSocial/GFIP/CAGED/Sistema SD/Caixa Tem: confirmados; integração telefônica: lacuna |
| Regras/normativos | **Sim (alto)** | Matriz normativa completa; lacuna em norma de presunção de ciência digital |
| Fail points | **Sim (médio-alto)** | 26 fail points; mix de comprovado, evidência indireta e inferido |
| Métricas operacionais | **Não (baixo)** | Único dado robusto: % deferimento de recurso por canal (CGU 2022); fila/TMA/abandono: lacuna total |
| Lacunas mapeadas | **Sim (completo)** | 15 lacunas detalhadas com método de obtenção |

---

## Nota metodológica final — escalas de evidência utilizadas (v2)

| Nível | Definição | Exemplos neste relatório |
|---|---|---|
| **Comprovado** | Fonte oficial pública afirma diretamente o fato (lei, resolução, página oficial, edital, relatório público, acórdão) | Res. 957/2022; govbr; Lei 7.998; CGU 2022; TCU 1151/2018 |
| **Evidência indireta** | Fonte oficial tangencia ou sugere o fato; relato anedótico consistente; estrutura normativa que implica o fato sem comprová-lo | Jogo de empurra (Reclame Aqui + estrutura institucional); prazo de disponibilidade da parcela; presunção de ciência digital |
| **Inferido** | Plausível por arquitetura de call center, URA, atendimento público ou operação de benefícios; sem fonte pública direta | Protocolo de atendimento telefônico Caixa; log de URA; integração de bastider; termo de aceite digital |
| **Pendente/lacuna** | Elemento central para o serviço; não localizado em fonte pública confiável; exige pesquisa de campo, LAI ou acesso interno | Menu da URA Caixa; nível gov.br exigido; formatos de anexo no recurso; dados de fila/TMA |
| **Em-aberto** | Ponto válido levantado pela auditoria sem fonte suficiente para fechar em nenhuma das categorias acima; registrado explicitamente para próxima etapa | CGSAP como unidade de recurso; BGSD como sistema operacional; operador atual do contact center Caixa |
