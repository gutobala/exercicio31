# Auditoria — Assistente 2 · audit_v2 (sobre a v2)

- **Ferramenta:** ChatGPT 5.5 — mesmo modelo do audit_v1, conversa continuada
- **Data:** 2026-06-13
- **Link da conversa:** https://chatgpt.com/s/t_6a2d5328a2088191b2481e82c9821f1b

# Relatório de Auditoria v2 — Segunda auditoria da pesquisa revisada

## 1. Veredito geral

A v2 melhorou bastante em relação à audit_v1, mas **não pode ser considerada saneada**. Ela endereça a maior parte das falhas no nível declaratório — há uma tabela de “tratamento da auditoria” afirmando correção de cada ponto —, porém em vários casos a correção foi **parcial**, **inconsistente** ou gerou **novas falhas factuais**.

As falhas mais sérias da v2 são:

1. Ela diz que removeu CAGED da habilitação, mas o reinseriu em bastidor/recurso.
2. Ela criou uma tese forte demais sobre “presunção de ciência digital” que não está comprovada na Resolução CODEFAT nº 957/2022.
3. Ela manteve como “pendente” pontos que a própria Resolução 957/2022 comprova claramente, como 67 dias, registro de pagamento por 5 anos, contestação de recebimento e GRU.
4. Ela errou prazos normativos de LAI/ouvidoria.
5. Ela tratou a Resolução CODEFAT/MTE nº 1027/2025 como atualização genérica do Seguro-Desemprego, quando ela é específica do pescador artesanal.

---

## 2. As falhas da audit_v1 foram endereçadas?

### 2.1 CAGED / “base Caixa” na habilitação

**Status:** parcialmente endereçado, com reincidência.

A v2 afirma que:

> “CAGED e ‘base Caixa’ foram removidos como elementos do fluxo ordinário de habilitação.”

**Problema:** em seguida, ela reintroduz CAGED na tabela de bastidor:

> “Empregador Web (MTE); eSocial; CAGED (para informação de vínculo)”

e também em B_RECURSO:

> “Bases externas: eSocial; CAGED; GFIP; documentação judicial”

Isso ainda é problemático. A Resolução CODEFAT nº 957/2022 lista, para aferição automática da habilitação:

- CNIS;
- Guia de Recolhimento do FGTS;
- GFIP;
- eSocial;
- documento judicial.

Ela não lista CAGED como meio ordinário de habilitação.

**Conclusão:** a falha foi corrigida no resumo, mas não foi totalmente corrigida no corpo do relatório.

---

### 2.2 “Resultado imediato” da verificação automática

**Status:** endereçado.

A v2 substituiu “resultado imediato” por “resultado disponibilizado após processamento” em J6. Isso atende à crítica da audit_v1.

**Conclusão:** corrigido.

---

### 2.3 Bronze/Prata/Ouro como requisito gov.br

**Status:** parcialmente endereçado.

A v2 rebaixou o nível gov.br para “pendente/lacuna”, o que está correto. Porém, ainda constrói F4 e F24 em torno de “nível insuficiente” e “precisa subir nível da conta” como se isso fosse uma barreira comprovada do Seguro-Desemprego.

A FAQ oficial fala em criar conta gov.br e, se o cidadão não consegue gerar cadastro, recorrer a terminais do Banco do Brasil/Caixa ou posto conveniado. Ela não comprova exigência de nível Bronze/Prata/Ouro específico para o serviço.

**Conclusão:** a v2 acertou ao marcar o nível mínimo como lacuna, mas errou ao manter fail points baseados em “nível insuficiente” como barreira operacional quase comprovada.

---

### 2.4 Tela “solicitação realizada com sucesso” e parcelas

**Status:** endereçado.

A v2 rebaixou a tela de confirmação para **inferido** e preservou a necessidade de teste/print oficial.

**Conclusão:** corrigido.

---

### 2.5 Anexos JPG/PNG/PDF ≤1MB

**Status:** a v2 foi conservadora demais.

