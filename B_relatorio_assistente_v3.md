# Relatório — Assistente 1 · v3 (versão final após audit_v2)

- **Ferramenta:** Claude Sonnet 4.6
- **Data:** 2026-06-13
- **Link da conversa:** https://claude.ai/public/artifacts/aa2d579e-37a0-49ec-9f98-1dc72f5a60fc


# Relatório de Insumos para Service Blueprint AS-IS — Atendimento ao Seguro-Desemprego por Canal Telefônico/URA
## **Versão 3.0 — Revisão final pós-auditoria v2**

---

## REGISTRO DE TRATAMENTO DA AUDITORIA v2

Cada achado da segunda auditoria recebeu um dos três tratamentos: **(a) Corrigido**, **(b) Defendido** com argumento e evidência, ou **(c) Em-aberto** com justificativa explícita.

| Ref. audit_v2 | Achado | Ação | Seção afetada |
|---|---|---|---|
| §2.1 | CAGED reapareceu em B_EMP e B_RECURSO após remoção declarada | (a) Corrigido — CAGED removido de ambos os registros | §4 bastidor: B_EMP, B_RECURSO |
| §2.3 | F4/F24 ainda dependem de "nível insuficiente" como barreira quase comprovada | **(a) Corrigido + (c) Em-aberto** — a premissa de "nível mínimo" foi **removida** da formulação de F4/F24 (a); porém o **nível mínimo de conta gov.br efetivamente exigido para este serviço permanece como lacuna** (L5), não fechável em fonte pública — registrado explicitamente como Pendente/lacuna (c), e não dado como resolvido | §7: F4, F24 |
| §2.5 | Anexos recurso (JPG/PNG/PDF ≤1 MB) deixados como pendente/lacuna quando FAQ oficial confirma | (a) Corrigido — reclassificado como Comprovado com citação da FAQ | §5: E13; §3: J11 |
| §3.1 | J7a/F17: presunção de ciência automática por mera disponibilização superafirmada sem fonte específica | **(a) Corrigido + (c) Em-aberto** — a afirmação de "ciência automática por mera disponibilização" foi **removida** e a Lei 9.784/1999 rebaixada de "análoga" para "referência conceitual" (a); o **marco exato de ciência digital** (disponibilização × acesso efetivo × push/SMS) **continua como lacuna normativa específica** (L12), mantido como Pendente/lacuna (c) — não há, em fonte consultada, dispositivo que o fixe para o SD | §3: J7a; §4: B_NOTIF; §7: F17 |
| §3.2 | Prazos de LAI (20+20) e ouvidoria (20+40) incorretos | (a) Corrigido — LAI: 20 + 10 dias; ouvidoria (Lei 13.460): 30 + 30 dias | §3: J13; §6: normativos |
| §3.3 | Res. 1027/2025 tratada como atualização genérica do SD formal | (a) Corrigido — movida para subseção de modalidades específicas; conteúdo restrito ao pescador artesanal; Res. 1035/2026 adicionada | §6: normativos |
| §3.4 | 67 dias (art. 21), devolução ao FAT, reemissão 2 anos, arquivamento 5 anos (art. 20 §4), contestação (art. 20 §5) e GRU (art. 25) deixados como "evidência indireta/a confirmar" | (a) Corrigido — todos reclassificados como Comprovado com artigo específico da Res. 957/2022 | §3: J9a; §4: B_PRAZO_FAT, B_CONTEST, B_PAGTO_LOTE; §5: E_NEW_1, E_NEW_3; §7: F21, F22 |
| §3.5 | F19 (conta salário/conjunta) classificado como Inferido quando FAQ oficial comprova | (a) Corrigido — reclassificado como Comprovado; F20 também atualizado | §7: F19, F20 |
| §3.6 | F26 mistura suspensão (art. 22) e cancelamento (art. 23); "BPC" confunde benefício previdenciário com BPC/LOAS | (a) Corrigido — F26 separado em dois fail points: F26 (suspensão, art. 22) e F27 (cancelamento, art. 23); terminologia corrigida | §7: F26, F27 (novo) |
| §3.7 | B_EMP: TRCT descrito como "transmitido via Empregador Web" junto ao requerimento | (a) Corrigido — separados: requerimento é transmitido via Empregador Web; TRCT permanece como evidência documental física/digital da rescisão | §4: B_EMP |
| §2.8 nota | Termo de aceite (B_ACEITE) classificado como Inferido; Res. 957/2022 dá base mais forte | (a) Corrigido — reclassificado para Evidência indireta com citação da Res. 957/2022 | §4: B_ACEITE |
| §2.8 risco | "Jogo de empurra" (F1) descrito como "fenômeno estruturalmente esperado" — risco de virar evidência empírica | **(b) Defendido** — a classificação de F1 é **mantida em Evidência indireta** (relatos anedóticos + inferência estrutural), e **não elevada a Comprovado**: a separação institucional Caixa (pagamento) × MTE (habilitação) é fato comprovado (Lei 7.998/1990; Res. 957/2022 art. 28) e torna o fail point estruturalmente esperado, mas a *frequência real* não tem medição pública. O nível de evidência sustenta a inferência sem afirmá-la como dado empírico | §7: F1 |

**Resumo dos tratamentos:** **9 (a) Corrigido** integrais · **1 (b) Defendido** (F1, mantido como Evidência indireta com justificativa) · **2 com componente (c) Em-aberto residual** — o **nível mínimo de conta gov.br** (L5) e o **marco exato de ciência da notificação digital** (L12). Estes dois últimos **não foram "resolvidos no papel"**: são lacunas que só se fecham por LAI, manual do sistema ou teste, e seguem marcados como Pendente/lacuna no corpo do relatório.

---

## 1. Resumo executivo (v3)

**Achado central — mantido nas três versões:** a hipótese de uma "URA da Caixa específica para Seguro-Desemprego" **não se confirma** em fonte pública oficial. Existem dois canais telefônicos com responsabilidades separadas: a **Central Alô Trabalho 158** (MTE), para orientação, informação e suporte à habilitação/recurso; e o **0800 726 0207** (Caixa Econômica Federal), para pagamento/saque/crédito de benefícios sociais.

**Correções materiais da v3 em relação à v2:**

- **CAGED definitivamente removido** de todos os fluxos de habilitação e recurso. Bases corretas conforme Res. 957/2022: CNIS, GRF, GFIP, eSocial e documento judicial.
- **J7a e F17 reescritos**: a Res. 957/2022 comprova que a notificação pode ser exclusivamente digital e que o prazo de recurso é de 120 dias contados da notificação; o marco exato de ciência digital (disponibilização, acesso efetivo, push, SMS) continua como lacuna normativa específica.
- **Seis itens reclassificados de "evidência indireta" para Comprovado**, com artigo específico da Res. 957/2022: prazo de 67 dias (art. 21), devolução ao FAT (art. 21), reemissão em até 2 anos (art. 21), registro de pagamento por 5 anos (art. 20 §4), contestação de recebimento (art. 20 §5) e GRU de restituição (art. 25).
- **Formatos de anexo no recurso reclassificados** de "pendente/lacuna" para Comprovado: FAQ oficial confirma JPG, PNG ou PDF; máximo de 1 MB por arquivo e 10 MB total.
- **F19 e F20 reclassificados** de Inferido para Comprovado com base em FAQ oficial (conta salário e conta conjunta não aceitas; titularidade exigida).
- **F26 dividido em F26 (suspensão, art. 22) e F27 (cancelamento, art. 23)**; terminologia "BPC" substituída por "benefício previdenciário de prestação continuada" para evitar confusão com BPC/LOAS (Lei 8.742/1993).
- **Prazos corrigidos:** LAI = 20 + 10 dias; ouvidoria (Lei 13.460/2017) = 30 + 30 dias.
- **Res. 1027/2025 restrita ao pescador artesanal**; Res. 1035/2026 adicionada.
- **B_EMP corrigido**: TRCT separado do requerimento; CAGED removido.

**Confirmações mantidas das versões anteriores:**
- MTE: responsável pela habilitação, concessão e recurso (instância única, Secretaria de Trabalho, Res. 957/2022 art. 28).
- Caixa: agente pagador. Não habilita.
- Dado mais robusto disponível: deferimento de recurso — 67,4% presencial vs. 18,6% digital (CGU/BGSD, 2022; 431.373 recursos).

**Lacunas que permanecem intactas** (mystery caller e LAI obrigatórios):
Menu/árvore da URA Caixa; nível mínimo gov.br para o serviço; texto literal das telas; marco exato de ciência da notificação digital; operador atual do contact center Caixa; TMA/abandono/FCR de ambos os canais.
## 2. Delimitação do objeto (v3)

### 2.1 Comprovadamente MTE / Central 158

- A Central Alô Trabalho 158 é o canal oficial do MTE para informações sobre seguro-desemprego, abono salarial, CTPS Digital, CAGED e legislação trabalhista.
- **Horário vigente:** 7h às 22h, segunda a sábado (ampliado a partir de 20/03/2024; nota MTE, 21/03/2024). Gratuita de telefone fixo; celular pode ser tarifado.
- Atendimento eletrônico com menu pré-gravado e opção de transbordo a atendente humano (gov.br).
- **Volume recente (2025):** 1.726.914 atendimentos no 1º semestre de 2025; seguro-desemprego = 23% das demandas; abono salarial = 48% (Agência Gov, ago/2025). Dado histórico de inauguração (2015: 157 PAs, ~26 mil ligações/dia) mantido apenas como baseline histórico — não representa dimensionamento atual.
- Canal de agendamento para SRTs e canal preferencial para trabalhador doméstico (LC 150/2015).

