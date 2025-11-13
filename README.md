# SPTrans Dashboard – Monitoramento Near Real-Time  
**Trabalho Final de MBA em Engenharia de Dados**

![SPTrans Logo](https://www.sptrans.com.br/img/sptrans.png)

> Sistema completo de ingestão, processamento e visualização de dados da frota de ônibus da SPTrans, utilizando **API Olho Vivo** e **GTFS**.

---

## Funcionalidades
- Ingestão **near real-time** (a cada 10 min) da posição de 11.131 ônibus
- Enriquecimento com GTFS (endereços completos das paradas)
- Cálculo de KPIs: Frota Ativa, % Acessível, Previsões Ativas
- Dashboard interativo com:
  - **Cards** (KPIs)
  - **Mapa** (Point Map com 11.131 pins)
  - **Tabela** (próximas chegadas em até 60 min)

---

## Arquitetura (Medallion)

Bronze (Raw) → Silver (Trusted) → Gold (Curated) → Dashboard

| Camada | Tabelas |
|-------|--------|
| Bronze | `bronze_posicao`, `bronze_previsao`, `bronze_gtfs` |
| Silver | `silver_posicao`, `silver_previsao`, `silver_paradas` |
| Gold | `gold_posicao_atual`, `gold_previsao_paradas`, `gold_kpis` |
| View | `sptrans_dashboard_data` |

---

## Tecnologias
- **Databricks** (Free Edition)
- **Delta Lake** (Lakehouse)
- **Python** (requests, pandas, geopy)
- **API Olho Vivo** (SPTrans)
- **GTFS SPTrans**
- **Databricks SQL Dashboard**

---

## Estrutura do Repositório
sptrans-mba-dashboard/
├── notebooks/          → Notebooks Databricks (.ipynb)
├── docs/               → Diagramas e relatório
├── workflow/           → Workflow JSON
├── README.md           → Este arquivo
└── .gitignore


---

## Dashboard (Link)
[Ver Dashboard ao Vivo](https://databricks.com/your-dashboard-link)

---

## Autor
**Breno** – Estudante de MBA  
GitHub: [@breso78](https://github.com/breso78)

---

> **Licença MIT** – Uso acadêmico e open source permitido.
