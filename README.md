# Exercício 3.1 — Service Blueprint AS-IS — Jornada do Seguro-Desemprego

**Aluno:** Gustavo Salvador Ferraz Ferreira
**Disciplina:** Transformação Digital no Governo - Turma 1/2026
**Serviço escolhido:** Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal

---

## Índice dos entregáveis

### Parte A — Meta-prompt
- [A_meta_prompt.md](A_meta_prompt.md) — meta-prompt usado para iniciar a pesquisa no assistente 1

### Parte B — Auditoria iterativa (v1 → audit_v1 → v2 → audit_v2 → v3)
- [B_relatorio_assistente_v1.md](B_relatorio_assistente_v1.md) — pesquisa original do assistente 1 (Claude Sonnet 4.6)
- [B_relatorio_auditoria_v1.md](B_relatorio_auditoria_v1.md) — auditoria da v1 pelo assistente 2 (ChatGPT 5.5)
- [B_relatorio_assistente_v2.md](B_relatorio_assistente_v2.md) — revisão do assistente 1 após audit_v1 (Claude Sonnet 4.6)
- [B_relatorio_auditoria_v2.md](B_relatorio_auditoria_v2.md) — segunda auditoria (sobre a v2) pelo assistente 2 (ChatGPT 5.5)
- [B_relatorio_assistente_v3.md](B_relatorio_assistente_v3.md) — versão final do assistente 1 após audit_v2 (Claude Sonnet 4.6)

### Parte C — Service Blueprint AS-IS via `/grill-me`
- [C_grill_transcript.md](C_grill_transcript.md) — transcript integral da sessão `/grill-me`
- [C_blueprint_asis.md](C_blueprint_asis.md) — Service Blueprint AS-IS — Jornada do Seguro-Desemprego 

### Parte D — Diagrama da jornada
- [D_diagrama_asis.md](D_diagrama_asis.md) - Diagrama Mermaid do Service Blueprint AS-IS


---

## Assistentes utilizados (modelos distintos — requisito)

- **Assistente 1 (pesquisa):** Claude Sonnet 4.6 — produz audit_v1, audit_v2
- **Assistente 2 (auditoria):** ChatGPT 5.5 — produz v1, v2, v3

## Configuração do autograder

- Marcador presente: [`.autograde-exercise`](.autograde-exercise) (conteúdo: `3.1`)

Para validar localmente:

```bash
autograde validar 3.1
```