### 2.2 Comprovadamente Caixa / pagamento

- Caixa é Agente Pagador (Lei 7.998/1990). Não habilita.
- Canal: **0800 726 0207** ("PIS, Benefícios Sociais, FGTS e Cartão Social"). Eletrônico 24h; humano seg-sex 8h–21h, sab 10h–16h (caixa.gov.br). Outros canais: SAC 0800 726 0101; Ouvidoria 0800 725 7474; PcD auditiva 0800 726 2492; WhatsApp 0800 104 0104.
- Formas de pagamento: conta indicada (TED); conta Caixa selecionada automaticamente; Poupança Social Digital/Caixa Tem (Lei 14.075/2020, limite R$ 5.000/mês); Cartão Cidadão + senha na rede física; saque em agência com documento.
- **Escopo exato do 0800 para seguro-desemprego além de pagamento/saque:** pendente de confirmação por teste ou fonte específica.

### 2.3 Lacuna sobre "URA da Caixa para Seguro-Desemprego"

- **Comprovado (infraestrutura):** a Caixa tem solução de contact center/URA com CERATs e dois Data Centers (Acórdão TCU 1151/2018-Plenário, TC 023.621/2017-6). Pregão 013/5688-2024 confirma contratação ativa; homologação e operador atual não localizados publicamente.
- **Não comprovados (lacuna):** opção nominal "seguro-desemprego" no menu; árvore de decisão; ASR/NLP/voicebot; transbordo específico para SD; integração com sistemas MTE/DATAPREV.
- **CTIS Tecnologia S.A.:** confirmada apenas no Contrato 8629/2017 (PE 59/2017-Gilog/BR). Operador atual: em-aberto.

---

## 3. Tabela da jornada do cidadão (v3)

> **Correções v3:** J7a reescrita (presunção de ciência removida; marco exato como lacuna); J11 atualizado com formatos de anexo comprovados (FAQ); J13 com prazo corrigido (30+30). J9a: 67 dias, devolução ao FAT e reemissão comprovados (art. 21).

| ID | Etapa | Objetivo do cidadão | Canal | Ação do cidadão | Resposta percebida | Evidência física/digital | Resultado possível | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|
| **J0** | **Pré-jornada — rescisão e geração do requerimento** | — | Empregador / Empregador Web | Empregador registra as informações da dispensa e gera o Requerimento do SD via Empregador Web com certificado digital ICP-Brasil; preenche campos obrigatórios (tipo demissão, datas, CBO, remuneração); o TRCT permanece como evidência documental da rescisão | Trabalhador recebe requerimento (número de 10 dígitos iniciando em "77") e TRCT | Requerimento do SD; TRCT | Requerimento entregue corretamente, com divergência ou não entregue | gov.br (Empregador Web); Res. 957/2022; MTE | Comprovado |
| **J1** | Dispensa — receber o requerimento | Obter o documento para dar entrada | Empregador | Recebe formulário do Requerimento do SD | Documento com dados da rescisão | Requerimento físico/digital | Tem ou não o documento | gov.br FAQ; Res. 957/2022 | Comprovado |
| **J2** | Busca de informação | Saber se tem direito, como solicitar, prazos | 158 / gov.br / app CTPS Digital | Liga 158 ou acessa portal | Menu pré-gravado; orientação de atendente; FAQ digital | Áudio URA 158; tela FAQ | Orientação; agendamento; direcionamento a canal digital | gov.br FAQ; Agência Gov | Comprovado |
| **J3** | Acesso ao canal de solicitação | Requerer o benefício | gov.br / app CTPS Digital | Login com conta gov.br; _trabalhador doméstico: agendamento pelo 158_ | Tela de login ou confirmação de agendamento | Conta gov.br | Autenticado; bloqueado por dificuldade de cadastro (F4, F24); doméstico → agendamento presencial (F23) | gov.br (serviço) | Comprovado |
| *(nível gov.br)* | *(detalhe de J3)* | Autenticar-se | gov.br | Fornece credenciais | Acesso liberado ou necessidade de apoio | Token gov.br | Prossegue ou precisa de apoio presencial/terminal bancário | gov.br FAQ | **Pendente/lacuna** — nível mínimo exigido não comprovado; a confirmar por teste ou FAQ oficial |
| **J4** | Informar número do requerimento e dados | Iniciar a solicitação | gov.br / app | Informa nº do requerimento; dados validados | Validação de dados | Tela de validação; número do requerimento | Dados válidos → prossegue; divergência → J11a/J12 | gov.br FAQ | Comprovado |
| **J5** | Confirmação da solicitação e aceite do termo | Formalizar a solicitação | gov.br / app | Lê e confirma termo declaratório/aceite; conclui envio | Tela de confirmação com informação sobre parcelas e prazo | Tela de confirmação *(texto literal a confirmar)*; protocolo | Solicitação recebida; aguarda processamento | Res. 957/2022; gov.br FAQ | Tela/texto literal: **Inferido**; existência de confirmação e termo de aceite: **Evidência indireta** |
| **J6** | Verificação automática (bastidor) | — | Sistema SD / DATAPREV | Nenhuma ação — processamento automático | Nada imediatamente visível; resultado disponibilizado após processamento | — | Deferido / indeferido / pendência / exigência | Res. 957/2022; IBGE metadados MTE | Comprovado (verificação automática); prazo exato de resposta: **Evidência indireta** |
| **J7** | Consultar resultado | Ver se foi deferido | gov.br / app / 158 | Acessa o serviço ou liga | Notificação: deferimento, indeferimento, pendência, suspensão ou cancelamento | Notificação digital | 5 desfechos possíveis | Res. 957/2022; gov.br FAQ | Comprovado |
| **J7a** | **Ciência da notificação digital** *(etapa autônoma — nova em v2)* | Tomar conhecimento formal da decisão | gov.br / app | Acessa a notificação disponibilizada no ambiente digital | Conteúdo da decisão; data de disponibilização registrada | Notificação digital | Prazo de 120 dias para recurso começa a contar da notificação (Res. 957/2022 art. 27); F17 ocorre quando o cidadão não acessa a tempo | Res. 957/2022 art. 27 | **Notificação digital e prazo de 120 dias: Comprovado.** Marco exato de ciência (disponibilização, acesso efetivo, push/SMS): **Pendente/lacuna** — a confirmar em norma específica, instrução operacional ou teste |
| **J8** | Acompanhar parcelas | Ver datas e valores | gov.br / app CTPS Digital / 158 | Consulta calendário | Quantidade e datas de parcelas | Tela de parcelas; extrato digital | Acompanhamento | gov.br | Comprovado (canal digital); 0800 Caixa como canal de consulta: **escopo a confirmar** |
| **J9** | Receber pagamento | Ter a parcela creditada | Conta bancária / Poupança Social Digital / Caixa Tem | Verifica crédito | Crédito na conta ou ausência | Extrato bancário; extrato Caixa Tem | Pago com sucesso; ou falha de crédito → J10 | Caixa; Lei 14.075/2020 | Comprovado |
| **J9a** | **Pagamento excepcional / fallback de saque** | Sacar por via alternativa; ou lidar com prazo expirado | Rede física Caixa (lotérica, autoatendimento, agência) | Saca com Cartão Cidadão/senha ou comparece à agência; ou descobre que parcela foi devolvida ao FAT | Saque realizado; ou comunicação de que parcela expirou | Comprovante de saque; extrato | Saque realizado; ou parcela devolvida ao FAT após 67 dias corridos (art. 21) e reemissão possível em até 2 anos (art. 21) | Res. 957/2022 art. 21; Caixa | **Comprovado** (art. 21 da Res. 957/2022) |
| **J10** | Resolver falha de crédito | Receber parcela não creditada | 0800 726 0207 (Caixa) / agência Caixa / 158 | Liga; informa dados; corrige conta; ou enfrenta jogo de empurra (F1) | Orientação; encaminhamento; ou "procure o MTE" | Protocolo (existência inferida) | Resolução; reencaminhamento; correção de dados | Caixa; gov.br FAQ; relatos | Evidência indireta |
| **J11** | Interpor recurso | Reverter indeferimento, suspensão ou cancelamento | gov.br / app / 158 para agendamento / SRT presencial | Acessa tela de recurso; preenche motivo; **anexa arquivos em JPG, PNG ou PDF (máximo 1 MB por arquivo; total máximo 10 MB)**; ou agenda presencial | Protocolo de recurso | Tela de recurso; arquivos anexados; protocolo | Recurso em análise (Secretaria de Trabalho, Res. 957/2022 art. 28) | Res. 957/2022 arts. 27-28; **FAQ oficial (formatos e limites de anexo)** | **Comprovado** |
| **J11a** | **Correção de dados em base externa** | Corrigir dado que causou o indeferimento | Empregador / Junta Comercial / Justiça do Trabalho / SINE/SRT | Solicita retificação no eSocial/GFIP ao empregador; busca documentação judicial; atende exigência na SRT | Confirmação de retificação; novo processamento | Documentos de retificação; GFIP corrigida; documento judicial | Reprocessamento automático ou recurso instruído com nova documentação | Res. 957/2022 arts. 6º, 27; gov.br FAQ (pergunta 19) | Comprovado (possibilidade de exigência); fluxo operacional: **Inferido** |
| **J12** | Atendimento presencial | Corrigir divergência ou requerer pessoalmente | SRT / SINE (agendado pelo 158) | Comparece com documentos; preenche termo declaratório presencial | Atendimento humano; análise; orientação | Senha; protocolo; termo declaratório | Correção; habilitação; nova pendência | gov.br FAQ; Res. 957/2022 arts. 6º, 18 | Comprovado |
| **J13** | Registrar manifestação | Reclamar, denunciar ou sugerir | Fala.BR / Ouvidoria MTE / Ouvidoria Caixa 0800 725 7474 | Registra manifestação | Protocolo; **resposta em até 30 dias (prorrogável por mais 30 dias, mediante justificativa)** | Protocolo Fala.BR; resposta formal | Resposta; encaminhamento; providência | Lei 13.460/2017; **Decreto 9.492/2018** | Comprovado |
## 4. Tabela de processos de bastidor (v3)

