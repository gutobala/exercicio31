# Service Blueprint AS-IS — Jornada do Seguro-Desemprego (trabalhador formal)
## Canais digital (gov.br), telefônico (158 / 0800 Caixa) e presencial (SRT/SINE)

> **Metodologia:** Service Blueprint de Shostack — 5 camadas (Evidências Físicas, Ações do Cidadão, Frontstage, Backstage, Processos de Suporte), 3 linhas divisórias e fail points.
> **Insumo:** `B_relatorio_assistente_v3.md` (v3, pós-auditoria).
> **Nota de escopo:** o título original do exercício ("Atendimento pela URA da Caixa") foi ajustado. O insumo prova (§1) que **não existe URA da Caixa específica para Seguro-Desemprego confirmada** em fonte pública: o atendimento ao SD é protagonizado pela Central 158/MTE e pelo canal digital gov.br; a Caixa (0800) é **agente pagador**. A URA da Caixa aparece aqui como **uma raia telefônica com lacuna marcada**, não como o objeto único.

---

## Legenda

**Camada epistêmica (nível de evidência) — aplicada a todas as células:**
- **●** Comprovado (fonte oficial direta) — *linha sólida*
- **◐** Evidência indireta / Inferido — *linha tracejada*
- **○** Pendente-lacuna / Em-aberto — *“fantasma”*

**Dono institucional:** `[MTE]` `[CAIXA]` `[DATAPREV]` `[SERPRO/gov.br]` `[EMPREG]` (empregador) `[FAT]` (fundo/CODEFAT) `[SRT/SINE]` (presencial) `[RFB]` (Receita) `[AGU]`

**As 3 linhas divisórias** (neste layout transposto, são *fronteiras entre colunas*):
- **┃LI┃ Linha de interação** → entre **Ação do Cidadão** e **Frontstage**
- **┃LV┃ Linha de visibilidade** → entre **Frontstage** e **Backstage**
- **┃LII┃ Linha de interação interna** → entre **Backstage** e **Processos de Suporte**

**Emenda institucional MTE↔Caixa:** ocorre entre J7 (mundo MTE — habilitação/decisão) e J9 (mundo Caixa — pagamento). É a costura onde nasce **F1 (jogo de empurra)**.

---

## Blueprint — etapas (linhas) × camadas (colunas)

