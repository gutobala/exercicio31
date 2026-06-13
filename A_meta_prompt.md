# Meta-prompt — Pesquisa estruturada para Service Blueprint AS-IS do Atendimento ao Seguro-Desemprego por canal telefônico/URA

> Este é o **meta-prompt** usado na Parte A: o texto que pedi a um assistente de IA
> para que ele **elaborasse** um prompt de deep research por mim — não a pesquisa em si,
> nem o prompt elaborado que ele devolveu (esse está em `prompt_assistente1_deepresearch.md`,
> e é o que se cola no Assistente 1 na Parte B).

Você é um pesquisador sênior em **Service Blueprint no serviço público**, com 10 anos de experiência em **call center governamental, atendimento telefônico, URA, IA conversacional, roteamento de chamadas, operações de retaguarda e integração entre canais digitais e presenciais**.

Seu objetivo é realizar uma **pesquisa estruturada, documental e evidencial** para sustentar a construção de um **Service Blueprint AS-IS** do serviço:

> **Atendimento ao Seguro-Desemprego pela URA da Caixa**, entendido como uma jornada em que o cidadão liga, navega menus de voz, pode ser roteado por sistemas automatizados/IA ou atendente humano, e eventualmente obtém uma resposta sobre status do benefício, pagamento, agendamento, recurso, orientação ou encaminhamento a ponto de atendimento físico.

A pesquisa deve ser feita **sem desenhar ainda o blueprint final**. O produto esperado é um relatório de insumos para posterior construção do Service Blueprint AS-IS.

---

## 1. Contexto crítico obrigatório

Antes de pesquisar, considere o seguinte achado do mapa de atores já elaborado:

> As fontes públicas oficiais consultadas **não documentam claramente uma URA específica da Caixa para Seguro-Desemprego**: não há evidência pública consolidada de número, menu, árvore de decisão, fornecedor, ASR/NLP, transbordo, escopo resolutivo ou integração com sistemas de habilitação. O canal telefônico oficial documentado para orientação trabalhista é o **158 / Alô Trabalho**, ligado ao MTE. A Caixa aparece de forma comprovada principalmente como **agente pagador** do benefício, não como responsável pela habilitação, deferimento ou recurso.

Portanto, a pesquisa deve tratar a expressão **“URA da Caixa para Seguro-Desemprego”** como uma **hipótese operacional a ser verificada**, e não como fato confirmado.

A pesquisa deve separar claramente:

1. **O que é fato comprovado em fonte oficial**;
2. **O que é evidência indireta**;
3. **O que é inferência plausível baseada em arquitetura típica de call center/URA**;
4. **O que permanece como lacuna de evidência**.

Não preencha lacunas com suposições sem rotular claramente como inferência.

---

## 2. Objetivo da pesquisa

Produzir uma base estruturada para um **Service Blueprint AS-IS** contendo, no mínimo:

a. **Etapas da jornada na ótica do cidadão**;  
b. **Processos de bastidor**, indicando quem faz o quê fora da vista do cidadão;  
c. **Evidências físicas/digitais** de cada etapa;  
d. **Normativos aplicáveis**;  
e. **Fail points conhecidos ou prováveis**, com classificação do nível de evidência.

A pesquisa deve permitir responder:

- O que o cidadão faz, vê, ouve, recebe e espera em cada etapa?
- Quais canais existem oficialmente?
- Quais atores humanos e automatizados participam da jornada?
- Que sistemas, bases de dados e órgãos atuam nos bastidores?
- Onde há ruptura, ambiguidade, transferência, abandono, erro de informação ou encaminhamento presencial?
- O que pertence ao MTE, à Caixa, à DATAPREV, ao SINE, à SRT, à Ouvidoria/CGU ou a outros órgãos?
- O que pode ser resolvido remotamente e o que ainda tende a gerar fallback presencial?
- Quais normativos e fontes sustentam cada etapa?

---

## 3. Escopo do serviço a pesquisar

Pesquisar o ecossistema operacional relacionado ao **Seguro-Desemprego** nos seguintes recortes:

### 3.1 Canais de entrada e orientação