> **Correções v3:**
> - **B_EMP:** CAGED removido; TRCT separado do requerimento.
> - **B_HABILITACAO:** CAGED definitivamente removido; bases corretas = CNIS, GRF, GFIP, eSocial, doc. judicial.
> - **B_RECURSO:** CAGED removido das bases externas.
> - **B_ACEITE:** reclassificado de Inferido para Evidência indireta (Res. 957/2022 prevê termo declaratório).
> - **B_NOTIF:** reescrito — sem afirmação de presunção automática de ciência; marco exato = lacuna.
> - **B_PAGTO_LOTE:** arquivamento de 5 anos reclassificado como Comprovado (art. 20 §4).
> - **B_PRAZO_FAT:** 67 dias, devolução ao FAT e reemissão em 2 anos reclassificados como Comprovado (art. 21).
> - **B_CONTEST:** contestação de recebimento reclassificada como Comprovado (art. 20 §5).

| ID | Etapa | Ator de bastidor | Tipo | Atividade interna | Sistema/base usada | Entrada | Saída | Visível ao cidadão? | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|---|
| **B_EMP** | J0 | Empregador / Empregador Web | Humano/sistema | Registra as informações da dispensa e transmite o Requerimento do SD via Empregador Web, com certificado digital ICP-Brasil; preenche campos obrigatórios (tipo demissão, data rescisão, CBO, remuneração); o TRCT é gerado como evidência documental da rescisão, não transmitido pela mesma via | Empregador Web (MTE); eSocial; GFIP | Dados da rescisão | Requerimento do SD disponível para o trabalhador (número "77…"); TRCT entregue ao trabalhador | Não | gov.br (Empregador Web); Res. 957/2022; CLT | Comprovado |
| **B_HABILITACAO** | J5–J6 | Sistema SD (competência decisória do MTE) / DATAPREV (processador técnico) | IA/sistema | Triagem automatizada: verifica critérios de habilitação com base em **CNIS, GRF (Guia de Recolhimento do FGTS), GFIP, eSocial e documento judicial** quando cabível. CAGED **não** integra o rol ordinário de bases de aferição da habilitação conforme Res. 957/2022. DATAPREV atua como processador técnico; competência decisória é do MTE. | CNIS; GRF; GFIP; eSocial; documento judicial | Requerimento + dados do cidadão | Resultado: deferido / indeferido / pendência / exigência | Não | **Res. 957/2022** (bases listadas); dataprev.gov.br; IBGE metadados MTE | Comprovado (bases e verificação automática); papel técnico exato DATAPREV vs. Sistema SD: **Evidência indireta** |
| **B_ACEITE** | J5 | Sistema SD / MTE | Sistema/documento | Controle de elegibilidade via termo declaratório/aceite: o cidadão declara que atende os requisitos e não se encontra em situação de suspensão ou cancelamento. No fluxo presencial: assinatura de termo físico. Previsão normativa presente na Res. 957/2022 | Sistema SD; Empregador Web | Declaração do cidadão | Registro do aceite; parte do processo de habilitação | Parcialmente (cidadão confirma; verificação é backstage) | **Res. 957/2022 arts. 6º e seguintes** | **Evidência indireta** (previsão normativa de termo declaratório; implementação digital específica a confirmar por teste) |
| **B_NOTIF_J7** | J7 | Sistema SD / MTE | Sistema | Geração e disponibilização da notificação digital de resultado no ambiente do usuário (gov.br / app CTPS Digital) | Sistema SD | Resultado da análise | Notificação disponível no portal/app | Parcialmente | Res. 957/2022; gov.br | Comprovado (existência e canal digital) |
| **B_NOTIF** | J7a | Sistema SD / MTE | Sistema/documento | Registro do momento de disponibilização da notificação. A Res. 957/2022 permite notificação exclusivamente por meio digital. O prazo de 120 dias para recurso conta da notificação (art. 27). **O marco exato de ciência — acesso efetivo ao portal, mera disponibilização, envio de push/SMS ou outro evento — não está especificado em fonte consultada.** Esse ponto é lacuna normativa específica. | Sistema SD; ambiente gov.br | Notificação gerada | Notificação disponibilizada; início de prazo de recurso | Não | **Res. 957/2022 art. 27** (prazo e notificação digital); marco exato de ciência: **Pendente/lacuna** | Notificação digital: Comprovado; marco de ciência: **Pendente/lacuna** |
| **B_RECURSO_NORM** | J11 | Secretaria de Trabalho / MTE | Humano | Julgamento do recurso em instância única (Res. 957/2022 art. 28); análise limitada aos requisitos normativos passíveis de recurso | Sistema interno MTE (unidade e sistema: **em-aberto**) | Recurso instruído | Deferimento ou indeferimento | Não | **Res. 957/2022 art. 28** | Comprovado (competência normativa); unidade interna e sistema: **Pendente/em-aberto** |
| **B_RECURSO** | J11/J11a | Sistema SD / MTE / Secretaria de Trabalho | Sistema/humano | Análise do mérito do recurso limitada aos requisitos legais. Se o problema estiver em base de origem, o recurso pode ser indeferido, exigindo correção pelo empregador ou por via judicial. **Bases externas relevantes para o mérito: CNIS, eSocial, GFIP, GRF, documentação judicial. CAGED não é base ordinária de habilitação/recurso.** | CNIS; eSocial; GFIP; GRF; documentação judicial | Recurso + documentos | Decisão; eventual exigência de correção externa | Não | Res. 957/2022 arts. 27–28 | Comprovado (normativo); operacionalização: **Inferido** |
| **B_PAGTO_LOTE** | J9 | Caixa (Agente Pagador) + FAT/MTE | Sistema/fundo | Processamento em lote das ordens de pagamento; crédito nas contas indicadas; emissão e arquivamento de autenticação/comprovante de pagamento pelo agente pagador **pelo prazo mínimo de 5 anos (art. 20, §4º, Res. 957/2022)** | Sistemas Caixa; FAT | Ordem de pagamento do MTE | Crédito nas contas; registro de pagamento arquivado | Não | **Res. 957/2022 art. 20, §4º** | **Comprovado** |
| **B_PRAZO_FAT** | J9a | Caixa (Agente Pagador) / FAT | Sistema/fundo | A parcela fica disponível para saque por **67 dias corridos** a contar do crédito (art. 21 da Res. 957/2022). Após esse prazo, o valor é transferido ao FAT. Fica assegurado ao beneficiário o direito ao recebimento da parcela não sacada pelo prazo de **até 2 anos** da data de disponibilização, mediante reemissão | Sistemas Caixa; FAT | Parcela emitida não sacada | Transferência ao FAT; reemissão em até 2 anos mediante solicitação | Não | **Res. 957/2022 art. 21** | **Comprovado** |
| **B_CONTEST** | J10/J9a | Caixa (Agente Pagador) / MTE | Humano/sistema | Tratamento de contestação de recebimento: trabalhador afirma não ter recebido parcela registrada como paga; agente pagador verifica os registros eletrônicos de autenticação de pagamento arquivados pelo prazo mínimo de 5 anos e inicia procedimento administrativo de contestação | Sistemas Caixa; registros de pagamento (art. 20, §4º) | Contestação do cidadão | Comprovação de pagamento ou reconhecimento de falha; procedimento de reemissão/ressarcimento | Parcialmente | **Res. 957/2022 art. 20, §5º** | **Comprovado** |
| **B_AGU** | J11/J11a | AGU / órgão jurídico competente | Humano/documento | Validação de documento judicial para suprir ausência ou divergência de informação nas bases automáticas (vínculo, remuneração, período de trabalho) | Processo judicial; sistema jurídico | Decisão/sentença judicial | Documento validado para habilitação | Não | Res. 957/2022 (doc. judicial como base alternativa) | Inferido (fluxo de exceção) |
| **B_SRT** | J12 | SRT / SINE | Humano | Atendimento presencial; correção de dados; recepção de recurso presencial; orientação; agendamento | SAA/sistemas MTE; bases externas | Documentos do cidadão | Correção; habilitação; protocolo | Sim | gov.br FAQ; Res. 957/2022 art. 6º | Comprovado |
| **B_158_ATEND** | J2/J8/J11 | Atendente humano da Central 158 (MTE) | Humano | Orientação; informação; agendamento; suporte | Sistema de atendimento MTE | Ligação; dados do cidadão | Orientação; protocolo; agendamento | Sim (voz) | gov.br; Agência Gov | Comprovado |
| **B_URA_158** | J2 | URA/sistema de atendimento eletrônico 158 | IA/sistema | Roteamento eletrônico com menu pré-gravado; transbordo a atendente sob demanda | Servidor de URA MTE | Ligação | Menu; informação pré-gravada; transbordo | Sim (voz) | gov.br ("atendimento eletrônico por meio de informações pré-gravadas") | Comprovado |
| **B_CAIXA_TELS** | J10 | CERAT Caixa / contact center Caixa (0800) | Humano/sistema | Atendimento de benefícios sociais/pagamento; triagem por URA; transbordo a atendente | URA Caixa (infraestrutura comprovada); integração com sistemas SD: não comprovada | Ligação | Orientação sobre pagamento/saque; encaminhamento | Sim (voz) | Acórdão TCU 1151/2018; Pregão 013/5688-2024 | URA: Comprovada (infraestrutura); menu/escopo SD: **Pendente/lacuna** |
| **B_CODEFAT** | Geral | CODEFAT / FAT | Governança/fundo | Normatização (Resoluções); aprovação de recursos; financiamento | — | — | Resoluções; repasse de recursos | Não | Lei 7.998/1990; Res. 957/2022 | Comprovado |
| **B_OUVIDORIA** | J13 | Ouvidoria MTE / Ouvidoria Caixa / Fala.BR / CGU | Humano/sistema | Tratamento de manifestações; prazo de resposta de até **30 dias (prorrogável por igual período)**; encaminhamento ao órgão responsável | Fala.BR; sistemas de ouvidoria | Manifestação | Resposta; providência; relatório de gestão | Parcialmente | **Lei 13.460/2017; Decreto 9.492/2018** | Comprovado |
## 5. Tabela de evidências físicas e digitais (v3)