| Etapa (cidadão) | Evidências Físicas | Ação do Cidadão ┃LI┃ | Frontstage ┃LV┃ | Backstage ┃LII┃ | Processos de Suporte | Fail points (ancorados) | ⏱ Prazo |
|---|---|---|---|---|---|---|---|
| **J2 · Buscar informação** | ● Áudio/menu URA 158 `[MTE]`<br>● Tela FAQ gov.br | ● Liga 158 ou acessa portal/app CTPS Digital para saber direito, prazos e como solicitar | ● URA 158: menu pré-gravado + transbordo `[MTE]`<br>● Atendente humano 158 `[MTE]`<br>○ URA 0800 Caixa: menu/opção “SD” **não comprovados** `[CAIXA]` | ● Sistema de atendimento MTE (orientação, agendamento) `[MTE]` | ● Carta de Serviços / FAQ gov.br<br>◐ Scripts/manuais de atendimento *(lacuna L13)* | **F2** ◐ liga à Caixa p/ habilitação · **F11** ◐ fila/abandono 158 · **F13** ◐ linguagem/siglas · **F14** ◐ acessibilidade · **F3** ○ sem opção SD na URA Caixa · **F15** ○ sem protocolo telefônico | — |
| **J3–J5 · Solicitar** (autenticar + informar requerimento + aceite) | ● Conta gov.br autenticada / token `[SERPRO]`<br>● Nº do requerimento “77…”<br>◐ Tela de confirmação *(texto literal — lacuna L6)*<br>◐ Termo de aceite digital | ● Faz login gov.br; informa nº do requerimento e dados; lê e **confirma** o termo declaratório; conclui o envio<br>*(doméstico → agenda pelo 158 — ramo F23)* | ● Telas self-service gov.br / app CTPS Digital `[SERPRO/MTE]` *(autosserviço — sem atendente)*<br>◐ Confirmação do aceite *(parte percebida)* | ● Validação dos dados do requerimento `[MTE/Sistema SD]`<br>◐ Registro/verificação do termo de aceite *(parte oculta)* `[MTE]` | ● Requerimento originado no **Empregador Web** em J0 `[EMPREG]`<br>● Infra de autenticação SERPRO/gov.br<br>○ Nível mínimo de conta gov.br exigido *(lacuna L5)* | **F4** ● dificuldade de criar/usar gov.br *(nível ○)* · **F24** ● distância de ponto de apoio · **F25** ◐ falta de internet · **F6** ● requerimento não localizado/divergência · **F23** ● doméstico fora do fluxo digital | — |
| **J6 · Aguardar habilitação** *(espera assíncrona)* | ○ Nada imediatamente visível | ● **Nenhuma ação** — aguarda o processamento automático | — *(sem contato)* | ● Triagem automatizada: **Sistema SD** decide com base em **CNIS, GRF, GFIP, eSocial, doc. judicial**; resultado = deferido / indeferido / pendência / exigência. *(CAGED não integra o rol)* `[MTE/DATAPREV]` | ● Bases CNIS/eSocial/GFIP/GRF `[DATAPREV]`<br>◐ Documento judicial via AGU/Justiça *(exceção)* `[AGU]` | **F5** ● dados inconsistentes CNIS/eSocial/GFIP | ◐ prazo de resposta = **lacuna** (quebra na espinha) |
| **J7 / J7a · Receber a decisão e tomar ciência** | ● Notificação digital: deferimento / indeferimento / pendência / suspensão / cancelamento `[MTE]`<br>○ Data-hora — **marco de ciência** *(E_NEW_2 — lacuna L7/L12)* | ● Acessa o serviço/app ou liga ao 158; **toma ciência** da decisão (5 desfechos possíveis) | ● Notificação disponibilizada no portal/app — cidadão **recebe** *(parte percebida)* `[MTE]` | ● Geração e disponibilização da notificação `[Sistema SD/MTE]`<br>● Registro do momento de disponibilização *(parte oculta)*<br>○ Marco exato de ciência (disponibilização vs. acesso vs. push/SMS) | ● Res. 957/2022 art. 27 (prazo 120d; notificação digital) · arts. 22/23 (suspensão/cancelamento) `[MTE]` | **F7** ◐ indeferimento sem compreensão · **F17** ● perda de prazo pela notificação digital *(marco ○)* · **F26** ● suspensão automática (art. 22) · **F27** ● cancelamento (art. 23) | ⏱ **120 dias** p/ recurso a contar da notificação |
| **J9 · Receber o pagamento** ⟵ *emenda MTE↔Caixa* | ● Extrato bancário / Caixa Tem com o crédito `[CAIXA]`<br>◐ Mensagem de “parcela não creditada” *(E12)* | ● Verifica o crédito na conta indicada / Poupança Social Digital / Caixa Tem | ● Atendente 0800 Caixa (em caso de falha de crédito) `[CAIXA]` *(o crédito em si é automático, sem contato)* | ● Processamento em **lote** das ordens de pagamento; crédito; emissão e arquivamento do comprovante **≥ 5 anos** (art. 20 §4) `[CAIXA]` | ● **FAT** (fundo) `[FAT]`<br>● Sistemas Caixa<br>● Registro eletrônico de pagamento arquivado 5 anos *(artefato de bastidor — não é evidência física)* | **F9** ● falha de crédito · **F19** ● conta salário/conjunta rejeitada · **F20** ● dados bancários incorretos · **F1** ◐ jogo de empurra Caixa↔MTE · **F12** ◐ atendente Caixa sem acesso à habilitação | — |
| **J9a · Sacar / fallback** | ● Comprovante de saque `[CAIXA]`<br>● Cartão Cidadão / Social<br>● GRU de restituição *(E_NEW_3)* `[RFB]` | ● Saca com Cartão Cidadão/senha na rede física (lotérica, autoatendimento, agência); **ou** descobre que a parcela foi devolvida ao FAT | ● Rede física Caixa: agência / lotérica / correspondente `[CAIXA]`<br>● Atendente 0800 `[CAIXA]` | ● Parcela disponível **67 dias corridos**; após, devolução ao **FAT**; reemissão em até **2 anos** (art. 21)<br>● Tratamento de contestação de recebimento (art. 20 §5) `[CAIXA/FAT]` | ● FAT · Sistemas Caixa · Receita Federal (GRU art. 25) `[RFB]` | **F10** ● sem cartão/senha/acesso digital · **F21** ● não saca em 67d → devolução ao FAT · **F22** ● contestação de recebimento | ⏱ **67 dias** corridos · reemissão até **2 anos** · arquivamento **5 anos** |
| **J11 · Recorrer** *(ramo de exceção — indeferimento/suspensão/cancelamento)* | ● Tela de recurso<br>● Protocolo de recurso<br>● Anexos JPG/PNG/PDF (≤ 1 MB/arquivo; 10 MB total) *(E13)* | ● Acessa a tela de recurso, preenche o motivo e anexa documentos; **ou** agenda presencial pelo 158; **ou** comparece à SRT | ● Telas gov.br / app `[MTE]`<br>● Atendente 158 (agendamento) `[MTE]`<br>● SRT/SINE presencial `[SRT/SINE]` | ● Julgamento em **instância única** — Secretaria de Trabalho `[MTE]`<br>● Análise de mérito limitada a requisitos legais<br>○ Unidade interna (CGSAP?) e sistema (BGSD?) — **em-aberto** *(L15)* | ● Bases CNIS/eSocial/GFIP/GRF<br>● Empregador retifica eSocial/GFIP (J11a) `[EMPREG]`<br>◐ AGU/Justiça — doc. judicial `[AGU]` | **F8** ● recurso digital 18,6% vs. presencial 67,4% · **F16** ● perda do prazo de 120d · **F18** ◐ indeferido por exigir correção em base de origem | ⏱ **120 dias** · instância única (sem 2ª instância adм.) |