Na audit_v1, o problema era que o relatório não demonstrava a fonte. A v2 rebaixou para “pendente/lacuna”. Porém, a FAQ oficial confirma que o recurso aceita arquivos **JPG, PNG ou PDF**, com tamanho máximo de **1 MB por arquivo** e limite total de **10 MB**.

**Conclusão:** a v2 não introduziu erro grave, mas deixou aberto um ponto que poderia ser fechado como **comprovado**.

---

### 2.6 CGSAP/BGSD como unidade/sistema do recurso

**Status:** endereçado.

A v2 separou o que é normativo — Secretaria de Trabalho julga em instância única — do que é operacional e permanece em aberto — CGSAP/BGSD.

**Conclusão:** corrigido.

---

### 2.7 CTIS e sucessores

**Status:** endereçado.

A v2 restringiu CTIS ao contrato específico 2017/2018 e manteve operador atual como lacuna.

**Conclusão:** corrigido.

---

### 2.8 Reclame Aqui / “parcela emitida” / jogo de empurra

**Status:** majoritariamente endereçado.

A v2 rebaixou Reclame Aqui para evidência indireta/anedótica.

**Risco residual:** o relatório ainda usa a expressão “fenômeno estruturalmente esperado” para o jogo de empurra. Isso é aceitável como hipótese operacional, desde que não vire evidência empírica.

**Conclusão:** corrigido, com pequeno risco de superinterpretação.

---

## 3. Falhas novas introduzidas pela v2

### 3.1 Presunção de ciência digital foi superafirmada

**Trecho problemático da v2:**

> “o cidadão é considerado notificado a partir da data de disponibilização, independentemente de acesso efetivo”

e:

> “prazo de recurso (120 dias) começa a correr a partir desse marco”

**Falha:** a Resolução CODEFAT nº 957/2022 diz que notificações podem ser realizadas exclusivamente por meio digital, mediante anuência e cadastro no gov.br/app CTPS Digital, e que o recurso pode ser interposto em 120 dias contados da notificação. Ela não estabelece, no trecho aplicável, a regra específica de “ciência automática por mera disponibilização, independentemente de acesso”.

A v2 usa a Lei nº 9.784/1999 por analogia, mas isso não fecha a lacuna. A Lei 9.784 trata de intimação no processo administrativo e não comprova, sozinha, a regra operacional específica do Seguro-Desemprego em ambiente digital.

**Correção necessária:**

> O prazo de recurso é de 120 dias contados da notificação. A forma exata de ciência no ambiente digital — acesso efetivo, disponibilização, envio de e-mail/push/SMS ou outro marco — precisa ser confirmada em norma específica, manual do sistema ou teste.

---

### 3.2 Prazos de LAI e ouvidoria estão errados

**Trechos problemáticos da v2:**

> “Lei nº 12.527/2011 (LAI) — prazo de 20 dias (prorrogável a 40)”

e:

> “resposta em até 20 dias (prorrogável a 40)”

**Falha:** a LAI tem prazo de **20 dias**, prorrogável por **mais 10 dias**, não “20 prorrogável a 40”.

Para manifestações de ouvidoria pela Lei nº 13.460/2017, o prazo é de **30 dias**, prorrogável de forma justificada por igual período, não 20/40.

**Correção necessária:**

- LAI: **20 + 10 dias**.
- Ouvidoria/Lei 13.460: **30 + 30 dias**.

---

### 3.3 Resolução CODEFAT/MTE nº 1027/2025 foi tratada de forma genérica demais

**Trecho problemático da v2:**

> “Resolução CODEFAT/MTE nº 1027/2025 — Atualiza regras do SD após 2022; conteúdo específico a confirmar”

**Falha:** a Resolução 1027/2025 dispõe sobre o **Seguro-Desemprego do pescador artesanal**, não sobre o fluxo geral do trabalhador formal. Ela revoga dispositivos específicos da Resolução 957/2022 relacionados ao pescador artesanal.