- Telefone **158 / Alô Trabalho**;
- Eventual canal telefônico da Caixa relacionado a pagamento, benefício social, Cartão Cidadão, conta, saque ou seguro-desemprego;
- Portal de Serviços do MTE;
- Carteira de Trabalho Digital;
- SINE-Fácil, se ainda aplicável;
- Superintendências Regionais do Trabalho;
- Unidades SINE;
- Telefones de agências do trabalho estaduais;
- Fala.BR / Ouvidoria / CGU;
- Agências da Caixa, lotéricas, terminais de autoatendimento e demais canais de pagamento.

### 3.2 Etapas do Seguro-Desemprego

Mapear a jornada do cidadão desde a necessidade inicial até a resolução ou não resolução:

1. Trabalhador é dispensado e recebe ou não recebe o requerimento;
2. Busca informação sobre direito ao benefício;
3. Acessa canal digital ou telefônico;
4. Autentica-se, identifica-se ou informa dados;
5. Solicita benefício, consulta status ou busca orientação;
6. Sistema verifica dados trabalhistas e critérios;
7. Benefício é deferido, indeferido, suspenso, cancelado ou colocado em exigência;
8. Cidadão acompanha parcelas;
9. Cidadão recebe pagamento, tem falha de crédito ou busca saque;
10. Cidadão abre recurso ou solicita revisão;
11. Cidadão é orientado, transbordado, encaminhado ou obrigado a comparecer presencialmente;
12. Cidadão registra reclamação ou manifestação em ouvidoria, quando aplicável.

### 3.3 Separação institucional obrigatória

A pesquisa deve distinguir:

- **MTE**: política, serviço, habilitação, orientação, recurso e canais oficiais;
- **Caixa Econômica Federal**: agente pagador, crédito, saque, conta, Cartão Cidadão, rede de pagamento e eventuais canais de atendimento relacionados a pagamento;
- **DATAPREV/CNIS/eSocial/GFIP/GRF**: bases e infraestrutura de dados;
- **CODEFAT/FAT**: governança normativa e financiamento;
- **SINE/SRT**: atendimento presencial, correção, suporte, recurso ou fallback;
- **Ouvidoria/CGU/Fala.BR**: manifestações, reclamações, denúncias, sugestões e controle social;
- **Fornecedores de tecnologia/telefonia/IA**: apenas se houver evidência documental pública de contratação, edital, contrato, termo de referência ou notícia oficial.

---

## 4. Perguntas de pesquisa

Organize a pesquisa para responder às seguintes perguntas.

### 4.1 Jornada do cidadão

Para cada etapa da jornada, identificar:

- Qual é o gatilho que leva o cidadão a buscar atendimento?
- Que canal ele procura primeiro?
- Que informação ele precisa fornecer?
- O que ele vê, ouve ou recebe como resposta?
- Que decisões ele precisa tomar?
- Quais são os pontos de espera, fila, repetição, autenticação ou fricção?
- O atendimento termina com resolução, orientação, transbordo, recurso ou encaminhamento?
- Em que situações o cidadão precisa ir presencialmente?
- Quais diferenças existem entre consulta de **habilitação/status/recurso** e consulta de **pagamento/saque/conta**?

### 4.2 Bastidores e processos internos

Para cada etapa, identificar:

- Quem executa a atividade fora da vista do cidadão?
- Que órgão ou sistema é responsável?
- Há consulta automática a bases de dados?
- Há intervenção humana?
- Há análise, auditoria, supervisão ou controle de qualidade?
- Há roteamento por URA, ACD, ASR, NLP, bot, CRM ou fila?
- Há transbordo para atendente humano?
- Há integração entre canal telefônico e sistemas do Seguro-Desemprego?
- Há registro de protocolo?
- Há logs, gravações, trilhas de auditoria ou histórico do atendimento?
- O que acontece quando o sistema não consegue responder?

### 4.3 Evidências físicas, digitais e informacionais

Levantar, por etapa:

- Número de telefone, menu de URA, gravação, script, protocolo ou SMS;
- Tela do Portal MTE;
- Tela da Carteira de Trabalho Digital;
- Notificação de deferimento, indeferimento, suspensão ou cancelamento;
- Comprovante de solicitação;
- Extrato ou calendário de parcelas;
- Comprovante de pagamento;
- Mensagem de erro;
- E-mail da SRT;
- Manifestação Fala.BR;
- Documento judicial;
- Requerimento entregue pelo empregador;
- Cartão Cidadão;
- Comprovante de saque;
- Agendamento ou encaminhamento presencial;
- Qualquer artefato documental que o cidadão possa apresentar, receber ou consultar.

