# Diagrama AS-IS — Jornada do Seguro-Desemprego (trabalhador formal)

> Relações entre **etapas** (J0–J13) e **atores** (MTE, Caixa, DATAPREV, SERPRO/gov.br, Empregador, FAT, externos), a partir dos itens da Parte C (`C_blueprint_asis.md`).
> Atores agrupados por instituição (subgraphs); arestas rotuladas = ações/etapas; cilindros = bases de dados; losango = decisão automática; nós vermelhos `⚠` = **fail points**, ligados à relação que os causa.
> Codificação: `○` = lacuna/não comprovado (a URA da Caixa para SD e o marco de ciência aparecem assim).

```mermaid
flowchart LR
  Cidadao([👤 Cidadão<br>trabalhador formal])

  subgraph EXT["Origem & atores externos"]
    Emp[Empregador<br>Empregador Web]
    AGU[AGU / Justiça do Trabalho]
    RFB[(GRU / Receita Federal)]
    Ouv[Ouvidoria / Fala.BR]
  end

  subgraph GOV["gov.br / SERPRO"]
    Govbr[Telas self-service<br>gov.br · app CTPS Digital]
  end

  subgraph MTE["MTE"]
    URA158[URA 158<br>menu de voz + transbordo]
    Atend158[Atendente 158]
    SD{Sistema SD<br>triagem / decisão}
    Sec[Secretaria de Trabalho<br>recurso — instância única]
    SRT[SRT / SINE<br>atendimento presencial]
  end

  subgraph BASES["Bases de habilitação — DATAPREV"]
    CNIS[(CNIS)]
    ESoc[(eSocial)]
    GFIP[(GFIP)]
    GRF[(GRF)]
  end

  subgraph CX["CAIXA — agente pagador"]
    C0800[0800 726 0207<br>URA + atendente]
    Lote[Processamento em lote<br>arquivamento 5 anos]
    Rede[Rede física<br>agência · lotérica · Caixa Tem]
  end

  FAT[(FAT — fundo)]

  %% ---------- J0: origem ----------
  Emp -->|"J0: gera requerimento 77… (ICP-Brasil)"| SD
  Emp -.->|"entrega requerimento + TRCT"| Cidadao

  %% ---------- J2: busca de informação ----------
  Cidadao -->|"J2: liga 158"| URA158
  URA158 -->|transbordo| Atend158
  Cidadao -->|"J2: acessa o portal"| Govbr

  %% ---------- J3–J5: solicitação ----------
  Cidadao -->|"J3–J5: login + requerimento + aceite"| Govbr
  Govbr -->|"valida e envia"| SD

  %% ---------- J6: habilitação automática ----------
  SD -.->|"J6: triagem"| CNIS
  SD -.-> ESoc
  SD -.-> GFIP
  SD -.-> GRF
  AGU -.->|"doc. judicial (exceção)"| SD

  %% ---------- J7: decisão / notificação ----------
  SD -->|"J7: notificação digital<br>(deferido / indeferido / suspensão / cancelamento)"| Cidadao

  %% ---------- J9: pagamento ----------
  SD -->|"ordem de pagamento"| Lote
  FAT --- Lote
  Lote -->|"J9: crédito"| Rede
  Rede -->|"crédito em conta / Caixa Tem"| Cidadao
  Cidadao -->|"falha de crédito → liga"| C0800

  %% ---------- J9a: saque / fallback ----------
  Cidadao -->|"J9a: saca (Cartão Cidadão)"| Rede
  Rede -.->|"não sacado em 67 dias → devolve"| FAT

  %% ---------- J11 / J11a: recurso ----------
  Cidadao -->|"J11: recurso (anexos JPG/PDF)"| Govbr
  Govbr -->|protocolo| Sec
  Cidadao -->|"agenda recurso presencial"| Atend158
  Atend158 -->|agendamento| SRT
  SRT --> Sec
  Cidadao -->|"J11a: pede correção"| Emp
  Emp -.->|"retifica eSocial / GFIP"| ESoc

  %% ---------- J13 / restituição ----------
  Cidadao -->|"J13: manifestação"| Ouv
  Cidadao -.->|"devolve valor indevido (GRU)"| RFB

  %% ================= FAIL POINTS =================
  F1[/"⚠ F1 — jogo de empurra Caixa↔MTE"/]
  C0800 -.->|"'procure o MTE'"| F1
  Atend158 -.->|"'procure a Caixa'"| F1
  F1 -.-> Cidadao

  F3[/"⚠ F3/F15 — URA Caixa: opção 'SD' não documentada ○"/]
  C0800 -.-> F3

  F4[/"⚠ F4/F24/F25 — barreira de acesso ao gov.br"/]
  Govbr -.-> F4

  F5[/"⚠ F5 — dados inconsistentes (CNIS/eSocial/GFIP)"/]
  CNIS -.-> F5
  F5 -.-> SD

  F17[/"⚠ F17 — perda de prazo: marco de ciência da notificação ○"/]
  SD -.-> F17

  F8[/"⚠ F8/F16 — recurso digital 18,6% vs 67,4% · prazo 120d"/]
  Sec -.-> F8

  F9[/"⚠ F9/F19/F20 — falha de crédito / conta inválida"/]
  Lote -.-> F9

  F21[/"⚠ F21 — não sacado em 67d → devolução ao FAT"/]
  Rede -.-> F21

  F26[/"⚠ F26/F27 — suspensão (art.22) / cancelamento (art.23)"/]
  SD -.-> F26

  %% ================= ESTILOS =================
  classDef ator fill:#e3f2fd,stroke:#1565c0,color:#000;
  classDef base fill:#ede7f6,stroke:#5e35b1,color:#000;
  classDef fund fill:#fff8e1,stroke:#f9a825,color:#000;
  classDef fail fill:#ffcdd2,stroke:#c62828,color:#000;
  classDef cid  fill:#c8e6c9,stroke:#2e7d32,color:#000,stroke-width:2px;

  class Cidadao cid;
  class Emp,AGU,Ouv,Govbr,URA158,Atend158,Sec,SRT,C0800,Lote,Rede ator;
  class CNIS,ESoc,GFIP,GRF,RFB base;
  class FAT fund;
  class F1,F3,F4,F5,F17,F8,F9,F21,F26 fail;
```

---

## Como ler

- **Setas cheias** = fluxo principal da jornada (rotulado pela etapa: J0, J2, J3–J5, J7, J9, J9a, J11, J13).
- **Setas pontilhadas** = consultas a bases, exceções e desvios (triagem em J6, correção em base, devolução ao FAT, restituição via GRU).
- **Subgraphs** = fronteiras institucionais. A separação **MTE ↔ Caixa** torna visível a causa de **F1**: dois mundos (habilitação vs. pagamento) que empurram o cidadão entre si.
- **Cilindros** = bases/sistemas (CNIS, eSocial, GFIP, GRF, FAT, GRU). **Losango** `SD` = decisão automática (J6).
- **Nós vermelhos `⚠`** = fail points, ligados ao ator/relação que os origina. São os 9 mais críticos da Parte C (agrupados); os **27 completos**, com tipo, evidência e fonte, estão na tabela `C_blueprint_asis.md`.
- **`○`** marca o que é lacuna: a opção "SD" na URA da Caixa (F3) e o marco exato de ciência da notificação digital (F17).

> Renderiza direto no GitHub (Mermaid nativo). Para editar/exportar: https://mermaid.live
