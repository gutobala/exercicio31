# Transcript da sessão `/grill-me` (Parte C)

- **Service Blueprint AS-IS — Jornada do Seguro-Desemprego**
- **Contexto base:** `@B_relatorio_assistente_v3.md`
- **Ferramenta:** Claude Code (skill `grill-me`)
- **Data:** 2026-06-13
- **Método:** entrevista guiada, uma pergunta por vez, descendo a árvore de decisões; **eu** decido cada nó.

# Transcript do grill-me — Service Blueprint AS-IS (Seguro-Desemprego)

> Registro das perguntas da entrevista e das **respostas do usuário**.
> Insumo de contexto: `B_relatorio_assistente_v3.md`. Entregável gerado: `C_blueprint_asis.md`.

---

**Solicitação inicial:** Elaborar conceitualmente um Service Blueprint AS-IS da jornada "Atendimento ao Seguro-Desemprego pela URA da Caixa", seguindo a metodologia de Shostack — camadas (Evidências Físicas, Ações do Cidadão, Frontstage, Backstage, Processos de Suporte), as linhas divisórias (interação, visibilidade, interação interna) e os fail points.

---

### 1. Escopo

**Pergunta:** O título diz "URA da Caixa", mas o insumo prova que esse canal, para SD, é quase todo lacuna (só pagamento é confirmado) e que o protagonista real do atendimento ao SD é o 158/MTE + canal digital gov.br. Qual é o escopo (a fronteira) do seu Service Blueprint AS-IS?

**Resposta:** Jornada SD completa multicanal.

---

### 2. Caminho (eixo horizontal)

**Pergunta:** Como você vai tratar os múltiplos caminhos/desfechos no eixo horizontal do blueprint?

**Resposta:** Espinha única + ramos de exceção.

---

### 3. Estrutura multi-ator (eixo vertical)

**Pergunta:** Como estruturar Frontstage/Backstage com múltiplas instituições (MTE, Caixa, DATAPREV, SERPRO, Empregador)?

**Resposta:** 5 camadas canônicas + dono anotado.

---

### 4. Linha de visibilidade

**Pergunta:** Como tratar os elementos marcados como "Parcialmente visíveis" (aceite, notificação, contestação) em relação à linha de visibilidade binária de Shostack?

**Resposta:** Desmembrar em duas ações (parte percebida no Frontstage; processamento oculto no Backstage).

---

### 5. Linha de interação interna

**Pergunta:** Onde cai a linha de interação interna — o que é Backstage vs. Processo de Suporte?

**Resposta:** Backstage = processa ESTE caso; Suporte = infraestrutura permanente.

---

### 6. Evidências Físicas

**Pergunta:** O que entra na camada Evidências Físicas?

**Resposta:** Só o que o cidadão percebe (registros de auditoria descem para o bastidor).

---

### 7. Fail points

**Pergunta:** Como representar os 27 fail points no blueprint AS-IS?

**Resposta:** Todos os 27, ancorados e codificados.

---

### 8. Camada epistêmica

**Pergunta:** Você vai aplicar a codificação por nível de evidência a TODOS os elementos do blueprint, ou só aos fail points?

**Resposta:** A todos os elementos (camada epistêmica).

---

### 9. Dimensão temporal

**Pergunta:** Como o blueprint representa a dimensão temporal (esperas assíncronas e prazos legais)?

**Resposta:** Anotar prazos/SLAs + marcar a espera de J6.

---

### 10. Persona

**Pergunta:** Qual persona/modalidade o blueprint AS-IS representa?

**Resposta:** Trabalhador formal; doméstico como ramo.

---

### 11. Entregável

**Pergunta:** Qual é a forma do entregável conceitual do blueprint?

**Resposta:** Usar tabela (markdown). Mapear ≥ 5 etapas na ótica do cidadão, com as cinco camadas e marcando os fail points.

---

### 12. Layout da tabela

**Pergunta:** Qual a orientação da tabela markdown do blueprint?

**Resposta:** Etapas em linhas × camadas em colunas.

---

### 13. Próximo passo

**Pergunta:** A especificação consolidada reflete o que você quer? Como prosseguimos?

**Resposta:** Construir o blueprint agora.