### 4.4 Normativos aplicáveis

Identificar e resumir, com citação precisa:

- Lei nº 7.998/1990;
- Resoluções CODEFAT aplicáveis, especialmente a Resolução CODEFAT nº 957/2022, se vigente ou ainda relevante;
- Normas do MTE sobre Seguro-Desemprego;
- Normas e páginas oficiais sobre canais de atendimento;
- Regras sobre solicitação, habilitação, pagamento, recurso, suspensão, cancelamento e restituição;
- Normas sobre atendimento ao usuário de serviço público, ouvidoria, simplificação, governo digital e proteção de dados quando pertinentes;
- Eventuais contratos, editais ou termos públicos relativos a atendimento telefônico, URA, IA, call center, contact center ou canais digitais, caso encontrados.

Para cada normativo, registrar:

- Nome;
- Data;
- Órgão emissor;
- Trecho ou dispositivo relevante;
- Impacto direto na jornada;
- Etapa do blueprint que ele sustenta.

### 4.5 Fail points conhecidos ou prováveis

Levantar falhas, gargalos e riscos, separando evidência comprovada de inferência. Considerar:

- Cidadão liga para a Caixa esperando resolver habilitação, mas a responsabilidade é do MTE;
- Cidadão liga para o 158 buscando informação de pagamento específico da Caixa;
- Ausência de documentação pública de URA específica da Caixa para Seguro-Desemprego;
- Confusão institucional entre MTE, Caixa, SINE, SRT e DATAPREV;
- Dificuldade de autenticação gov.br;
- Dados inconsistentes em CNIS/eSocial/GFIP/GRF;
- Requerimento não localizado;
- Divergência de vínculo, salário, data de demissão ou tipo de desligamento;
- Benefício indeferido, suspenso ou cancelado sem compreensão clara pelo cidadão;
- Recurso não encontrado, mal instruído ou demorado;
- Falha de crédito em conta indicada;
- Cidadão sem conta, senha, Cartão Cidadão ou acesso digital;
- Encaminhamento a agência Caixa, SINE ou SRT quando a expectativa era resolução remota;
- Abandono de chamada;
- Fila longa;
- Menu de URA confuso;
- Erro de reconhecimento de fala;
- Classificação incorreta de intenção;
- Transbordo inadequado;
- Atendente sem acesso a dados necessários;
- Duplicidade de orientação entre canais;
- Falta de protocolo ou rastreabilidade;
- Linguagem difícil, siglas e baixa compreensão;
- Falha de acessibilidade para público vulnerável;
- Falha de integração entre canal telefônico e sistemas de retaguarda.

---

## 5. Fontes prioritárias

Pesquisar preferencialmente em fontes oficiais, nesta ordem:

1. Portal gov.br do serviço “Solicitar o Seguro-Desemprego”;
2. Perguntas Frequentes oficiais sobre Seguro-Desemprego;
3. Ministério do Trabalho e Emprego;
4. Portal FAT / CODEFAT;
5. Legislação federal;
6. Caixa Econômica Federal, especialmente páginas sobre Seguro-Desemprego, benefícios sociais, pagamento, Cartão Cidadão, conta e canais de atendimento;
7. DATAPREV;
8. eSocial;
9. Fala.BR / CGU / Ouvidoria;
10. SINE e Superintendências Regionais do Trabalho;
11. Diários oficiais, contratos, editais e termos de referência sobre atendimento telefônico, URA, contact center, IA, bots e tecnologia de atendimento;
12. Relatórios de auditoria, acórdãos, recomendações de órgãos de controle e notícias institucionais oficiais;
13. Fontes secundárias apenas quando ajudarem a identificar falhas ou reclamações, sempre rotuladas como secundárias e não oficiais.

---

## 6. Método de pesquisa

Execute a pesquisa em fases.

### Fase 1 — Confirmação do objeto telefônico

Verificar se há, em fonte oficial:

- Número telefônico da Caixa específico para Seguro-Desemprego;
- Menu de URA da Caixa para Seguro-Desemprego;
- Orientação da Caixa sobre atendimento telefônico do Seguro-Desemprego;
- Separação entre atendimento de pagamento e atendimento de habilitação;
- Existência de transbordo para atendente humano;
- Existência de IA, reconhecimento de fala ou chatbot no fluxo telefônico;
- Scripts, árvore de decisão, FAQ, manual ou termo de referência.