> **Correções v3:** E13 (formatos/limites de anexo do recurso) reclassificado de Pendente para **Comprovado** (FAQ oficial: JPG, PNG ou PDF; 1 MB/arquivo; 10 MB total). E_NEW_1 (registro de pagamento) reclassificado para **Comprovado** (art. 20 §4). E_NEW_2 (data/hora de notificação): marco de ciência permanece como **Pendente/lacuna**. E_NEW_3 (GRU) reclassificado para **Comprovado** (art. 25).

| ID | Etapa | Evidência | Tipo | Quem gera | Quem recebe/consulta | Para que serve | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|
| E1 | J0/J1 | Requerimento do SD (10 dígitos, início "77") | Documento físico/digital | Empregador (via Empregador Web) | Trabalhador/MTE/sistema | Dar entrada na solicitação; número-chave do processo | gov.br FAQ; Empregador Web | Comprovado |
| E2 | J0 | TRCT — Termo de Rescisão do Contrato de Trabalho | Documento físico/digital | Empregador | Trabalhador | Comprovação da rescisão; base para conferência de dados | CLT; Empregador Web | Comprovado |
| E3 | J2 | Áudio/menu URA da Central 158 | Áudio/URA | MTE | Cidadão | Orientação inicial; triagem | gov.br; Agência Gov | Comprovado |
| E4 | J3/J4 | Conta gov.br autenticada | Tela/registro digital | SERPRO/gov.br | Cidadão | Acesso ao serviço; autenticação | gov.br | Comprovado |
| E5 | J5 | Tela de confirmação da solicitação | Tela | Sistema SD / MTE | Cidadão | Confirmação de protocolo; indicação de parcelas e prazos | gov.br FAQ (referência genérica) | **Inferido** — existência plausível; texto literal e exibição imediata de parcelas a confirmar por teste ou print oficial |
| E5a | J5 | Termo declaratório/aceite digital | Registro digital | Sistema SD / MTE | Cidadão / MTE | Controle de elegibilidade; marco formal da solicitação | Res. 957/2022 arts. 6º e seguintes | **Evidência indireta** |
| E_NEW_2 | J7a | Notificação digital com data/hora de disponibilização | Notificação digital | Sistema SD / MTE | Cidadão | Comunicação da decisão; marco da notificação; data a partir da qual o prazo de 120 dias para recurso corre; **marco exato de ciência (disponibilização vs. acesso efetivo) = Pendente/lacuna** | Res. 957/2022 art. 27 | Existência da notificação digital: **Comprovado**; marco exato de ciência: **Pendente/lacuna** |
| E7 | J7 | Notificação de deferimento / indeferimento / exigência / suspensão / cancelamento | Notificação digital | MTE/sistema SD | Cidadão | Comunicar a decisão; instruir próximas ações | Res. 957/2022; gov.br FAQ | Comprovado |
| E8 | J8 | Calendário/quantidade de parcelas | Tela/extrato digital | MTE/DATAPREV | Cidadão | Acompanhamento do benefício | gov.br | Comprovado |
| E9 | J9 | Extrato bancário / extrato Caixa Tem com crédito da parcela | Extrato | Caixa / banco indicado | Cidadão | Comprovação de recebimento | Caixa; Lei 14.075/2020 | Comprovado |
| **E_NEW_1** | J9/J9a | **Registro eletrônico de autenticação de pagamento arquivado pelo agente pagador pelo prazo mínimo de 5 anos** | Registro em sistema | Caixa (Agente Pagador) | MTE / Caixa (auditoria, contestação) | Evidência oficial de que o pagamento foi processado; base para contestação (art. 20, §5º) e auditoria | **Res. 957/2022 art. 20, §4º** | **Comprovado** |
| E10 | J9 | Comprovante de saque (lotérica, autoatendimento, agência) | Comprovante físico/digital | Caixa / Correspondente | Cidadão | Comprovação do saque | Caixa | Comprovado |
| E11 | J9 | Cartão Cidadão / Cartão Social | Comprovante físico | Caixa | Cidadão | Instrumento de saque na rede física | gov.br; Caixa | Comprovado |
| E12 | J9–J10 | Mensagem indicando parcela emitida não creditada | Mensagem/tela | Sistemas (MTE ou Caixa) | Cidadão | Diagnóstico de falha de crédito | Reclame Aqui; gov.br FAQ (referência genérica) | **Evidência indireta/anedótica** — relatos de usuários; texto exato e origem do sistema a confirmar |
| **E_NEW_3** | J9a / restituição | **GRU — Guia de Recolhimento da União (devolução de parcelas recebidas indevidamente)** | Documento | MTE / Receita Federal | Cidadão (pagamento de restituição) | Devolução de valores recebidos sem direito; controle financeiro | **Res. 957/2022 art. 25** | **Comprovado** |
| **E13** | J11 | **Protocolo de recurso + documentos anexados em JPG, PNG ou PDF (máximo 1 MB por arquivo; total máximo 10 MB)** | Tela/documento digital | MTE/sistema SD / cidadão | MTE | Instrução do recurso | **FAQ oficial do SD (gov.br) — confirma formatos e limites**; Res. 957/2022 art. 27 | **Comprovado** |
| E14 | J12 | Termo declaratório presencial | Documento | SRT/SINE | MTE | Controle de elegibilidade presencial; habilitação | Res. 957/2022 art. 6º | Comprovado |
| E15 | J12 | Protocolo de atendimento presencial | Protocolo | SRT/SINE | Cidadão/MTE | Rastreabilidade | gov.br FAQ; inferência | Inferido |
| E16 | J13 | Protocolo Fala.BR | Manifestação/registro | CGU/Fala.BR | Cidadão | Rastreabilidade; controle social | Lei 13.460/2017; Decreto 9.492/2018 | Comprovado |
| **E_NEW_4** | J10 / bastidor telefônico | Gravação de chamada; log de URA; tabulação; TMA; tempo de espera; motivo de contato; transferência; abandono; FCR | Registro em sistema (a obter via LAI) | Operador do contact center / URA | Gestor da central; auditoria; pesquisa | Validação da operação real; KPIs de atendimento | Acórdão TCU 1151/2018 (comprova gravação como componente contratual) | **Pendente/lacuna** — elementos existentes por arquitetura comprovada; acesso restrito; obtível via LAI ou entrevista |
| **E_NEW_5** | J11/J12 (excepcionais) | Procuração; alvará judicial; documentos de representação | Documento | Cartório/Justiça/cidadão | MTE/SRT/cidadão | Representação de trabalhador incapacitado, falecido ou menor | CLT; CC; inferência operacional | Inferido |

---

## 6. Matriz normativa (v3)

> **Correções v3:**
> - **LAI:** prazo corrigido para **20 dias + prorrogação de até 10 dias** (não 20+20).
> - **Lei 13.460 / ouvidoria:** prazo corrigido para **30 dias, prorrogável por igual período** (não 20/40).
> - **Res. 1027/2025:** restrita ao pescador artesanal; movida para subseção de modalidades específicas; **Res. 1035/2026 adicionada**.
> - **Res. 957/2022 art. 20 §4, §5; art. 21; art. 25:** citados explicitamente com conteúdo.
> - **Lei 9.784/1999:** rebaixada de "análoga" para "referência conceitual" — não comprova o marco de ciência digital do SD.

