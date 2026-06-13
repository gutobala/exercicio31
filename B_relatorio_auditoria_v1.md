# Auditoria — Assistente 2 · audit_v1 (sobre a v1)

- **Ferramenta:** ChatGPT 5.5 — **modelo diferente do Assistente 1 (requisito da rubrica)**
- **Data:** 2026-06-13
- **Link da conversa:** (https://chatgpt.com/s/t_6a2d455e61108191a6b8b8f7bac5ab2f)

# Relatório de Auditoria v1 — Pesquisa sobre a Operação do Atendimento ao Seguro-Desemprego e a hipótese da “URA da Caixa”

## 1. Síntese da auditoria

A pesquisa auditada é consistente em sua tese central: ela evita afirmar como fato a existência de uma **“URA da Caixa específica para Seguro-Desemprego”** e separa corretamente as responsabilidades institucionais entre:

- **MTE / Central Alô Trabalho 158**: canal oficial de orientação, informação, suporte, agendamento e temas ligados à habilitação, concessão, indeferimento e recurso do Seguro-Desemprego.
- **Caixa Econômica Federal / 0800 726 0207 / rede de pagamento**: atuação relacionada ao pagamento, saque, crédito, Cartão Cidadão, Caixa Tem e benefícios sociais.

Entretanto, a pesquisa apresenta falhas relevantes de rigor metodológico e factual. O principal problema é que diversos elementos foram classificados como **“comprovados”** quando, na verdade, são **inferidos**, **anedóticos**, **históricos**, **não demonstrados por fonte oficial** ou **genéricos demais para sustentar um Service Blueprint AS-IS**.

As falhas mais importantes são:

1. Uso indevido de bases/sistemas como **CAGED** e **“base CAIXA”** no fluxo de habilitação, quando a Resolução CODEFAT nº 957/2022 lista outros meios de aferição.
2. Afirmação de “resultado imediato” na verificação automática, incompatível com os prazos oficiais do serviço.
3. Classificação excessivamente forte de evidências oriundas de **Reclame Aqui**, fontes privadas ou inferências de arquitetura de call center.
4. Omissão de processos de bastidor importantes: notificação digital, presunção de ciência, limites do recurso, devolução de parcela ao FAT, contestação de recebimento e guarda de registros pelo agente pagador.
5. Matriz normativa incompleta, especialmente pela ausência de LAI, LGPD, Decreto nº 9.094/2017 e atualização normativa posterior à Resolução 957/2022.
6. Fail points relevantes não identificados, como perda de prazo por notificação digital presumida, conta salário/conjunta inválida, parcela não sacada em 67 dias e necessidade de correção de bases externas.

---

## 2. Erros factuais ou afirmações superdimensionadas

### 2.1 Dataprev “opera a habilitação” e cruzaria CAGED/base Caixa

**Trecho auditado:**

> “A habilitação/concessão é do MTE, com triagem automatizada operada pela DATAPREV (cruzamento com CNIS, CAGED, eSocial e base CAIXA).”

**Falha identificada:**

A frase mistura fatos corretos com componentes não sustentados. A Resolução CODEFAT nº 957/2022 estabelece que os critérios de habilitação são aferidos automaticamente pelo **sistema seguro-desemprego** com informações acessíveis em:

- CNIS;
- Guia de Recolhimento do FGTS;
- GFIP;
- eSocial;
- documento judicial, quando cabível.

A norma não lista **CAGED** nem **“base CAIXA”** como meios ordinários de aferição da habilitação.

**Justificativa:**

A Caixa atua no pagamento. A competência de habilitação/concessão é do MTE, com processamento pelo sistema seguro-desemprego. A Dataprev pode ser ator tecnológico relevante, mas o relatório não deveria afirmar, sem fonte direta, que ela “opera a habilitação” cruzando CAGED e base Caixa.

**Correção sugerida:**

> Os critérios de habilitação são aferidos automaticamente pelo sistema seguro-desemprego com base em CNIS, GRF, GFIP, eSocial e documento judicial, quando cabível. A Dataprev deve ser tratada como ator tecnológico/processador relevante, mas separando processamento técnico da competência decisória do MTE.

---

### 2.2 “Resultado imediato” da verificação automática

**Trecho auditado:**

> “J6 | Verificação automática | — (bastidor) | DATAPREV/sistemas | Nenhuma (automático) | Resultado imediato...”

**Falha identificada:**

A expressão **“resultado imediato”** é forte demais. Ainda que haja aferição automática, o serviço oficial trabalha com prazo estimado de prestação e a própria disciplina normativa prevê pagamento da primeira parcela após determinado prazo contado do requerimento.

**Justificativa:**

Para um Service Blueprint AS-IS, a diferença entre “validação automática” e “resultado imediato percebido pelo cidadão” é fundamental. Afirmar resultado imediato pode ocultar pontos de espera, ansiedade, consulta repetida, ligações ao 158/0800 e reclamações.

**Correção sugerida:**

> Verificação automática pelo sistema seguro-desemprego, com resultado digital posterior ou disponibilizado conforme processamento e prazos do serviço.

---

### 2.3 Uso de “Bronze/Prata/Ouro” como requisito comprovado

**Trecho auditado:**

> “Login gov.br (Bronze/Prata/Ouro)”

**Falha identificada:**

O relatório não demonstra que o serviço de Seguro-Desemprego exige nível específico da conta gov.br. O uso de conta gov.br é correto, mas a classificação por níveis Bronze, Prata ou Ouro não foi comprovada no relatório como requisito operacional do serviço.

**Justificativa:**

Nível de conta gov.br pode ser requisito em vários serviços públicos, mas não deve ser transportado automaticamente para este serviço sem fonte direta.

**Correção sugerida:**

> Login com conta gov.br, com eventual exigência de nível de autenticação a confirmar em fonte oficial ou teste de uso.

---

### 2.4 “Tela ‘Solicitação realizada com sucesso’ + parcelas” como evidência comprovada

**Trecho auditado:**

> “J5 | Solicitação | ... | ‘Solicitação realizada com sucesso’ + parcelas | Tela de confirmação; termo de aceite | ... | Comprovado”

**Falha identificada:**

A existência de uma tela de confirmação é plausível, mas a literalidade da mensagem **“Solicitação realizada com sucesso”** e a exibição imediata de parcelas não foram demonstradas.

**Justificativa:**

Para evidência física/digital de blueprint, deve-se diferenciar:

- tela observada em teste;
- tela documentada em manual;
- mensagem inferida;
- expectativa genérica de confirmação.

**Correção sugerida:**

Classificar como **inferido** ou **a confirmar por teste de tela**, salvo se houver print, manual de sistema ou evidência oficial.

---

### 2.5 “Anexos JPG/PNG/PDF ≤1MB” no recurso

**Trecho auditado:**

> “Tela de recurso; anexos JPG/PNG/PDF ≤1MB”

**Falha identificada:**

A possibilidade de anexar documentos no recurso é plausível e prevista no fluxo digital, mas os formatos e o limite de 1 MB não foram comprovados no relatório.

**Justificativa:**

Formatos e tamanho de anexo são requisitos operacionais específicos e devem ser citados apenas com fonte direta, print do sistema, manual ou teste documentado.

**Correção sugerida:**

> Tela de recurso com anexação de documentos digitais conforme exigência do sistema. Formatos e limites de tamanho a confirmar.

---

### 2.6 “MTE/CGSAP” como ator de análise de recursos e “BGSD” como sistema usado

**Trecho auditado:**

> “J6 | MTE/CGSAP | Humano | Análise de recursos centralizada | BGSD | Recurso | Decisão | ... | Comprovado”

**Falha identificada:**

A Resolução CODEFAT nº 957/2022 atribui o julgamento de recursos à Secretaria de Trabalho em instância única, mas o relatório não comprova que a unidade operacional seja especificamente a **CGSAP** nem que o sistema usado no julgamento seja a **BGSD**.

**Justificativa:**

A existência de uma base ou relatório chamado BGSD não implica, automaticamente, que esse seja o sistema operacional de análise de recurso. A unidade interna também precisa de fonte específica.

**Correção sugerida:**

Separar:

- **Normativo comprovado:** Secretaria de Trabalho julga o recurso em instância única.
- **Operacional a confirmar:** unidade interna responsável, sistema usado, fila de análise, critérios e SLAs.

---

### 2.7 “Fornecedores de tecnologia — CTIS e sucessores confirmados”

**Trecho auditado:**

> “Fornecedores de tecnologia (CTIS Tecnologia S.A. e sucessores): confirmados como operadores da solução de contact center da Caixa...”

**Falha identificada:**

O próprio relatório reconhece que a empresa atualmente operadora do Pregão 013/5688-2024 não foi localizada. Portanto, a expressão **“e sucessores confirmados”** é indevida.

**Justificativa:**

O Acórdão TCU 1151/2018 pode comprovar uma contratação específica daquele período, mas não comprova o operador atual nem a cadeia de fornecedores sucessores.

**Correção sugerida:**

> CTIS confirmada em contratação específica de 2017/2018; operador atual e eventuais sucessores não confirmados.

---

### 2.8 “Mensagem ‘parcela emitida’/não creditada” classificada como comprovada

**Trecho auditado:**

> “J9-J10 | Mensagem ‘parcela emitida’/não creditada | Mensagem/tela | Sistemas | Cidadão | Diagnóstico | Reclame Aqui; gov.br FAQ | Comprovado”

**Falha identificada:**

Relato em Reclame Aqui pode comprovar que **um usuário relatou** a mensagem, mas não comprova que essa seja uma mensagem oficial, recorrente ou padronizada do sistema.

**Justificativa:**

Reclame Aqui serve como indício ou evidência indireta, não como comprovação oficial da evidência física/digital do serviço.

**Correção sugerida:**

Reclassificar como **evidência indireta/anedótica**, salvo se a mensagem aparecer em FAQ oficial, manual, print ou sistema testado.

---

## 3. Inferências mal-suportadas ou fontes fracas

### 3.1 Reclame Aqui usado como “comprovado” para fail point sistêmico

**Trecho auditado:**

> “F1 | ‘Jogo de empurra’ Caixa↔MTE ... | Reclame Aqui (...) | Comprovado (relato)”

**Falha identificada:**

O nível correto não é **comprovado** para o fenômeno sistêmico. O máximo que se pode afirmar é que há **relatos públicos individuais** de jogo de empurra.

**Justificativa:**

Reclame Aqui não permite estimar incidência, causalidade, responsabilidade institucional ou frequência operacional. É útil para gerar hipótese de fail point, mas não para comprovar comportamento sistêmico.

**Correção sugerida:**

> Evidência indireta — relato público. Validar por amostra Fala.BR, logs de atendimento, LAI, entrevistas ou mystery caller.

---

### 3.2 Fonte privada “taxpratico” para inconsistência CNIS/eSocial

**Trecho auditado:**

> “F5 | Dados inconsistentes CNIS/eSocial ... | taxpratico (falha eSocial/CNIS 2022, alerta INSS) | Comprovado”

**Falha identificada:**

Fonte privada não deveria sustentar classificação **comprovada** em pesquisa de serviço público. A inconsistência de bases é plausível e normativamente reconhecida, mas deveria ser sustentada por fonte oficial.

**Justificativa:**

A própria Resolução CODEFAT nº 957/2022 prevê que inconsistências podem impedir a habilitação automática e gerar necessidade de recurso/correção.

**Correção sugerida:**

Substituir a fonte por:

- Resolução CODEFAT nº 957/2022;
- relatórios oficiais CGU/TCU, se disponíveis;
- dados administrativos obtidos por LAI.

---

### 3.3 Dados de capacidade do 158 de 2015 usados como AS-IS atual

**Trecho auditado:**

> “Capacidade da central: ... pode receber até 26 mil ligações diárias e 780 mil por mês ... 157 PAs...”

**Falha identificada:**

Não é necessariamente um erro histórico, mas é fraco para sustentar um blueprint AS-IS de 2026.

**Justificativa:**

Capacidade de inauguração em 2015 não comprova capacidade atual, dimensionamento atual, TMA, abandono, fila, transbordo ou taxa de resolução.

**Correção sugerida:**

Classificar como **histórico** e buscar dado atual via LAI, relatório de contrato, relatório gerencial ou painel operacional.

---

### 3.4 Uso do 0800 da Caixa como canal seguro de acompanhamento/pagamento

**Trecho auditado:**

> “J8 | Acompanhar parcelas | ... | app CTPS Digital / gov.br / 158 / 0800 Caixa | Consulta calendário... | Comprovado”

**Falha identificada:**

O canal 0800 726 0207 é oficial para atendimento ao cidadão/benefícios sociais, mas o relatório não comprova que ele forneça calendário, dados completos, status detalhado ou resolução específica do Seguro-Desemprego.

**Justificativa:**

A Caixa pode tratar pagamento e saque, mas o escopo exato da consulta telefônica sobre Seguro-Desemprego precisa ser validado por fonte oficial específica, teste de chamada ou manual de atendimento.

**Correção sugerida:**

> 0800 Caixa como canal de atendimento de benefícios sociais/pagamento, com escopo exato para Seguro-Desemprego a confirmar.

---

## 4. Etapas de bastidor omitidas

### 4.1 Comunicação eletrônica do empregador com certificado ICP-Brasil

**Omissão:**

A pesquisa cita Empregador Web/eSocial, mas não detalha o backstage normativo do empregador: transmissão eletrônica obrigatória pelo portal Empregador Web, com certificado digital ICP-Brasil e campos obrigatórios.

**Por que importa:**

Erros nessa etapa geram:

- requerimento não localizado;
- divergência de dados;
- falha na habilitação automática;
- necessidade de correção;
- presencialização.

---

### 4.2 Termo declaratório/termo de aceite como controle de elegibilidade

**Omissão parcial:**

O termo aparece como evidência, mas não como controle de bastidor. A Resolução exige assinatura de termo declaratório no presencial ou confirmação de termo de aceite no digital.

**Por que importa:**

Esse termo é ponto de controle de elegibilidade e potencial fail point de compreensão. O cidadão pode declarar incorretamente ou não entender as consequências.

---

### 4.3 Notificação exclusivamente digital e presunção de ciência após cinco dias

**Omissão grave:**

A pesquisa fala em notificação digital, mas não captura adequadamente o mecanismo de ciência/prazo: notificações podem ocorrer exclusivamente por meio digital, com presunção de ciência após disponibilização no ambiente do usuário.

**Por que importa:**

Esse é um fail point central. O cidadão pode perder prazo de recurso sem perceber a notificação.

---

### 4.4 Regras de mérito do recurso e necessidade de corrigir bases externas

**Omissão:**

O relatório não explicita que o recurso pode ficar limitado aos requisitos analisados e que alterações em bases de dados devem ser providenciadas pelos interessados.

**Por que importa:**

Isso explica por que recursos podem ser indeferidos mesmo quando o cidadão acredita ter razão. O problema pode estar em bases de origem, empregador, vínculos, dados trabalhistas ou documentação judicial.

---

### 4.5 Lote de pagamento, comprovação e guarda pelo agente pagador

**Omissão:**

A pesquisa diz “crédito de parcelas”, mas não registra o backstage de comprovação do pagamento: autenticação em documento próprio ou registro eletrônico, arquivado pelo agente pagador.

**Por que importa:**

Esse registro é evidência oficial de pagamento, útil para contestação e auditoria.

---

### 4.6 Parcela disponível por 67 dias, devolução ao FAT e reemissão

**Omissão:**

O relatório não inclui a regra operacional de disponibilidade da parcela, devolução ao FAT e possibilidade de reemissão.

**Por que importa:**

É um fail point concreto: o cidadão que não saca no prazo pode perder acesso imediato à parcela e depender de reemissão.

---

### 4.7 Contestação de recebimento de parcelas

**Omissão:**

A pesquisa não detalha o procedimento de contestação quando o trabalhador afirma não ter recebido parcela.

**Por que importa:**

Esse é um subprocesso de exceção de pagamento que deveria aparecer no blueprint, envolvendo cidadão, MTE, Caixa/agente pagador, registros de pagamento e eventual procedimento administrativo.

---

### 4.8 AGU e documento judicial no fluxo de exceção

**Omissão parcial:**

O relatório cita documento judicial, mas não detalha no backstage a validação da força executória por órgão jurídico competente da AGU.

**Por que importa:**

Esse ponto afeta casos de vínculo, demissão, remuneração ou períodos não reconhecidos pelas bases automáticas.

---

## 5. Evidências físicas/digitais relevantes que ficaram de fora ou foram mal classificadas

### 5.1 Registro eletrônico/autenticação de pagamento arquivado pelo agente pagador

**Falha:**

A pesquisa cita extrato e comprovante de saque, mas não inclui o registro eletrônico/autenticação de pagamento mantido pelo agente pagador.

**Por que importa:**

É uma evidência oficial de bastidor, mais robusta que o extrato do cidadão.

---

### 5.2 Notificação digital com data de disponibilização

**Falha:**

A matriz de evidências não trata a data/hora de disponibilização da notificação como evidência crítica.

**Por que importa:**

Essa data é fundamental para contagem de prazo e presunção de ciência.

---

### 5.3 GRU de restituição

**Falha:**

A pesquisa não inclui a GRU de restituição em casos de recebimento indevido.

**Por que importa:**

A GRU é evidência física/digital relevante para fluxo de devolução, compensação e controle financeiro.

---

### 5.4 Protocolo, gravação, log de URA e tabulação do atendimento

**Falha:**

O relatório menciona protocolo de atendimento telefônico Caixa como inferido, mas deveria listar de forma mais completa as evidências de bastidor a obter:

- gravação de chamada;
- log de URA;
- motivo de contato;
- tabulação do atendente;
- tempo de espera;
- transferência;
- fila;
- abandono;
- encerramento;
- protocolo.

**Por que importa:**

Esses elementos são essenciais para validar a operação real da URA/central e desenhar o blueprint AS-IS.

---

### 5.5 Procuração, alvará judicial e representação

**Falha:**

A pesquisa não contempla documentos de representação, procuração, alvará judicial e hipóteses envolvendo sucessores/dependentes.

**Por que importa:**

Embora sejam fluxos excepcionais, eles integram a operação real e podem gerar atendimento presencial, análise documental e pontos de falha.

---

## 6. Normativos relevantes omitidos ou insuficientemente tratados

### 6.1 Resolução CODEFAT/MTE nº 1027/2025

**Trecho auditado:**

> “Resolução CODEFAT nº 957 ... Norma central vigente”

**Falha:**

A Resolução 957/2022 continua central, mas deve ser tratada com alterações posteriores, inclusive por norma de 2025.

**Correção sugerida:**

> Resolução CODEFAT nº 957/2022, com alterações posteriores, inclusive Resolução CODEFAT/MTE nº 1027/2025, quando aplicável.

---

### 6.2 Lei nº 12.527/2011 — Lei de Acesso à Informação

**Falha:**

A pesquisa recomenda pedidos LAI, mas não inclui a Lei de Acesso à Informação na matriz normativa.

**Por que importa:**

A LAI é central para obtenção de árvore de URA, contratos, scripts, SLA, logs, relatórios e manuais.

---

### 6.3 Lei nº 13.709/2018 — LGPD

**Falha:**

A LGPD está ausente.

**Por que importa:**

O serviço envolve CPF, NIS/PIS, dados trabalhistas, remuneração, dados bancários, gravações de voz e possivelmente dados tratados por sistemas automatizados/IA.

---

### 6.4 Decreto nº 9.094/2017 e Carta de Serviços

**Falha:**

A pesquisa cita a Lei 13.460/2017, mas não inclui o Decreto nº 9.094/2017.

**Por que importa:**

Esse decreto é relevante para simplificação do atendimento, atendimento ao usuário e Carta de Serviços no Executivo Federal.

---

### 6.5 Normativos de ouvidoria pública

**Falha:**

A pesquisa menciona Fala.BR/CGU e Lei 13.460/2017, mas não detalha a regulamentação operacional de ouvidoria.

**Por que importa:**

Para fail points de “jogo de empurra”, tratamento de manifestação, prazo, resposta e escalonamento são partes importantes do blueprint.

---

## 7. Fail points não identificados ou subdesenvolvidos

### 7.1 Perda de prazo por presunção de notificação digital

**Falha:**

O relatório tem F16 “perda de prazo”, mas não identifica o mecanismo específico: notificação digital presumida válida após disponibilização.

**Impacto no cidadão:**

Perda do prazo de recurso por desconhecimento da ciência digital.

---

### 7.2 Recurso indeferido porque exige alteração em base de origem

**Falha:**

O relatório não identifica o ciclo em que o cidadão recorre, mas a solução depende de correção em base externa, empregador, sistema de origem ou documentação judicial.

**Impacto no cidadão:**

Recurso mal instruído, indeferimento, necessidade de atendimento presencial ou acionamento de terceiros.

---

### 7.3 Conta salário ou conta conjunta rejeitada

**Falha:**

O relatório trata genericamente de falha de crédito, mas não explicita que conta salário e conta conjunta podem ser incompatíveis com o pagamento.

**Impacto no cidadão:**

Parcela não creditada, necessidade de saque por outra via, ida à agência ou ligação para Caixa/158.

---

### 7.4 Dados bancários incorretos informados pelo cidadão

**Falha:**

O relatório cita falha de crédito, mas não detalha erro de banco, agência, conta ou titularidade como fail point operacional.

**Impacto no cidadão:**

Atraso no recebimento, abertura/uso de conta alternativa, necessidade de orientação ou atendimento presencial.

---

### 7.5 Parcela não sacada em 67 dias e devolvida ao FAT

**Falha:**

Não aparece na matriz de fail points.

**Impacto no cidadão:**

Perda de disponibilidade imediata da parcela e necessidade de reemissão.

---

### 7.6 Contestação de recebimento

**Falha:**

Não aparece como fail point específico.

**Impacto no cidadão:**

Trabalhador afirma não ter recebido, mas precisa de procedimento administrativo e evidências de pagamento.

---

### 7.7 Trabalhador doméstico fora do fluxo digital comum

**Falha:**

O relatório cita empregado doméstico, mas não transforma essa diferença em fail point ou desvio de jornada.

**Impacto no cidadão:**

Dependência de agendamento pelo 158 e atendimento presencial.

---

### 7.8 Falha no cadastro gov.br com dependência de Banco do Brasil/Caixa ou posto conveniado

**Falha:**

A dificuldade de autenticação gov.br aparece genericamente, mas faltou detalhar o caminho de exceção.

**Impacto no cidadão:**

Dependência de terminal bancário, posto SRT/conveniado ou apoio presencial.

---

### 7.9 Falta de internet

**Falha:**

Não aparece como fail point autônomo.

**Impacto no cidadão:**

Desvio obrigatório para atendimento presencial em SINE/SRT, com custo de deslocamento, fila e tempo.

---

### 7.10 Suspensão por reemprego, BPC ou recusa de recolocação

**Falha:**

A matriz normativa cita hipóteses de suspensão, mas a matriz de fail points não trata adequadamente esses cenários.

**Impacto no cidadão:**

Surpresa com suspensão, dificuldade de compreensão do motivo, recurso ou deslocamento para atendimento.

---

## 8. Omissões na jornada do cidadão

### 8.1 Pré-jornada: rescisão, TRCT e transmissão pelo empregador

A jornada começa na dispensa sem justa causa, mas deveria detalhar melhor:

- comunicação da dispensa;
- emissão/transmissão do requerimento;
- TRCT;
- Empregador Web;
- possíveis erros de preenchimento;
- dados obrigatórios da rescisão.

Esses elementos são decisivos para a qualidade do requerimento e para falhas posteriores.

---

### 8.2 Etapa de ciência da notificação

Entre “resultado” e “recurso”, falta uma etapa autônoma:

> Cidadão toma ciência da notificação digital.

Essa etapa é crítica porque marca a contagem de prazo, a presunção de ciência e a possibilidade de perda do direito de recorrer tempestivamente.

---

### 8.3 Etapa de correção de dados fora do MTE

A jornada presume “recurso” ou “presencialização”, mas não mostra claramente que o cidadão pode precisar acionar:

- empregador;
- base de origem;
- documentação judicial;
- órgão jurídico;
- SRT/SINE;
- sistema cadastral.

---

### 8.4 Etapa de pagamento excepcional

O pagamento deveria ser desdobrado em mais subetapas:

1. crédito em conta informada;
2. tentativa de localização de conta alternativa pelo agente pagador;
3. crédito em conta digital/social, quando aplicável;
4. saque por Cartão Cidadão/rede física;
5. saque em agência;
6. não saque no prazo;
7. devolução ao FAT;
8. reemissão;
9. contestação de não recebimento.

---

## 9. Conclusão da auditoria

A pesquisa auditada possui um núcleo analítico sólido: a **URA específica da Caixa para Seguro-Desemprego permanece como lacuna**, enquanto o **158/MTE** é o canal telefônico oficial de orientação e a **Caixa** atua como agente pagador.

No entanto, para sustentar um **Service Blueprint AS-IS rigoroso**, recomenda-se revisar o relatório nos seguintes pontos:

1. **Rebaixar níveis de evidência** onde há Reclame Aqui, inferência de arquitetura, fonte privada ou tela não observada.
2. **Corrigir as bases de habilitação**, substituindo CAGED/base Caixa por CNIS, GRF, GFIP, eSocial e documento judicial, conforme a Resolução CODEFAT nº 957/2022.
3. **Adicionar backstage normativo-operacional**: Empregador Web/ICP-Brasil, notificação digital, presunção de ciência, limites do recurso, pagamento arquivado por cinco anos, devolução ao FAT, reemissão e contestação.
4. **Ampliar fail points**: perda de prazo digital, conta inválida/salário/conjunta, parcela não sacada, necessidade de corrigir bases externas, trabalhador doméstico, ausência de internet e contestação de recebimento.
5. **Complementar a matriz normativa** com LAI, LGPD, Decreto nº 9.094/2017, alterações posteriores da Resolução 957/2022 e normas operacionais de ouvidoria.
6. **Separar claramente o que é canal documentado, hipótese operacional, evidência indireta e lacuna**, para que o blueprint não transforme suposições em fatos.

## 10. Recomendação prática para a próxima versão da pesquisa

A próxima versão do relatório deveria incluir uma coluna obrigatória chamada **“status de evidência operacional”**, com os seguintes níveis:

| Nível | Definição | Exemplo |
|---|---|---|
| Fato oficial | Confirmado em lei, resolução, página oficial, edital ou relatório público | MTE é responsável pela habilitação |
| Evidência operacional direta | Confirmado por teste, print, gravação, manual, script ou LAI | Menu real da URA 0800 |
| Evidência indireta | Relato público, notícia antiga, fonte secundária ou reclamação | Jogo de empurra Caixa↔MTE |
| Inferência técnica | Dedução plausível por arquitetura de call center ou sistema | Existência de log de URA |
| Lacuna | Não comprovado e central para a operação | Opção nominal “Seguro-Desemprego” na URA Caixa |

Essa distinção é essencial para que o Service Blueprint AS-IS não confunda o que está documentado com o que apenas parece provável.