---

## As 3 linhas divisórias — leitura

| Linha | Posição | O que separa | Tensão neste caso |
|---|---|---|---|
| **Interação (LI)** | Ação do Cidadão ┃ Frontstage | O que o cidadão faz × o que o prestador expõe no contato | Em J3–J5 o frontstage é **autosserviço digital** (telas gov.br), sem atendente humano — a “linha” encosta numa interface, não numa pessoa. |
| **Visibilidade (LV)** | Frontstage ┃ Backstage | O que o cidadão vê × o que é oculto | Itens **desmembrados**: aceite (confirma↑ / verifica↓), notificação (recebe↑ / gera↓), contestação (reclama↑ / apura↓). |
| **Interação interna (LII)** | Backstage ┃ Suporte | Processamento DESTE caso × infraestrutura permanente | DATAPREV processa o caso (backstage), mas as **bases CNIS/eSocial/GFIP/GRF** são suporte; Empregador Web é suporte que alimentou J0. |

---

## Fail points — síntese (27, ancorados na linha onde a falha se manifesta)

| Camada onde se manifesta | Fail points |
|---|---|
| **Ação/Frontstage — acesso e autenticação** | F4 ●, F24 ●, F25 ◐ (J3–J5); F23 ● (doméstico) |
| **Frontstage — canal telefônico** | F2 ◐, F11 ◐ (158); F3 ○, F15 ○ (URA Caixa — lacuna) |
| **Frontstage — emenda institucional** | **F1 ◐**, F12 ◐ (J9/J10 — Caixa↔MTE) |
| **Backstage — dados e decisão** | F5 ● (J6); F18 ◐ (J11/J11a) |
| **Linha de visibilidade — comunicação da decisão** | F7 ◐, F26 ●, F27 ● (J7); F13 ◐ (transversal) |
| **Backstage/Suporte — pagamento** | F9 ●, F19 ●, F20 ● (J9); F10 ●, F21 ●, F22 ● (J9a) |
| **Governança / prazo (temporais)** | F16 ● (120d), **F17 ●** (notificação digital — marco ○), F8 ● (canal de recurso) |
| **Acessibilidade transversal** | F14 ◐ |

> Os fail points **temporais** (F16, F17, F21) estão ligados aos prazos anotados na coluna ⏱ — perder o prazo *é* a falha.

---

## Ramos e pré-condições (fora da espinha principal)

- **J0 · Pré-jornada (empregador):** registra a dispensa e gera o Requerimento do SD via Empregador Web (ICP-Brasil); o TRCT é evidência documental da rescisão. **Processo de suporte** que antecede a jornada do cidadão — causa-raiz de **F5, F6, F18**.
- **J12 · Presencial (SRT/SINE):** ramo de J3/J11 — correção de divergência, recurso presencial, termo declaratório físico. Frontstage presencial `[SRT/SINE]`.
- **J13 · Ouvidoria (Fala.BR):** ramo transversal — manifestação; resposta em **30 + 30 dias** (Lei 13.460/2017; Decreto 9.492/2018) `[MTE/CAIXA/CGU]`.
- **Doméstico (LC 150/2015):** ramo de J3 — habilitação via agendamento 158/presencial (F23).
- **Pescador artesanal (Res. 1027/2025 e 1035/2026):** **fora de escopo** (modalidade distinta — seguro-defeso).

---

## Onde o AS-IS é “fantasma” (○) — lacunas que o blueprint torna visíveis

Toda a **raia telefônica da Caixa** (menu, opção SD, integração com sistemas MTE/DATAPREV — F3, L1, L2, L4), o **nível mínimo de conta gov.br** (L5), o **texto literal das telas** J5/J11 (L6), o **marco exato de ciência da notificação digital** (L7/L12 — sustenta F17), a **unidade/sistema interno de recurso** (L15) e os **KPIs telefônicos** (TMA/abandono/FCR — L8/L14). Estes são os pontos a resolver por *mystery caller*, LAI e teste de tela antes de um blueprint validado.