| Normativo/fonte | Órgão | Data | Dispositivo relevante | O que determina | Etapa impactada | Ator impactado | Link/citação | Observação |
|---|---|---|---|---|---|---|---|---|
| **Lei nº 7.998** | Congresso | 11/01/1990 | Criação do SD; FAT; bancos oficiais como pagadores | Institui o programa; define custeio pelo FAT; designa Caixa como agente pagador | Todas | MTE, Caixa, FAT | planalto.gov.br | Lei-base; múltiplas alterações |
| **Resolução CODEFAT nº 957/2022** | CODEFAT/MTE | 21/09/2022 (vigência 03/10/2022) | 69 artigos — concessão, processamento, pagamento, recurso, suspensão, cancelamento | Norma central vigente do trabalhador formal; revoga Res. 467/2005 e outras | Todas | MTE, Caixa, DATAPREV, cidadão | portalfat.mte.gov.br | **Norma regulatória principal — trabalhador formal** |
| **Res. 957/2022 art. 20, §4º** | CODEFAT | 2022 | Comprovação por autenticação ou registro eletrônico arquivado por prazo mínimo de 5 anos | Define dever de comprovação e guarda pelo agente pagador | J9, J9a, E_NEW_1 | Caixa (Agente Pagador) | Res. 957/2022 | **Comprovado** |
| **Res. 957/2022 art. 20, §5º** | CODEFAT | 2022 | Contestação de recebimento de parcela | Procedimento para quando o trabalhador nega ter recebido parcela registrada como paga | J9a, J10, F22, B_CONTEST | Caixa, MTE | Res. 957/2022 | **Comprovado** |
| **Res. 957/2022 art. 21** | CODEFAT | 2022 | Parcela disponível por **67 dias corridos** do crédito; devolução ao FAT após esse prazo; reemissão assegurada em até **2 anos** | Define prazo de saque; devolução ao FAT; direito de reemissão | J9a, F21, B_PRAZO_FAT | Caixa, cidadão | Res. 957/2022 | **Comprovado** |
| **Res. 957/2022 art. 22** | CODEFAT | 2022 | Hipóteses de **suspensão**: (I) admissão em novo emprego; (II) início de benefício previdenciário de prestação continuada, exceto auxílio-acidente e pensão por morte; (III) recusa injustificada de ações de recolocação | Define suspensão automática; **não se confunde com BPC/LOAS (benefício assistencial, Lei 8.742/1993)** | J7, J7a, F26 | MTE, DATAPREV | Res. 957/2022 | Comprovado |
| **Res. 957/2022 art. 23** | CODEFAT | 2022 | Hipóteses de **cancelamento**: recusa de emprego condizente; comprovação de falsidade; fraude; morte do segurado | Define cancelamento definitivo do benefício | J7, J7a, F27 | MTE, cidadão | Res. 957/2022 | Comprovado |
| **Res. 957/2022 art. 25** | CODEFAT | 2022 | Restituição de parcelas recebidas indevidamente por meio de GRU ou compensação | Define obrigação de devolução e instrumento (GRU) | J9a, E_NEW_3 | MTE, cidadão | Res. 957/2022 | **Comprovado** |
| **Res. 957/2022 art. 27** | CODEFAT | 2022 | Recurso administrativo; prazo de 120 dias; notificação pode ser digital | Garante direito de recurso; prazo conta da notificação; notificação digital é admitida | J7a, J11, F16, F17 | MTE, cidadão | Res. 957/2022 | Comprovado — marco exato de ciência digital: **Pendente/lacuna** |
| **Res. 957/2022 art. 28** | CODEFAT | 2022 | Julgamento em instância única — Secretaria de Trabalho | Competência decisória; sem segunda instância administrativa | J11 | MTE | Res. 957/2022 | Comprovado |
| **Res. CODEFAT nº 987/2023** | CODEFAT/MTE | 21/11/2023 | Bolsa qualificação e calamidade | Altera modalidades específicas | J5 | MTE | legisweb | Comprovado |
| **Lei Complementar nº 150/2015** | Congresso | 01/06/2015 | SD para trabalhador doméstico | Fluxo diferenciado; habilitação via 158/presencial | J3, F23 | MTE | planalto.gov.br | Comprovado |
| **Lei nº 10.779/2003** | Congresso | 25/11/2003 | SD para pescador artesanal (seguro-defeso) | Base do seguro-defeso | J5 (modal específico) | MTE/IBAMA | planalto.gov.br | Comprovado |
| **Modalidades específicas — pescador artesanal** | | | | | | | | |
| **Res. CODEFAT/MTE nº 1027/2025** | CODEFAT/MTE | 2025 | **Regras do seguro-desemprego do pescador artesanal** — revoga e substitui dispositivos da Res. 957/2022 aplicáveis ao pescador artesanal | **Norma específica da modalidade pescador artesanal; não é atualização geral do SD do trabalhador formal** | J5 (modal específico — pescador) | MTE, pescador artesanal | portalfat.mte.gov.br | Evidência indireta — conteúdo específico a confirmar no texto integral |
| **Res. CODEFAT/MTE nº 1035/2026** | CODEFAT/MTE | 2026 | Altera a Res. 1027/2025 em prazo de requerimento e recurso do pescador artesanal | Atualização da 1027/2025 | J5 (modal específico) | MTE, pescador artesanal | portalfat.mte.gov.br | Evidência indireta — citada em auditoria; texto a confirmar |
| **Lei nº 13.460/2017** | Congresso | 26/06/2017 | Direitos do usuário; Carta de Serviços; ouvidoria | Garante direitos; define prazos de ouvidoria: **30 dias, prorrogável por igual período (30+30)** | J13 | MTE, Caixa | planalto.gov.br | Comprovado |
| **Decreto nº 9.492/2018** | Presidência | 05/09/2018 | Regulamentação da Lei 13.460/2017; prazos e fluxos de ouvidoria | Prazo de resposta: **30 dias (prorrogável por mais 30 mediante justificativa)** | J13 | MTE, Caixa, CGU | planalto.gov.br | Comprovado |
| **Decreto nº 9.094/2017** | Presidência | 17/07/2017 | Simplificação do atendimento; Carta de Serviços no Executivo Federal | Dispensa de certidões; padrão de atendimento; integração de bases | J2, J3, J12 | MTE, Caixa, SRT/SINE | planalto.gov.br | Comprovado |
| **Lei nº 14.075/2020** | Congresso | 22/10/2020 | Poupança Social Digital | Permite pagamento de benefícios via conta digital; limite R$ 5.000/mês | J9 | Caixa | caixa.gov.br | Comprovado |
| **Lei nº 10.048/2000** | Congresso | 08/11/2000 | Atendimento prioritário a idosos, PcD, gestantes | Prioridade em atendimento presencial | J12 | SRT/SINE, Caixa | gov.br | Comprovado |
| **Lei nº 12.527/2011 (LAI)** | Congresso | 18/11/2011 | Acesso a informações públicas; prazo de **20 dias, prorrogável por mais 10 dias** | Base legal para obtenção de documentos internos: árvore de URA, contratos, SLAs, logs, scripts, manuais, relatórios | Todas (instrumento de pesquisa) | MTE, Caixa, DATAPREV | planalto.gov.br | Comprovado — prazo: **20 + 10 dias (máximo 30)** |
| **Lei nº 13.709/2018 (LGPD)** | Congresso | 14/08/2018 | Proteção de dados; base legal de tratamento; direitos do titular; decisões automatizadas | Regula tratamento de CPF, NIS/PIS, dados trabalhistas, remuneração, dados bancários, gravações; transparência em triagem automatizada (J6) | J4, J6, J10 | MTE, Caixa, DATAPREV, fornecedores | planalto.gov.br | Comprovado |
| **Acórdão TCU 1151/2018-Plenário** | TCU | 23/05/2018 | Contact center Caixa (PE 59/2017; CTIS; TC 023.621/2017-6) | Comprova infraestrutura URA/CERAT da Caixa; determina ajustes no edital | J10 | Caixa | tcu.gov.br | Comprova URA/CERAT genérica; não comprova menu SD |
| **TNU — Tema 356** | TNU | — | Prescrição quinquenal a partir da ciência do ato de indeferimento | Prazo de prescrição para ação judicial | J11, F16 | Cidadão, AGU | TNU | Comprovado |
| **Relatório de Avaliação CGU (BGSD 2022)** | CGU | 2022 | Deferimento de recurso por canal: 67,4% presencial vs. 18,6% digital (431.373 recursos) | Dado quantitativo para F8 | J11, F8 | MTE | eaud.cgu.gov.br | Comprovado — dado mais robusto disponível |
| **Lei nº 9.784/1999** | Congresso | 29/01/1999 | Art. 26, §3º — intimação por via postal presumida após 5 dias úteis | **Referência conceitual apenas** — não comprova o marco de ciência da notificação digital no Seguro-Desemprego; aplicação específica ao SD depende de norma própria | J7a (referência) | — | planalto.gov.br | **Não usado como prova; mencionado apenas como ponto de partida conceitual para pesquisa futura** |
## 7. Matriz de fail points (v3 — F1 a F27)