Resultado esperado da fase:

- Confirmar, negar ou classificar como lacuna a existência de uma URA específica da Caixa para Seguro-Desemprego;
- Registrar fontes e evidências;
- Definir se o blueprint AS-IS deve ser modelado como:
  - jornada telefônica Caixa comprovada;
  - jornada telefônica MTE/158 comprovada;
  - jornada híbrida com Caixa apenas no pagamento;
  - jornada hipotética/lacunar a validar com pesquisa de campo.

### Fase 2 — Jornada do cidadão

Construir uma tabela com as etapas do cidadão, incluindo:

| ID | Etapa | Objetivo do cidadão | Canal | Ação do cidadão | Resposta percebida | Evidência física/digital | Resultado possível | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|

### Fase 3 — Bastidores

Construir uma tabela de bastidores:

| Etapa relacionada | Ator de bastidor | Tipo de ator | Atividade interna | Sistema/base usada | Entrada | Saída | Visível ao cidadão? | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|---|---|

Tipos de ator:

- humano;
- IA/sistema;
- documento/instrumento;
- fundo/instrumento financeiro;
- órgão de governança;
- fornecedor.

### Fase 4 — Evidências físicas e digitais

Construir uma tabela de evidências:

| Etapa | Evidência | Tipo | Quem gera | Quem recebe/consulta | Para que serve | Fonte | Nível de evidência |
|---|---|---|---|---|---|---|---|

Tipos:

- áudio/URA;
- protocolo;
- tela;
- mensagem;
- documento;
- comprovante;
- extrato;
- e-mail;
- notificação;
- registro em sistema;
- manifestação/ouvidoria.

### Fase 5 — Normativos

Construir uma matriz normativa:

| Normativo/fonte | Órgão | Data | Dispositivo relevante | O que determina | Etapa impactada | Ator impactado | Link/citação | Observação |
|---|---|---|---|---|---|---|---|---|

### Fase 6 — Fail points

Construir uma matriz de falhas:

| ID | Fail point | Etapa | Descrição | Causa provável | Impacto no cidadão | Impacto operacional | Evidência | Nível de evidência | Possível métrica | Fonte |
|---|---|---|---|---|---|---|---|---|---|---|

Classificar os fail points por tipo:

- informação;
- autenticação;
- dados;
- decisão automática;
- pagamento;
- canal;
- roteamento;
- transbordo;
- fila;
- acessibilidade;
- governança;
- integração sistêmica;
- comunicação institucional;
- presencialização indesejada.

---

## 7. Níveis de evidência

Use obrigatoriamente a seguinte escala:

- **Comprovado**: há fonte oficial pública que afirma diretamente o fato.
- **Evidência indireta**: há fonte oficial que sugere ou tangencia o fato, mas não comprova o funcionamento operacional.
- **Inferido**: é plausível por conhecimento de arquitetura de call center, URA, atendimento público ou operação de benefícios, mas não há fonte pública direta.
- **Pendente/lacuna**: elemento central para o serviço, mas não localizado em fonte pública confiável.

Toda afirmação operacional deve receber um desses níveis.

---

## 8. Atores iniciais a considerar

Considere como ponto de partida os seguintes atores mapeados previamente:

### Cidadão e programa

- Cidadão trabalhador requerente;
- Empregador;
- MTE;
- Portal de Serviços do MTE;
- Conta gov.br;
- Carteira de Trabalho Digital;
- SINE-Fácil;
- Sistema Seguro-Desemprego;
- Recurso administrativo do Seguro-Desemprego.

### Telefonia e atendimento

- 158 / Alô Trabalho / teleatendimento do MTE;
- Telefone de agência do trabalho estadual;
- Eventual URA da Caixa para Seguro-Desemprego;
- Motor de roteamento telefônico / ACD;
- Reconhecimento automático de fala / ASR;
- Classificador de intenção / NLP;
- Atendente humano da Caixa em central telefônica;
- Supervisor / gerente de fila / qualidade;
- Fornecedor de URA, telefonia, IA, CRM ou contact center.

### Dados e infraestrutura

- CNIS;
- DATAPREV;
- eSocial;
- GFIP;
- Guia de Recolhimento do FGTS;
- Documento judicial;
- Poder Judiciário;
- AGU ou órgão jurídico competente.

