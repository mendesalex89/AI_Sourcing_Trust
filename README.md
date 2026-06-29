# AI_Sourcing_Trust


CONTEXTO
Sou Data Scientist com experiência em produção: construí uma plataforma BI+IA
(Django + React + LangGraph + DuckDB) com agentes LLM (RAG/FAISS, NL→SQL,
observabilidade MLflow) e um pipeline de ML de reposição de retalho (XGBoost
quantílico em GPU, forecasting estilo Vandeput, backtests). Vou candidatar-me a
uma vaga de AI Engineer (setor logística, remoto) que pede: LLMs, Machine
Learning E Deep Learning, Python (+Java para integração), NumPy/Pandas/Matplotlib
e frameworks PyTorch/TensorFlow/Keras/LangChain.
Quero um projeto-showcase público que prove as lacunas que ainda não tenho
evidenciadas: (1) Deep Learning com PyTorch; (2) cloud (GCP). A capacidade de
construir plataformas completas já está provada no meu trabalho atual — este
projeto é FOCADO, não uma plataforma inteira.

OBJETIVO
Ajuda-me a construir, do zero e por fases, um projeto open-source "LogiForecast"
— Inteligência de Procura & Reposição para Logística — com duas camadas de IA,
end-to-end (PoC→MVP), reproduzível e bem documentado.

CAMADA 1 — DEEP LEARNING (lacuna a cobrir)
- Forecasting de procura por SKU×loja em PyTorch: Temporal Fusion Transformer
  (ou LSTM/N-BEATS). Explica a arquitetura da rede, não só a usar.
- Baseline XGBoost + baseline ingénuo, para comparação justa.
- Métricas honestas: RMSSE/WRMSSE ou pinball loss (quantis), MAPE, vs baselines.
- Dataset: M5 Forecasting (Walmart, Kaggle) como default; camada de ingestão
  trocável. Se M5 for pesado, começa por 1 categoria/estado e escala.

CAMADA 2 — COPILOTO LLM (a minha força)
- Agente LangChain/LangGraph que: (a) explica a previsão em linguagem natural
  ("porque repor 12 unidades?") usando feature importance/SHAP; (b) faz NL→query
  sobre stock/vendas (DuckDB); (c) RAG sobre documentação de política de reposição.
- LLM via API configurável por variável de ambiente (OpenAI/Anthropic/OpenRouter),
  com modelo barato por default.

INTERFACE — STREAMLIT (link público, duplo propósito)
A app Streamlit tem DUAS funções e deve refletir isso na navegação:
1. DEMO INTERATIVO: escolher SKU → gráfico de previsão (PyTorch vs XGBoost) →
   chat com o copiloto LLM.
2. APRESENTAÇÃO PARA STAKEHOLDERS NÃO-TÉCNICOS: uma secção que explica, em
   linguagem simples e com DIAGRAMAS (arquitetura, fluxo de dados, pipeline
   PoC→MVP), o que foi construído, porquê, e o valor de negócio. Usa diagramas
   (mermaid/graphviz ou imagens) e texto claro, sem jargão.

STACK
Python 3.11+, PyTorch, pandas/numpy/matplotlib, XGBoost, DuckDB, LangChain/
LangGraph, FastAPI (serve o modelo), Streamlit (UI). Docker + docker-compose.
Testes com pytest.

TREINO E DEPLOY (custo ~0)
- Treino do modelo: LOCAL, GPU (tenho RTX 5060) — nunca na cloud.
- Empacotar em Docker.
- Deploy: GCP Cloud Run (CPU, scale-to-zero, min-instances=0) → link público,
  ~0€ parado, e cobre o requisito de cloud da vaga. Configura um budget alert.
  (Streamlit Community Cloud como alternativa grátis se o Cloud Run complicar.)

COMO QUERO QUE TRABALHES
- Por fases pequenas e verificáveis. No fim de cada fase: o que foi feito, como
  testar, e o resultado REAL (métricas/outputs executados — NUNCA inventados).
- Explica o "porquê" das decisões (quero aprender) e comenta o código.
- Sem over-engineering: o mínimo que prova a competência. YAGNI.
- Primeiro mostra-me um PLANO por fases e espera o meu OK antes de codar.

PLANO SUGERIDO (confirma/ajusta antes de começar)
0. Scaffolding: repo, README, docker-compose, estrutura de pastas.
1. Ingestão M5 + EDA (gráficos) + features (calendário, lags, preços, promos).
2. Baselines (ingénuo + XGBoost) + métricas.
3. Modelo PyTorch (TFT/LSTM): treino local GPU + comparação vs baselines.
4. FastAPI a servir o modelo (previsão por SKU).
5. Copiloto LLM (LangGraph): explicação + NL→query + RAG.
6. Streamlit: demo interativo + secção de apresentação a stakeholders (diagramas).
7. Docker + deploy no GCP Cloud Run (link público) + budget alert.
8. README final: arquitetura, diagramas, resultados, e um mapa explícito de
   "cada peça → competência da vaga" (LLMs, ML, DL/PyTorch, LangChain, cloud).

ENTREGÁVEL FINAL
Repo limpo e reproduzível + link público Streamlit. README que mostra a
arquitetura, os resultados reais, a narrativa PoC→MVP, e como o projeto
demonstra cada requisito da vaga. Começa por me apresentar o plano da Fase 0–1
e pergunta antes de avançar.

https://www.net-empregos.com/15601784/ai-engineer/