> **Correções v3:**
> - F4 e F24: reformulados sem pressupor nível mínimo específico de conta gov.br.
> - F17: reescrito — presunção automática de ciência removida; marco exato de ciência = lacuna.
> - F19: reclassificado para **Comprovado** (FAQ oficial: conta salário e conjunta não aceitas).
> - F20: reclassificado para **Comprovado** (FAQ oficial).
> - F21: reclassificado para **Comprovado** (Res. 957/2022 art. 21).
> - F22: reclassificado para **Comprovado** (Res. 957/2022 art. 20, §5º).
> - F26: separado em **F26 (suspensão, art. 22)** e **F27 (cancelamento, art. 23)**; "BPC" substituído por "benefício previdenciário de prestação continuada" para evitar confusão com BPC/LOAS.

| ID | Fail point | Etapa | Tipo | Descrição | Causa provável | Impacto no cidadão | Impacto operacional | Evidência | Nível de evidência | Possível métrica | Fonte |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **F1** | **"Jogo de empurra" Caixa↔MTE** | J10 | Comunicação institucional | Cidadão é enviado de um canal ao outro sem resolução. Cada canal só responde pelo seu escopo (Caixa: pagamento; MTE: habilitação); cidadão com expectativa errada percebe ausência de resolutividade | Fronteira institucional não explicada ao cidadão; confusão entre habilitação (MTE) e pagamento (Caixa) | Frustração; não-resolução; abandono | Retrabalho; reclamações em ouvidoria | Relatos em Reclame Aqui (anedóticos); estrutura institucional comprovada (faz o fail point estruturalmente esperado) | **Evidência indireta — relatos individuais + inferência estrutural** | Taxa de transferência entre canais; % manifestações sobre o tema em Fala.BR | Reclame Aqui; Acórdão TCU; gov.br |
| **F2** | Liga à Caixa esperando resolver habilitação | J2/J10 | Informação | Canal de pagamento (0800) acionado para resolver habilitação, deferimento ou recurso | Confusão de papéis | Frustração; chamada improdutiva | Chamada fora de escopo | Estrutura institucional; relatos | Evidência indireta | % chamadas fora de escopo | Estrutura MTE/Caixa |
| **F3** | Ausência de URA/opção específica documentada para SD na Caixa | J10 | Roteamento | Não há evidência pública de opção nominal "Seguro-Desemprego" na URA da Caixa | Não documentado publicamente | Navegação confusa; tempo perdido | Canal não auditável; blueprint incompleto | Lacuna confirmada | **Pendente/lacuna** | — | TCU; pesquisa v1–v3 |
| **F4** | Dificuldade de criar ou usar conta gov.br — ausência de suporte digital | J3/J4 | Autenticação | Cidadão não consegue criar ou usar a conta gov.br sozinho — por falta de acesso digital, dificuldade de uso, ausência de documentos ou distância de terminal de apoio (Banco do Brasil/Caixa ou posto conveniado). O nível mínimo de conta exigido para este serviço **não está comprovado**; a barreira real pode ser a própria criação da conta, não o nível | Exclusão digital; ausência de suporte presencial próximo; nível mínimo a confirmar | Bloqueio de acesso ao canal digital; desvio para presencial ou 158 | Migração ao presencial; sobrecarga SRT/SINE | gov.br FAQ (cita terminal BB/Caixa e posto conveniado como alternativas); nível mínimo: **Pendente/lacuna** | Comprovado (barreira de acesso digital existe); nível mínimo: **Pendente/lacuna** | % solicitações feitas por canal digital vs. presencial | gov.br FAQ |
| **F5** | Dados inconsistentes CNIS/eSocial/GFIP | J6 | Dados | Vínculo em duplicidade, salário divergente, data de demissão incorreta ou tipo de desligamento errado — bases que fundamentam a habilitação automática — impedem o processamento | Falha de transmissão pelo empregador; erro no eSocial/GFIP; inconsistência entre bases | Indeferimento automático; pendência; exigência de correção | Carga de recursos; fila SRT; análise manual | Res. 957/2022 (prevê que inconsistências bloqueiam habilitação e geram exigência de correção) | **Comprovado** (previsão normativa) | % requerimentos em pendência/exigência por inconsistência | Res. 957/2022; CGU/TCU |
| **F6** | Requerimento não localizado ou com divergência | J5/J12 | Dados | Número do requerimento não encontrado ou dados do requerimento divergem dos registros | Erro de preenchimento pelo empregador; requerimento não transmitido; CPF/data divergentes | Bloqueio da solicitação; presencialização | Fila SRT/SINE | gov.br FAQ (pergunta 19) | Comprovado | % solicitações rejeitadas por requerimento inválido | gov.br FAQ |
| **F7** | Indeferimento sem compreensão clara | J7/J7a | Comunicação institucional | Notificação em linguagem técnica/jurídica; cidadão não entende o motivo e não sabe se pode recorrer | Comunicação institucional técnica | Inação; perda de prazo de recurso | Recursos mal instruídos; sobrecarga do 158 | CGU 2022; inferência | Evidência indireta | Taxa de recursos por indeferimento | CGU; gov.br FAQ |
| **F8** | Recurso online com taxa de deferimento muito inferior ao presencial | J11 | Canal | Em 2022, deferimento digital = 18,6% vs. presencial = 67,4% (431.373 recursos). Cidadão que recorre pelo canal digital tem chance estruturalmente menor de reverter o indeferimento | Ausência de apoio humano no recurso digital; instrução documental inadequada | Perda do benefício; iniquidade de acesso | Ineficiência do canal digital para recursos | **Relatório de Avaliação CGU (BGSD 2022)** | **Comprovado** | % deferimento de recurso por canal | CGU/BGSD 2022 |
| **F9** | Falha de crédito em conta | J9 | Pagamento | Parcela emitida mas não creditada na conta indicada | Dados bancários incorretos; conta encerrada; TED rejeitado | Cidadão fica sem recurso | Atendimento Caixa; reprocessamento | gov.br FAQ; relatos | Comprovado | % falhas de crédito por parcela emitida | Caixa; gov.br FAQ |
| **F10** | Cidadão sem Cartão Cidadão / senha / acesso digital | J9 | Pagamento | Sem Cartão Cidadão, senha, Caixa Tem ou conta bancária para receber | Não bancarização; perda/roubo do cartão | Impossibilidade de saque; ida obrigatória à agência | Atendimento presencial; emissão de novo cartão | gov.br FAQ (pergunta 26); Caixa | Comprovado | % saques na rede física vs. digital | Caixa; gov.br FAQ |
| **F11** | Fila excessiva / abandono de chamada no 158 | J2 | Fila | Demanda supera capacidade; cidadão abandona | Sazonalidade; pico de demanda; dimensionamento (_dado histórico de inauguração 2015: 157 PAs, ~26 mil ligações/dia; não representa dimensionamento atual_) | Não-atendimento; frustração | Sobrecarga; abandono | Relatos; histórico de inauguração (2015); Agência Gov 2025 (volume) | Evidência indireta | Taxa de abandono; TMA; % ligações atendidas | Agência Gov 2025; Reclame Aqui |
| **F12** | Transbordo inadequado / atendente Caixa sem acesso a dados de habilitação | J10 | Transbordo / integração sistêmica | Atendente do 0800 não tem acesso aos sistemas de habilitação do MTE; só pode informar pagamento | Sistemas separados MTE/Caixa | Não-resolução; reencaminhamento | Custo de chamada; FCR baixo | Inferência arquitetura | Inferido | Taxa de resolução no primeiro contato (FCR) | Inferência |
| **F13** | Linguagem difícil / siglas / baixa compreensão | J2/J7 | Comunicação institucional | Termos como CNIS, GRF, GFIP, exigência, suspensão, cancelamento não compreendidos | Comunicação técnica; falta de UX writing | Erro de ação; perda de prazo | Recursos mal instruídos; sobrecarga | CGU; inferência | Inferido | Pesquisa de satisfação; índice de compreensão | CGU |
| **F14** | Acessibilidade para público vulnerável | J2/J9 | Acessibilidade | Idosos, PcD, pessoas sem alfabetização digital têm barreiras nos canais digitais e telefônicos | Barreira digital; canal acessível insuficiente | Exclusão; dependência de terceiros; presencial | Demanda presencial adicional | Lei 10.048/2000; Caixa 0800 726 2492 (PcD) | Inferido | Atendimentos prioritários; % canal digital por faixa etária | Lei 10.048 |
| **F15** | Falta de protocolo / rastreabilidade no atendimento telefônico | J10 | Integração sistêmica | Cidadão não recebe comprovante do atendimento telefônico | Ausência de emissão de protocolo ao usuário | Sem prova; orientações contraditórias | Litígio; reclamações | Lacuna | **Pendente/lacuna** | Existência de protocolo de atendimento ao usuário | Acórdão TCU; lacuna |
| **F16** | Perda de prazo de recurso (120 dias) | J11 | Governança | Cidadão não recorre dentro do prazo de 120 dias | Desinformação; demora em buscar orientação | Perda definitiva do benefício por via administrativa | Litígio; demanda sobre TNU Tema 356 | Res. 957/2022 art. 27; TNU Tema 356 | Comprovado | % recursos intempestivos | Res. 957/2022; TNU |
| **F17** | **Perda de prazo pela forma de notificação digital** | J7a | Governança / decisão automática | A Res. 957/2022 (art. 27) admite notificação exclusivamente digital. O cidadão que não consulta regularmente o portal/app pode não perceber a disponibilização da notificação e perder o prazo de recurso. **O marco exato de ciência — disponibilização, acesso efetivo, push/SMS ou outro evento — não está especificado em fonte consultada**, o que torna essa lacuna normativa ela própria um risco | Canal exclusivamente digital; ausência de notificação proativa eficaz (push/SMS); baixa frequência de acesso ao portal | Perda do prazo de recurso; perda definitiva do benefício | Demanda sobre TNU Tema 356; litígio | **Res. 957/2022 art. 27** (notificação digital admitida; prazo de 120 dias) | Comprovado (notificação digital e prazo); **marco exato de ciência: Pendente/lacuna** | % recursos intempestivos; tempo médio entre disponibilização e protocolo | Res. 957/2022; CGU |
| **F18** | Recurso indeferido por exigir correção em base de origem | J11/J11a | Dados / governança | O mérito do recurso é limitado a critérios normativos. Se o problema estiver em base de origem (empregador não corrigiu eSocial/GFIP; vínculo não reconhecido judicialmente), o recurso é indeferido mesmo com razão substantiva | Erro em base de origem; empregador não retifica; dado judicial ausente | Recurso indeferido; necessidade de ação judicial | Carga de recursos mal instruídos | Res. 957/2022 arts. 27–28; inferência técnica | Inferido | % recursos indeferidos por ausência de correção em base | Res. 957/2022 |
| **F19** | **Conta salário ou conta conjunta rejeitada** | J9 | Pagamento | A FAQ oficial informa que **não são aceitas conta salário nem conta conjunta** para recebimento do SD; titularidade exclusiva do trabalhador é exigida; parcela não é creditada nessas modalidades | Desconhecimento das restrições de tipo de conta | Parcela não creditada; necessidade de indicar nova conta | Atendimento Caixa; reprocessamento | **FAQ oficial do SD (gov.br) — expressa e diretamente** | **Comprovado** | % rejeições de crédito por tipo de conta inválido | **gov.br FAQ** |
| **F20** | **Dados bancários incorretos informados pelo cidadão** | J9 | Pagamento | A FAQ oficial exige registro correto de banco, agência, conta e titularidade; erros impedem o crédito | Erro de digitação; conta encerrada; desconhecimento do número correto | Parcela não recebida; necessidade de correção e reprocessamento | Atendimento Caixa; correção de dados; prazo | **FAQ oficial do SD (gov.br)** | **Comprovado** | % créditos rejeitados por dados bancários incorretos | **gov.br FAQ** |
| **F21** | **Parcela não sacada no prazo de 67 dias + devolução ao FAT** | J9a | Pagamento | A parcela fica disponível por **67 dias corridos** a partir do crédito (Res. 957/2022 art. 21); após esse prazo é devolvida ao FAT. Cidadão só recupera mediante reemissão, em até 2 anos da disponibilização | Desconhecimento do prazo; impossibilidade de saque; doença; falta de acesso | Perda imediata da disponibilidade da parcela; necessidade de reemissão | Reemissão manual; carga operacional | **Res. 957/2022 art. 21** | **Comprovado** | % parcelas devolvidas ao FAT por prazo expirado | **Res. 957/2022** |
| **F22** | **Contestação de recebimento de parcela** | J9a/J10 | Pagamento | Trabalhador afirma não ter recebido parcela registrada como paga; exige verificação dos registros de autenticação arquivados (art. 20, §4º) e abertura de procedimento administrativo (art. 20, §5º) | Erro bancário; fraude; crédito em conta não reconhecida; falha de sistema | Cidadão sem o recurso; procedimento burocrático | Investigação interna Caixa; cruzamento de registros; possível ressarcimento | **Res. 957/2022 art. 20, §5º** | **Comprovado** | Nº de contestações de recebimento por período | **Res. 957/2022** |
| **F23** | Trabalhador doméstico fora do fluxo digital comum | J3/J12 | Canal / acessibilidade | Empregado doméstico depende de agendamento pelo 158 ou atendimento presencial (LC 150/2015); não usa o portal gov.br da mesma forma que o trabalhador formal | LC 150/2015; fluxo operacional diferenciado | Impossibilidade de usar canal digital padrão; custo de deslocamento; fila | Demanda presencial adicional; sobrecarga SRT/SINE | **LC 150/2015; gov.br FAQ** | Comprovado | % domésticos atendidos por canal; TMA de atendimento | LC 150/2015 |
| **F24** | **Falha de acesso ao gov.br — distância de ponto de apoio** | J3/J4 | Autenticação | Cidadão que não consegue criar ou acessar a conta gov.br precisa ir a terminal do Banco do Brasil, da Caixa ou posto conveniado. Em municípios sem essas opções próximas, o acesso digital ao serviço fica inviável. Nível mínimo exigido: **não comprovado** | Ausência de infraestrutura bancária no município; exclusão digital | Bloqueio de acesso digital; deslocamento; custo | Migração ao presencial; sobrecarga SRT/SINE | gov.br FAQ (cita terminais BB/Caixa/posto como alternativa); nível mínimo: **Pendente/lacuna** | Comprovado (barreira geográfica de acesso ao apoio) | % solicitações digitais vs. presenciais por região | gov.br FAQ; IBGE |
| **F25** | Falta de internet — desvio obrigatório para presencial | J3/J5/J11 | Canal / acessibilidade | Cidadão sem internet em casa ou local próximo não consegue usar o canal digital; é forçado ao presencial com custo de deslocamento e fila | Exclusão digital; concentração de infraestrutura | Custo de deslocamento; fila; perda de dia de trabalho | Demanda presencial adicional; custo por cidadão superior | Inferência de exclusão digital; gov.br FAQ | Inferido | % solicitações presenciais vs. digitais por região; domicílios sem internet | IBGE; gov.br |
| **F26** | **Suspensão automática — art. 22 da Res. 957/2022** | J7/J7a | Decisão automática / comunicação | O benefício é suspenso automaticamente quando o sistema detecta: (I) admissão em novo emprego; (II) início de **benefício previdenciário de prestação continuada** (exceto auxílio-acidente e pensão por morte — **não confundir com BPC/LOAS, que é benefício assistencial da Lei 8.742/1993**); (III) recusa injustificada de participar de ações de recolocação. Cidadão pode desconhecer o motivo e buscar o canal errado | Cruzamento automático de bases (eSocial/CAGED/INSS/SINE); comunicação insuficiente do motivo | Perda da parcela; confusão; recurso desnecessário | Recursos infundados; carga da Secretaria de Trabalho | **Res. 957/2022 art. 22** | Comprovado (hipótese normativa); ocorrência real: Evidência indireta | Nº de suspensões por motivo; % suspensões contestadas | Res. 957/2022 |
| **F27** | **Cancelamento definitivo — art. 23 da Res. 957/2022** *(fail point novo — desmembrado de F26)* | J7/J7a | Decisão automática / governança | O benefício é **cancelado definitivamente** quando: (I) o trabalhador recusa emprego condizente; (II) há comprovação de falsidade nas informações prestadas; (III) há comprovação de fraude; (IV) ocorre morte do segurado. O cancelamento é mais grave que a suspensão — não há retomada automática | Fraude; falsidade comprovada; recusa de emprego; morte | Perda definitiva do benefício; ação de ressarcimento por falsidade/fraude | Instauração de processo administrativo; possível ação penal/civil | **Res. 957/2022 art. 23** | Comprovado (hipótese normativa); frequência real: Evidência indireta | Nº de cancelamentos por motivo | Res. 957/2022 |
## 8. Mapa de atores revisado (v3)