Além disso, já há a Resolução CODEFAT/MTE nº 1035/2026, que altera a 1027/2025 em prazo de requerimento e recurso do pescador artesanal.

**Correção necessária:** mover a 1027/2025 para uma subseção “modalidades específicas — pescador artesanal/seguro-defeso” e não apresentá-la como atualização genérica do Seguro-Desemprego do trabalhador formal.

---

### 3.4 A v2 deixou como “a confirmar” pontos que a Resolução 957 comprova

A v2 declara como “evidência indireta” ou “prazo a confirmar” estes pontos:

- prazo de 67 dias de disponibilidade da parcela;
- devolução ao FAT;
- reemissão;
- registro de pagamento arquivado por 5 anos;
- contestação de recebimento;
- GRU para restituição.

**Falha:** esses pontos estão expressamente previstos na Resolução CODEFAT nº 957/2022:

- art. 20, §4º: comprovação por autenticação ou registro eletrônico arquivado por 5 anos;
- art. 20, §5º: contestação de recebimento;
- art. 21: parcela disponível por 67 dias, devolução ao FAT e reemissão em até 2 anos;
- art. 25: restituição por GRU ou compensação.

**Correção necessária:** reclassificar esses itens como **comprovados**, não como “evidência indireta”.

---

### 3.5 F19 foi classificado como inferido, mas é comprovado

**Trecho problemático da v2:**

> “F19 — Conta salário ou conta conjunta rejeitada ... Nível de evidência: Inferido”

**Falha:** a FAQ oficial diz expressamente que a conta bancária/poupança deve ser de titularidade do trabalhador e que **não são admitidas conta salário ou conta conjunta**. Também exige registro correto de banco, agência e conta.

**Correção necessária:** F19 deve ser **comprovado**. F20, sobre dados bancários incorretos, também tem base oficial forte e deve ser ao menos “comprovado quanto à possibilidade operacional”.

---

### 3.6 F26 mistura suspensão e cancelamento

**Trecho problemático da v2:**

> “Suspensão por reemprego, BPC ou recusa de recolocação”

**Falha:** a Resolução 957/2022 separa hipóteses de **suspensão** e **cancelamento**.

O art. 22 trata de suspensão por:

- admissão em novo emprego;
- início de benefício previdenciário continuado, exceto auxílio-acidente e pensão por morte;
- recusa injustificada de participar de ações de recolocação.

O art. 23 trata de cancelamento, incluindo:

- recusa de outro emprego condizente;
- comprovação de falsidade;
- comprovação de fraude;
- morte do segurado.

Além disso, a expressão “BPC” é perigosa: BPC/LOAS é benefício assistencial, enquanto o art. 22 fala em benefício de prestação continuada da previdência social, exceto auxílio-acidente e pensão por morte. A v2 precisa evitar confundir BPC/LOAS com benefício previdenciário continuado.

**Correção necessária:** separar F26 em dois fail points:

1. Suspensão por reemprego, benefício previdenciário continuado ou recusa injustificada de ações de recolocação.
2. Cancelamento por recusa de emprego condizente, fraude, falsidade ou morte.

---

### 3.7 B_EMP continua com formulação imprecisa sobre TRCT e transmissão

**Trecho problemático da v2:**

> “Empregador transmite rescisão (TRCT) e requerimento via Empregador Web...”

**Falha:** a formulação mistura documento rescisório e requerimento. O TRCT é evidência documental da rescisão, mas a etapa operacional crítica para o Seguro-Desemprego é a comunicação/requerimento do benefício com dados da dispensa. O texto deveria evitar sugerir que o TRCT, como documento, é “transmitido via Empregador Web” da mesma forma que o requerimento.

**Correção necessária:**

> Empregador registra/transmite as informações da dispensa e gera o Requerimento do Seguro-Desemprego; o TRCT permanece como evidência documental da rescisão.

---

## 4. Pontos abertos que restam

A v2 corretamente manteve várias lacunas, e elas continuam abertas:

