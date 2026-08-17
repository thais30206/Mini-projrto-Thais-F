# Pipeline de Sanitização e ETL de Dados - Olist (E-commerce)

Este repositório contém o Mini-Projeto Avaliativo do **Módulo 1 (Semana 07)** do curso de **Machine Learning e Visão Computacional [T3] - SCTEC / FIESC**.

## 📌 Descrição do Projeto
O projeto consiste em um pipeline de Engenharia de Dados voltado para o tratamento, padronização e validação de regras de negócio em bases transacionais da Olist (`olist_products_dataset.csv` e `olist_orders_dataset.csv`).

O desenvolvimento foi realizado estritamente com a biblioteca padrão do Python (`csv`, `re`, `datetime`, `urllib`), demonstrando o domínio da manipulação nativa de dados sem dependência de bibliotecas de terceiros (como Pandas).

### Principais Etapas Executadas:
- **Ingestão Nativa:** Leitura estruturada dos arquivos CSV utilizando `csv.DictReader`.
- **Tratamento de Nulos e Dimensões:** Preenchimento de categorias vazias com a string `"sem categoria"` e descarte fundamentado de registros sem dimensões físicas essenciais para cálculo logístico.
- **Padronização de Strings e Regex:** Aplicação de `.lower()`, `.strip()` e expressões regulares (`re.sub`) para remover pontuações e caracteres especiais dos nomes de categorias.
- **Validação de Regra de Negócio:** Análise empírica e refutação da hipótese de que datas de entrega nulas pertencem exclusivamente a pedidos com status `canceled`.
- **Formatação Temporal:** Conversão de strings de data (`order_approved_at`) do padrão ISO/banco de dados para o padrão simplificado brasileiro (`DD/MM/YYYY`) com o módulo nativo `datetime`.
- **Relatório Manual:** Exibição de sumário estatístico consolidado validando o volume de dados processados e registros corrigidos.

---

Reflexão Teórica: Qualidade de Dados e Machine Learning
A integridade dos dados na etapa de pré-processamento (ETL) é o alicerce fundamental para a construção de qualquer modelo de Inteligência Artificial. O clássico axioma Garbage In, Garbage Out estabelece que arquiteturas complexas de Machine Learning falharão em capturar padrões reais se forem alimentadas com variáveis corrompidas, nulas ou ruidosas. A ausência de tratamento em valores faltantes e a falta de padronização textual introduzem distribuições artificiais no espaço vetorial, fazendo com que o algoritmo aprenda ruídos irrelevantes em vez da verdadeira representação do domínio do problema.

Além disso, inconsistências não tratadas são vetores diretos para o surgimento de viés algorítmico (bias) e sobreajuste (overfitting). Quando registros incompletos são ignorados sem critérios técnicos ou imputados de maneira equivocada, o modelo memoriza anomalias do conjunto de treino que não se generalizam para dados em produção. A sanitização determinística dos metadatos assegura a estabilidade estatística necessária para que futuros modelos preditivos ou sistemas de visão computacional alcancem alta acurácia e capacidade real de generalização.
