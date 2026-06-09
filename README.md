# 🏥 Painel Inteligente de Acesso Hospitalar

**Challenge Oracle + FIAP · Sprint 1 · Turma 1TSCO**

Painel analítico para visualização e análise de dados de internações hospitalares no Brasil, integrando dados do SIH/SUS, CNES e IBGE.

## 🚀 Acesse o painel

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io)

## 📊 Funcionalidades

- **Dashboard Principal** — métricas gerais, ranking de municípios e distribuição por zona de pressão hospitalar
- **Análise por Região** — filtros por estado, zona e indicadores per capita com gráficos interativos
- **Oracle Select AI** — simulação de consultas em linguagem natural que geram SQL automaticamente
- **Estabelecimentos** — busca e visualização de hospitais com dados do CNES

## 🗃️ Fontes de Dados

| Fonte | Formato | Descrição |
|-------|---------|-----------|
| SIH/SUS | Relacional | 465.261 internações — SP + RJ, 1º sem/2024 |
| CNES | JSON via API | 10.000+ estabelecimentos (88 hospitalares) |
| IBGE | CSV via External Table | ~5.500 municípios brasileiros |

## 🏗️ Arquitetura

```
Google Colab (ingestão)
    ↓
OCI Object Storage (bucket datalake-datascience)
    ↓
Oracle Autonomous DB Lakehouse (Always Free)
    ├── Select AI (perguntas em linguagem natural → SQL)
    └── Views analíticas (internações per capita, pressão hospitalar)
         ↓
Streamlit Dashboard (este repositório)
```

## ⚙️ Como executar localmente

```bash
pip install -r requirements.txt
streamlit run app.py
```

## 👥 Equipe

**Turma:** 1TSCO — FIAP  
**Integrantes:** [adicionar nomes e RMs]

## 📅 Cronograma

- **Sprint 1 — 16/06:** Ideação + Arquitetura (este protótipo)
- **Sprint 2 — 01/09:** MVP com dados reais + Select AI + vídeo pitch
