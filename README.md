# Athul Sasidharan

**Data analyst and data scientist in Vancouver.** UBC Master of Data Science (2026), with three years across banking data engineering, consulting and clinical analytics.

I'm best where the data is messy, the deadline is real, and somebody needs an answer they can defend afterwards.

[Portfolio](https://codingwithathul.github.io) · [CV (PDF)](https://codingwithathul.github.io/assets/Athul_Sasidharan_Resume.pdf) · [LinkedIn](https://www.linkedin.com/in/athul-sasidharan-48a1ba195/) · [Email](mailto:athulchira@gmail.com)

> Open to data analyst, business analyst and data science roles across Canada.

**Ask me about**

- Grounding LLM answers in evidence, and scoring how far to trust them
- Evaluating a retrieval system instead of eyeballing it
- Taking a model from a notebook to a live endpoint
- Building pipelines where a wrong number is a regulatory problem

---

## Selected work

### 1. CodeIQ: ask a 100K-line codebase questions in plain English

<a href="https://codeiq-source-code-knowledge-graph-latest.onrender.com/">
  <img src="https://github.com/goudmani/codeiq_source_code_knowledge_graph/raw/main/img/demo.gif" width="640" alt="Demo of CodeIQ answering a plain-English question about a React Native codebase, with cited file paths">
</a>

- **Problem.** Every unfamiliar codebase starts with hours of "who calls this?"
- **Approach.** Parses Bluesky's React Native app (about 100K lines) into a knowledge graph of 3,820 entities plus a vector index. An LLM agent with graph-traversal tools answers in plain English and cites the files it used. Confidence is scored from retrieval relevance, not self-reported by the model.
- **Result.** 28 of 30 evaluation questions answered with the expected source cited, zero errors, with token-cost and run-to-run reliability reports published alongside.

![ts-morph](https://img.shields.io/badge/ts--morph-3178C6?style=flat-square&logo=typescript&logoColor=white) ![NetworkX](https://img.shields.io/badge/NetworkX-555555?style=flat-square) ![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6446?style=flat-square) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white) ![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square) ![Shiny](https://img.shields.io/badge/Shiny-75AADB?style=flat-square) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

**[Live app](https://codeiq-source-code-knowledge-graph-latest.onrender.com/)** · **[Code](https://github.com/goudmani/codeiq_source_code_knowledge_graph)** · **[Evaluation write-up](https://github.com/goudmani/codeiq_source_code_knowledge_graph#evaluation-cost--reliability-testing)**

### 2. Vancouver Parks Dashboard: find a park by what you actually need

<a href="https://019c91e8-5952-d69b-140e-530221568f2d.share.connect.posit.cloud/">
  <img src="https://github.com/UBC-MDS/DSCI-532_2026_3_vancouver_park_dashboard/raw/main/img/demo.gif" width="640" alt="Demo of the Vancouver Parks Dashboard filtering parks by neighbourhood, size and facilities on a map">
</a>

- **Problem.** Vancouver publishes its parks as open data, but picking one by the facilities you need means scanning a spreadsheet.
- **Approach.** A public dashboard over the City of Vancouver parks dataset: filter by neighbourhood, size and facilities and see the results on a map, or describe what you want on the AI search tab, which maps free text onto real neighbourhood names.
- **Result.** Deployed publicly on Posit Connect Cloud. The filter logic is unit-tested, including that combined filters intersect and that size limits are inclusive.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Shiny](https://img.shields.io/badge/Shiny-75AADB?style=flat-square) ![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white) ![Folium](https://img.shields.io/badge/Folium-77B829?style=flat-square) ![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)

**[Live app](https://019c91e8-5952-d69b-140e-530221568f2d.share.connect.posit.cloud/)** · **[Code](https://github.com/UBC-MDS/DSCI-532_2026_3_vancouver_park_dashboard)**

### 3. Smart product review search: answers that cite their sources

- **Problem.** Thousands of product reviews hold the answers to buying questions, and nobody can read them all.
- **Approach.** Hybrid retrieval over 15,972 cleaned Amazon software reviews: BM25 keyword search and MiniLM embeddings in FAISS, fused with reciprocal rank fusion. A Groq-hosted Llama 3.3 70B answers from the retrieved reviews and cites the ones it used.
- **Result.** Benchmarked Qwen3 32B (about 38% faster) against Llama 3.3 70B and kept the slower model, because it hedged honestly when retrieval came back thin instead of over-committing.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![BM25](https://img.shields.io/badge/BM25-555555?style=flat-square) ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square) ![RAG](https://img.shields.io/badge/RAG-6E40C9?style=flat-square) ![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

**[Code](https://github.com/codingwithAthul/Information_Rag_Retrieval_Project)**

### 4. Rainfall prediction API: a model that answers requests

- **Problem.** A trained model sitting in a `.joblib` file has not helped anyone yet.
- **Approach.** A random forest (100 trees) trained on an AWS EMR/Spark cluster, then served through FastAPI on a 1 GB EC2 `t3a.micro`. The model loads once at startup rather than per request, and Pydantic validates every 25-feature payload before it reaches the model.
- **Result.** Deployed and tested end to end with `curl`, and cross-tested against a classmate's endpoint.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)

**[Code](https://github.com/codingwithAthul/rainfall-prediction-aws-deployment)**

### 5. geospatial-toolkit: a tested, documented Python package

- **Problem.** The same coordinate and distance helpers get rewritten by hand in every project.
- **Approach.** A lightweight package with four functions: `standardize_latlong`, `haversine_distance`, `point_to_city` (point-in-polygon city lookup) and `get_antipode` (with optional reverse geocoding).
- **Result.** Version 3.0.0 on TestPyPI, with a pytest suite and a documentation site.

```bash
pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple/ geospatial-toolkit
```

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![GeoPandas](https://img.shields.io/badge/GeoPandas-139C5A?style=flat-square) ![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white) ![Quarto](https://img.shields.io/badge/Quarto-39729E?style=flat-square&logo=quarto&logoColor=white)

**[Docs](https://ubc-mds.github.io/geospatial-toolkit/)** · **[Code](https://github.com/UBC-MDS/geospatial-toolkit)**

---

## Tools

| Area | Stack |
| --- | --- |
| Languages and querying | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![R](https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square) ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-F80000?style=flat-square&logo=oracle&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white) |
| Analysis and modelling | ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white) ![Causal inference](https://img.shields.io/badge/Causal_inference-555555?style=flat-square) ![Experiment design](https://img.shields.io/badge/Experiment_design-555555?style=flat-square) |
| LLM and retrieval | ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white) ![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6446?style=flat-square) ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square) ![BM25](https://img.shields.io/badge/BM25-555555?style=flat-square) ![RAG](https://img.shields.io/badge/RAG-6E40C9?style=flat-square) ![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![Groq](https://img.shields.io/badge/Groq-F55036?style=flat-square) |
| Pipelines and databases | ![Informatica](https://img.shields.io/badge/Informatica-FF4D00?style=flat-square) ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) ![Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) |
| Reporting and delivery | ![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black) ![Shiny](https://img.shields.io/badge/Shiny-75AADB?style=flat-square) ![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white) ![Quarto](https://img.shields.io/badge/Quarto-39729E?style=flat-square&logo=quarto&logoColor=white) ![ggplot2](https://img.shields.io/badge/ggplot2-1E5B8C?style=flat-square) |
| Workflow | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) ![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white) |

---

## Experience

**BC Children's Hospital: Capstone Data Analyst** · Apr to Jun 2026

Built R and Shiny pipelines and a dashboard to validate the hospital's move from paper to electronic lab testing, quantifying the reduction in errors for stakeholders.

![R](https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white) ![Shiny](https://img.shields.io/badge/Shiny-75AADB?style=flat-square) ![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) ![ggplot2](https://img.shields.io/badge/ggplot2-1E5B8C?style=flat-square) ![Quarto](https://img.shields.io/badge/Quarto-39729E?style=flat-square&logo=quarto&logoColor=white)

**Axis Bank: Data Engineer (Deputy Manager)** · Jul 2022 to Feb 2024

Built Oracle, PL/SQL and Informatica pipelines serving 5+ reporting teams under banking regulation, owned unit testing and production releases in Blaze/TRAID, and wrote the documentation standard the team adopted.

![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-F80000?style=flat-square&logo=oracle&logoColor=white) ![Informatica](https://img.shields.io/badge/Informatica-FF4D00?style=flat-square) ![Blaze/TRAID](https://img.shields.io/badge/Blaze%2FTRAID-555555?style=flat-square)

**Agies Safety Solutions: Business Consultant (part-time)** · May 2020 to Apr 2022

Used statistical modelling to design a new product sales model that drove 5x revenue growth, and automated finance reporting to save up to 30% of annual operational turnover.

![Statistical modeling](https://img.shields.io/badge/Statistical_modeling-555555?style=flat-square) ![Workflow automation](https://img.shields.io/badge/Workflow_automation-555555?style=flat-square) ![Automated reporting](https://img.shields.io/badge/Automated_reporting-555555?style=flat-square) ![Market research](https://img.shields.io/badge/Market_research-555555?style=flat-square)

**Education:** UBC Master of Data Science (2026) · BCIT Graduate Certificate in Global Leadership, Distinction (2025) · NIT Tiruchirappalli B.Tech Mechanical Engineering, First Class Honours (2022)

---

[Portfolio](https://codingwithathul.github.io) · [CV (PDF)](https://codingwithathul.github.io/assets/Athul_Sasidharan_Resume.pdf) · [LinkedIn](https://www.linkedin.com/in/athul-sasidharan-48a1ba195/) · [Email](mailto:athulchira@gmail.com)