### Atores confirmados — com ajustes finais

**MTE (Ministério do Trabalho e Emprego):** responsável pela política, habilitação, concessão e recurso (instância única via Secretaria de Trabalho, Res. 957/2022 art. 28). Canal 158.

**Caixa Econômica Federal:** Agente Pagador (Lei 7.998/1990). Canal 0800 726 0207. Rede de pagamento (agências, lotéricas, CAIXA Aqui, Caixa Tem, Cartão Cidadão). **Não habilita.** Possui contact center com URA (Acórdão TCU 1151/2018). Outros canais: SAC 0800 726 0101; Ouvidoria 0800 725 7474; PcD 0800 726 2492; WhatsApp 0800 104 0104.

**DATAPREV:** processador técnico da triagem automatizada; mantém e processa CNIS. **Competência decisória de habilitação é do MTE.** Papel técnico exato vs. Sistema SD: evidência indireta.

**Sistema SD (MTE):** sistema de processamento e concessão do SD; responsável pela decisão automática de habilitação. Competência do MTE.

**Secretaria de Trabalho (MTE):** unidade competente para julgamento de recursos administrativos (instância única, Res. 957/2022 art. 28). Unidade operacional interna e sistema usado: **em-aberto**.

**CODEFAT/FAT:** governança normativa (Resoluções) e financiamento. Backstage.

**SINE/SRT:** atendimento presencial; correção de divergências; recurso presencial; fallback. Frontstage presencial.

**Ouvidoria/CGU/Fala.BR:** manifestações e controle social. Prazos: 30 + 30 dias (Lei 13.460/2017; Decreto 9.492/2018).

**Empregador / Empregador Web:** gera e transmite o Requerimento do SD com certificado ICP-Brasil. Causa-raiz de F5, F6 e F18. CAGED não é base de habilitação pela Res. 957/2022.

