# Akim AI
### Open-Source Municipal Data Intelligence Platform

Akim AI is an open-source platform designed to help municipal authorities identify, analyze, and prioritize urban problems using Data Engineering, Machine Learning, and Large Language Models (LLMs).

The initial implementation focuses on Almaty, Kazakhstan, with an architecture designed to support other cities and municipalities in the future.

## Problem Statement

Urban authorities receive information about city problems from numerous disconnected sources, including public complaints, social media, news outlets, government statistics, and municipal datasets.

However, this information is often fragmented, unstructured, and difficult to analyze collectively.

As a result, identifying recurring problems, understanding their geographical distribution, and prioritizing potential solutions can be challenging.

Akim AI aims to address this problem by transforming fragmented public information into structured, actionable insights.

## Key Features

- **Multi-Source Data Collection:** Aggregation of information from government datasets, public APIs, news media, social media platforms, and open geographical sources.
- **Automated Data Processing:** Data validation, cleaning, normalization, and deduplication using an automated ETL/ELT pipeline.
- **AI-Powered Classification:** Machine learning models classify reported problems into categories such as road infrastructure, education, healthcare, public transportation, and waste management.
- **Problem Prioritization:** Identification of recurring problems based on the number of independent reports, geographical distribution, and available supporting evidence.
- **Geospatial Analytics:** Visualization of urban problems using geographical information and OpenStreetMap data.
- **RAG-Based AI Assistant:** An intelligent assistant that retrieves relevant municipal information and provides contextual recommendations.
- **Municipal Analytics Dashboard:** A centralized interface for exploring urban problems, monitoring statistics, and supporting data-driven decision-making.

## Data Sources

The platform is designed to integrate information from multiple publicly available sources:

| Source | Purpose |
|---|---|
| Stat.gov.kz | Official statistical data |
| Government Open APIs | Public government and municipal datasets |
| Threads | Public discussions and reports about urban problems |
| News Media | Information about local events and infrastructure issues |
| OpenStreetMap | Geographical data and urban infrastructure mapping |
| Other Public Sources | Additional municipal and publicly available datasets |

Data availability and collection methods depend on the terms of service, API access conditions, and applicable legislation.

## System Architecture

Akim AI follows a modular architecture based on the Medallion Data Architecture.

The main data processing stages include:

1. **Data Ingestion:** Collection of information from external sources through API integrations and web parsers.
2. **Bronze Layer:** Storage of raw, unmodified source data.
3. **Silver Layer:** Data cleaning, validation, normalization, and deduplication.
4. **ML Classification:** Identification and categorization of urban problems.
5. **Gold Layer:** Storage of structured, enriched, and analytics-ready datasets.
6. **AI Assistant:** Retrieval of relevant municipal knowledge and generation of contextual recommendations.

The platform combines analytical data storage with a vector database to support both structured analytics and Retrieval-Augmented Generation (RAG).

See [Architecture Documentation](docs/architecture/overview.md).

## Technology Stack

The proposed technology stack includes:

| Component | Technology |
|---|---|
| Backend | Python, FastAPI |
| Data Ingestion | Python, Scrapy, API Connectors |
| Data Processing | Python, Polars |
| Data Orchestration | Apache Airflow |
| Object Storage | MinIO (S3-compatible) |
| Analytical Database | ClickHouse |
| Operational Database | PostgreSQL |
| Vector Database | Qdrant |
| Machine Learning | Scikit-learn, Hugging Face |
| AI Integration | LLM, RAG |
| Geospatial Data | OpenStreetMap |
| Containerization | Docker |

The technology stack is subject to change during development.

## Project Goals

- Improve the accessibility and usability of public urban information.
- Help identify recurring municipal problems.
- Support more informed and transparent decision-making.
- Encourage the use of open data and open-source technologies.
- Provide a reusable architecture that can be adapted to different cities.

## Digital Public Goods Alignment

Akim AI aims to support the United Nations Sustainable Development Goals:

- **SDG 11:** Sustainable Cities and Communities.
- **SDG 16:** Peace, Justice and Strong Institutions.
- **SDG 9:** Industry, Innovation and Infrastructure.

The project is designed around open-source development, transparency, responsible data processing, and public benefit.

## Project Status

Akim AI is currently in the planning and early development stage.

The architecture, technology stack, and documentation are being established. Individual components will be implemented incrementally.

## Contributing

Contributions are welcome!

Developers can participate in improving data ingestion, processing pipelines, machine learning models, backend services, documentation, and other components.

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## License

This project is intended to be distributed under the Apache License 2.0.

See the [LICENSE](LICENSE) file for details.

---

**Akim AI — Turning public data into actionable insights for better cities.**