### Presencial, exceção e controle

- Superintendências Regionais do Trabalho;
- E-mails corporativos das SRT;
- Unidades SINE;
- Fala.BR / Ouvidoria / CGU.

### Pagamento

- Caixa Econômica Federal como agente pagador;
- Conta bancária indicada pelo trabalhador;
- Conta poupança Caixa;
- Poupança social digital Caixa;
- Cartão Cidadão;
- Terminais de autoatendimento da Caixa;
- Lotéricas e casas de conveniência;
- Agências da Caixa.

### Governança e financiamento

- CODEFAT;
- FAT — Fundo de Amparo ao Trabalhador.

---

## 9. Regras de análise

Durante a pesquisa:

1. Não confundir **pagamento do benefício** com **habilitação/concessão do benefício**.
2. Não atribuir à Caixa responsabilidades que sejam do MTE, salvo fonte oficial clara.
3. Não assumir que existe URA da Caixa específica para Seguro-Desemprego sem fonte.
4. Não assumir que há IA, ASR, NLP ou bot no canal telefônico sem evidência.
5. Quando usar conhecimento típico de call center, rotular como inferência.
6. Identificar explicitamente zonas de fronteira institucional e risco de “jogo de empurra”.
7. Priorizar fontes oficiais e normativas.
8. Distinguir atendimento remoto resolutivo de mera orientação.
9. Registrar quando a evidência está ausente, incompleta ou desatualizada.
10. Usar datas de acesso e datas de publicação das fontes.
11. Evitar linguagem promocional; manter tom analítico e diagnóstico.
12. Não propor solução TO-BE nesta etapa, exceto quando for necessário registrar uma implicação para pesquisa futura.
13. Quando houver contradição entre fontes, apresentar as versões, fonte, data e implicação.

---

## 10. Produto final esperado da pesquisa

Entregar um relatório estruturado com as seguintes seções:

1. **Resumo executivo**
   - Principais achados;
   - Confirmações;
   - Lacunas;
   - Implicações para o Service Blueprint AS-IS.

2. **Delimitação do objeto**
   - O que é comprovadamente MTE/158;
   - O que é comprovadamente Caixa/pagamento;
   - O que é lacuna sobre URA da Caixa;
   - Como isso afeta o desenho do blueprint.

3. **Tabela da jornada do cidadão**
   - Usar o modelo da Fase 2.

4. **Tabela de processos de bastidor**
   - Usar o modelo da Fase 3.

5. **Tabela de evidências físicas e digitais**
   - Usar o modelo da Fase 4.

6. **Matriz normativa**
   - Usar o modelo da Fase 5.

7. **Matriz de fail points**
   - Usar o modelo da Fase 6.

8. **Mapa de atores revisado**
   - Atualizar ou confirmar os atores do mapa inicial;
   - Indicar novos atores encontrados;
   - Remover ou reclassificar atores sem evidência, se necessário.

9. **Lacunas de evidência**
   - Questões que só podem ser respondidas por entrevista, LAI, observação, teste de chamada, auditoria interna ou documentação não pública.

10. **Recomendações para próxima etapa de pesquisa**
   - Não desenhar solução;
   - Sugerir apenas como validar o AS-IS: entrevistas, mystery caller, análise de gravações, dados de fila, relatórios de URA, logs de transbordo, reclamações, bases de ouvidoria e documentos internos.

---

## 11. Formato de saída obrigatório

A saída deve ser em Markdown, com tabelas legíveis.

Cada tabela deve conter uma coluna **Fonte** e uma coluna **Nível de evidência**.

Ao final, incluir uma seção chamada:

## Checklist para construção posterior do Service Blueprint AS-IS

Com uma lista objetiva indicando se a pesquisa já permite preencher:

- Ações do cidadão;
- Evidências físicas;
- Frontstage;
- Backstage;
- Sistemas de suporte;
- Regras/normativos;
- Fail points;
- Métricas operacionais;
- Lacunas a validar.

---

## 12. Atenção especial

O resultado da pesquisa deve ser útil para construir um Service Blueprint AS-IS, mas **não deve ainda apresentar o blueprint desenhado**.

Não entregar mapa TO-BE, proposta de solução, redesenho de jornada, plano de implantação ou recomendações de tecnologia.

O foco é produzir uma base factual e auditável para o diagnóstico do estado atual.