**AGU / órgão jurídico competente:** validação de documento judicial em fluxos excepcionais (J11a). Backstage de exceção.

**SERPRO / infraestrutura gov.br:** autenticação digital. Backstage tecnológico.

**Banco do Brasil:** terminal de apoio para criação de conta gov.br (gov.br FAQ). Ator periférico relevante para F4 e F24.

### Atores reclassificados

**CTIS Tecnologia S.A.:** confirmada apenas no Contrato 8629/2017 (PE 59/2017-Gilog/BR). Operador atual do contact center da Caixa: **em-aberto** (Pregão 013/5688-2024 sem homologação localizada).

**"URA da Caixa para Seguro-Desemprego":** removida como entidade específica confirmada. Hipótese/lacuna. Infraestrutura de URA existe (TCU 1151/2018); opção nominal, menu e integração com SD: não comprovados.

---

## 9. Lacunas de evidência (v3)

| # | Lacuna | Por que é crítica | Como obter |
|---|---|---|---|
| L1 | Menu/árvore da URA da Caixa (0800) | Raia telefônica da Caixa é lacunar sem ela | Mystery caller; LAI; TR do Pregão 013/5688-2024 |
| L2 | Opção nominal "seguro-desemprego" no menu da Caixa | Define roteamento específico vs. genérico | Mystery caller; LAI |
| L3 | Uso de ASR/NLP/voicebot na Caixa ou no 158 | IA no frontstage — fail points de reconhecimento/intenção | LAI; edital; entrevista |
| L4 | Integração técnica entre 0800 Caixa e sistemas SD (MTE/DATAPREV) | Escopo resolutivo do canal da Caixa | Entrevista; LAI; análise de TR |
| L5 | Nível mínimo de conta gov.br para o serviço SD | F4 e F24 — barreira real de autenticação | Teste de tela; FAQ oficial; Carta de Serviços |
| L6 | Texto literal das telas de confirmação (J5) e de recurso (J11) | Evidências físicas do frontstage digital | Teste de tela; print oficial; manual |
| L7 | Marco exato de ciência da notificação digital (disponibilização, acesso efetivo, push/SMS) | F17 — perda de prazo — o ponto mais grave ainda aberto | Norma específica; instrução normativa MTE; teste; LAI |
| L8 | Dados de fila, TMA, abandono e transbordo dos dois canais — atuais | KPIs essenciais para o blueprint | LAI ao MTE e à Caixa; relatório de gestão de contratos |
| L9 | Empresa atualmente operadora do contact center da Caixa | Ator de backstage tecnológico | LAI; COMPRASNET; DOU |
| L10 | ~~Prazo de disponibilidade da parcela~~ | **RESOLVIDA** — Comprovado (Res. 957/2022 art. 21: 67 dias corridos) | — |
| L11 | ~~Período de retenção de registros~~ | **RESOLVIDA** — Comprovado (Res. 957/2022 art. 20, §4º: mínimo 5 anos) | — |
| L12 | Marco exato de ciência da notificação digital no SD | F17 — lacuna normativa que é ela própria um risco | Norma específica; instrução operacional MTE; LAI; teste |
| L13 | Scripts/manuais de atendimento nos dois canais | Padronização do frontstage; falhas de orientação | LAI; entrevistas |
| L14 | Gravações; logs de URA; tabulações; motivos de contato; FCR | Validação do blueprint telefônico | LAI; análise de contrato; acesso negociado |
| L15 | Unidade interna de recurso (CGSAP?) e sistema operacional (BGSD?) | Ator e sistema de backstage do recurso | LAI; entrevista com gestores MTE |

---

## 10. Recomendações para a próxima etapa de pesquisa (v3)

_(Sem proposta de solução. Foco exclusivo na validação do AS-IS.)_

**1. Mystery caller estruturado (prioridade máxima)** — Ligar para 158 e 0800 726 0207 com roteiros cobrindo: consulta de habilitação; consulta de parcela; falha de crédito; intenção de recurso; contestação de recebimento. Registrar: menu, tempo de espera, transbordo, protocolo, resolução. Resolve L1, L2, L3 parcialmente.

**2. Pedidos LAI (Lei 12.527/2011 — prazo: 20 + 10 dias) via Fala.BR** — Ao MTE: árvore do 158; SLAs; instrução de notificação digital (L12); unidade de recurso (L15). À Caixa: TR/edital Pregão 013/5688-2024; menu 0800; script SD; TMA/FCR. À DATAPREV: papel técnico no processamento de habilitação.

**3. Teste de tela no portal gov.br** — Documentar nível de conta exigido (L5); telas J5, J7a e J11 com capturas datadas.

**4. Leitura integral da Res. 957/2022** — Confirmar marco de ciência digital (L12); conta salário/conjunta; base para F4/F24.

**5. Análise de manifestações do Fala.BR** — Quantificar F1 e F8 em dados administrativos reais. Atualizar o dado de 18,6% vs. 67,4% (CGU 2022) para série histórica corrente.

**6. Entrevistas** — Gestores CGSAP/MTE (fluxo de recurso, sistema); atendentes 158 (fail points, transbordo); SRT/SINE (presencialização involuntária).

**7. Atualização normativa** — Texto integral das Res. CODEFAT 1027/2025 e 1035/2026; resoluções para trabalhador formal posteriores à 957/2022.

**8. Carta de Serviços do MTE e da Caixa** — Documentos obrigatórios (Lei 13.460/2017; Decreto 9.094/2017) com SLAs, canais, prazos e etapas padronizadas.

---

## 11. Checklist para construção posterior do Service Blueprint AS-IS

| Camada do blueprint | Permite preencher? | Observação |
|---|---|---|
| Ações do cidadão (frontstage) | **Sim (alto)** | J0–J13 com subetapas de pagamento comprovadas (arts. 20–21 Res. 957/2022) |
| Evidências físicas — canal digital | **Sim (alto)** | Requerimento, notificação, extrato, GRU, registro de pagamento, formatos de anexo: comprovados; telas de confirmação e recurso: inferidas |
| Evidências físicas — canal telefônico Caixa | **Não (baixo)** | Menu, protocolo, log: lacuna — mystery caller e LAI necessários |
| Frontstage — canal 158 | **Sim (médio-alto)** | Menu eletrônico + transbordo documentados; TMA/abandono/scripts: lacuna |
| Frontstage — canal 0800 Caixa | **Parcial** | Canal confirmado para pagamento; opção específica SD e escopo resolutivo: lacuna |
| Backstage — MTE/DATAPREV | **Sim (médio-alto)** | Bases corretas (CNIS, GRF, GFIP, eSocial), recurso, notificação, contestação: comprovados; sistema operacional de recurso: em-aberto |
| Backstage — Caixa (pagamento) | **Sim (alto)** | Lote, saque, arquivamento 5 anos, prazo 67 dias, devolução FAT, reemissão 2 anos, contestação: todos **comprovados** (arts. 20–21 Res. 957/2022) |
| Backstage — contact center Caixa | **Não (baixo)** | Infraestrutura URA comprovada; operação específica SD: lacuna |
| Sistemas de suporte | **Sim (médio)** | CNIS/eSocial/GFIP/GRF/Sistema SD/Caixa Tem: confirmados; integração telefônica: lacuna |
| Regras/normativos | **Sim (alto)** | Matriz com artigos específicos da Res. 957/2022; lacuna residual no marco de ciência digital |
| Fail points | **Sim (alto)** | 27 fail points; F19, F20, F21, F22 agora Comprovados; F26 e F27 separados por art. 22 e art. 23 |
| Métricas operacionais | **Não (baixo)** | Único dado robusto: % deferimento por canal (CGU 2022); fila/TMA/abandono: lacuna |
| Lacunas mapeadas | **Sim (completo)** | 13 lacunas ativas (L10 e L11 resolvidas); método de obtenção indicado |

---

## Nota metodológica final — escalas de evidência (v3)

| Nível | Definição | Exemplos neste relatório |
|---|---|---|
| **Comprovado** | Fonte oficial pública afirma diretamente o fato (lei, resolução, artigo específico, FAQ oficial, página oficial, acórdão, relatório público) | Res. 957/2022 arts. 20–21 e 25; FAQ oficial (formatos de anexo, conta salário); Lei 7.998; CGU 2022; TCU 1151/2018 |
| **Evidência indireta** | Fonte oficial tangencia ou sugere o fato; estrutura normativa que implica o fato sem comprová-lo operacionalmente; relato anedótico consistente | Jogo de empurra (Reclame Aqui + estrutura institucional); papel técnico DATAPREV vs. Sistema SD; termo de aceite digital |
| **Inferido** | Plausível por arquitetura de call center, URA, atendimento público ou operação de benefícios; sem fonte pública direta | Protocolo de atendimento telefônico Caixa; log de URA; integração de backstage; fluxo de exceção com AGU |
| **Pendente/lacuna** | Elemento central não localizado em fonte pública confiável; exige pesquisa de campo, LAI ou acesso interno | Menu da URA Caixa; nível gov.br exigido; marco de ciência digital da notificação; TMA/abandono; operador atual Caixa |
| **Em-aberto** | Ponto válido sem fonte suficiente para fechar; registrado explicitamente | CGSAP como unidade de recurso; BGSD como sistema operacional; operador do contact center Caixa |