1. Menu real da URA Caixa/0800 726 0207 para Seguro-Desemprego.
2. Existência de opção nominal “Seguro-Desemprego” na URA Caixa.
3. Escopo resolutivo do 0800 Caixa: consulta, pagamento, saque, falha de crédito, ou apenas orientação.
4. Existência de transbordo específico para Seguro-Desemprego.
5. Integração técnica entre atendimento Caixa e sistemas MTE/DATAPREV.
6. Operador atual do contact center Caixa.
7. Scripts, manuais, árvore de decisão e SLAs.
8. Logs, gravações, TMA, abandono, fila, motivos de contato e FCR.
9. Nível mínimo gov.br, se houver, para o serviço.
10. Texto literal das telas de confirmação, notificação e recurso.

Esses pontos exigem **mystery caller, LAI, prints/teste de sistema, manuais internos ou entrevistas operacionais**.

---

## 5. Quadro-resumo: audit_v1 versus v2

| Achado da audit_v1 | Situação na v2 | Veredito da segunda auditoria |
|---|---|---|
| CAGED/base Caixa na habilitação | Removido no resumo, mas CAGED reaparece em bastidor/recurso | **Parcialmente corrigido; reincidência** |
| Resultado imediato | Corrigido para processamento posterior | **Corrigido** |
| Bronze/Prata/Ouro | Rebaixado para lacuna, mas F4/F24 ainda dependem disso | **Parcial** |
| Tela de sucesso/parcelas | Rebaixada para inferido | **Corrigido** |
| Anexos JPG/PNG/PDF ≤1MB | Rebaixado para pendente | **Conservador demais; fonte oficial confirma** |
| CGSAP/BGSD | Separado como normativo versus operacional | **Corrigido** |
| CTIS e sucessores | CTIS restrita a 2017/2018 | **Corrigido** |
| Reclame Aqui como comprovado | Rebaixado | **Corrigido, com pequeno risco de superinterpretação** |
| Termo de aceite | Adicionado, mas classificado como inferido | **Parcial; Res. 957 dá base mais forte** |
| Notificação digital | Adicionada, mas com presunção de ciência superafirmada | **Parcial, com nova falha** |
| Pagamento 67 dias/FAT/5 anos/contestação/GRU | Adicionado, mas como indireto/a confirmar | **Subclassificado; deveria ser comprovado** |
| LAI/LGPD/Decretos | Adicionados | **Adicionados, mas prazos errados em LAI/ouvidoria** |
| Novos fail points F17–F26 | Adicionados | **Boa expansão, mas alguns estão mal classificados ou misturam conceitos** |

---

## 6. Conclusão

A v2 está **melhor que a v1**, mas ainda não está pronta como base rigorosa para um Service Blueprint AS-IS. Ela deve passar por uma v3 com estas correções prioritárias:

1. Remover CAGED de qualquer posição que sugira base ordinária de habilitação/recurso, salvo como hipótese claramente delimitada e comprovada.
2. Reescrever J7a/F17 para não afirmar presunção de ciência digital sem fonte específica.
3. Reclassificar como comprovados: 67 dias, devolução ao FAT, reemissão, registro eletrônico de pagamento por 5 anos, contestação de recebimento e GRU.
4. Corrigir prazos: LAI = 20 + 10; ouvidoria = 30 + 30.
5. Tratar Resolução 1027/2025 como norma específica do pescador artesanal, já alterada pela Resolução 1035/2026.
6. Separar suspensão e cancelamento no F26.
7. Reclassificar F19/F20 com base na FAQ oficial da conta bancária.
8. Manter como lacunas reais tudo que depende de URA Caixa, scripts, SLAs, logs, operador atual e escopo do 0800.

**Nota final:** a v2 foi honesta ao registrar lacunas, mas ainda “resolve no papel” alguns pontos que continuam sem prova operacional, e, em outros casos, faz o inverso: deixa como lacuna aquilo que já está comprovado normativamente.
