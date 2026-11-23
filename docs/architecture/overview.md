# Akim AI — System Architecture Overview

## 1. Introduction

Akim AI is designed as a modular data intelligence platform that collects, processes, analyzes, and visualizes information about urban problems.

The initial deployment targets Almaty, Kazakhstan. However, the architecture is designed to support multiple cities through configurable data sources, geographical identifiers, and municipality-specific knowledge bases.

The platform combines Data Engineering, Machine Learning, Geospatial Analytics, and Retrieval-Augmented Generation (RAG).

## 2. High-Level Architecture

The system consists of five main architectural layers:

1. Data Ingestion Layer
2. Data Lake and Processing Layer
3. Machine Learning and Classification Layer
4. Analytical Storage Layer
5. Application and AI Layer

## 3. Data Ingestion Layer

This layer collects information from external sources.

Planned data sources include:

- Stat.gov.kz — official statistical information.
- Government Open APIs — public government and municipal datasets.
- Threads — publicly accessible discussions and reports.
- News Media — local news and information about urban issues.
- OpenStreetMap — geographical and infrastructure data.
- Additional public data sources.

Data is collected through API integrations, scheduled extraction jobs, and web parsers where permitted.

Each extracted record should contain source metadata, collection timestamps, and available geographical information.

## 4. Data Lake and Medallion Architecture

The platform uses a Medallion Architecture to organize data processing.

### Bronze Layer

Stores raw data collected from external sources.

Characteristics:
- Original source representation is preserved.
- Data is stored in formats such as JSON, CSV, and HTML.
- Source metadata and extraction timestamps are retained.
- Raw data can be reprocessed when transformation logic changes.

Storage: MinIO (S3-compatible object storage).

### Silver Layer

Contains cleaned, validated, and standardized data.

Processing operations include:
- Data cleaning.
- Schema validation.
- Deduplication.
- Data normalization.
- Geographical enrichment.
- Entity extraction.
- Data quality checks.

The objective is to transform heterogeneous source data into a consistent structure.

### Gold Layer

Contains enriched and analytics-ready information.

Processing operations include:
- ML-based classification.
- Problem categorization.
- Geographical grouping.
- Identification of recurring issues.
- Aggregation of related reports.
- Priority estimation.

Gold datasets are stored in ClickHouse for analytical queries and reporting.

## 5. Machine Learning Layer

Machine Learning models analyze structured records and identify urban problem categories.

Initial classification categories include:

- Road Infrastructure.
- Public Transportation.
- Education.
- Healthcare.
- Waste Management.
- Utilities.
- Environmental Issues.

The classification component can also extract relevant entities, identify geographical references, and estimate classification confidence.

Multiple reports referring to the same location and problem may be linked to identify recurring issues.

The system distinguishes between report frequency, classification confidence, and actual problem verification.

## 6. Analytical Storage

ClickHouse serves as the primary analytical database.

It stores structured information from the Gold Layer and supports:

- Analytical queries.
- Aggregations.
- Time-based analysis.
- Geographical statistics.
- Problem frequency analysis.
- Dashboard reporting.

PostgreSQL is used for operational information, application configuration, and user-related metadata.

MinIO remains the primary object storage for raw and intermediate datasets.

## 7. Geospatial Layer

OpenStreetMap provides geographical information about urban infrastructure and locations.

Geospatial data can be used to:
- Identify affected geographical areas.
- Associate reports with districts and locations.
- Visualize urban problems on maps.
- Analyze the distribution of recurring issues.

## 8. AI Assistant and RAG

The AI Assistant provides contextual recommendations based on available municipal information.

The RAG architecture consists of:

1. Document ingestion and preprocessing.
2. Text chunking.
3. Embedding generation.
4. Vector storage in Qdrant.
5. Semantic retrieval.
6. Context construction.
7. LLM-based response generation.

The knowledge base may contain:
- Municipal regulations.
- Urban planning documents.
- Infrastructure information.
- Public technical documentation.
- Relevant historical and statistical information.

The assistant retrieves relevant documents and combines them with structured analytical information from ClickHouse.

It can help municipal employees explore problems and identify possible approaches to addressing them.

AI-generated recommendations are advisory and require human verification.

## 9. Application Layer

The application layer exposes platform functionality through a backend API and a web dashboard.

Planned functionality includes:
- City selection.
- District selection.
- Urban problem visualization.
- Filtering by problem category.
- Statistical dashboards.
- Individual problem details.
- AI-powered recommendations.
- Access to supporting sources and evidence.

## 10. Orchestration

Apache Airflow is planned for scheduling and managing data workflows.

It will coordinate:
- Data extraction.
- Data validation.
- Data transformation.
- ML classification.
- Analytical database loading.
- Knowledge base updates.

## 11. Scalability and Extensibility

The platform follows a modular architecture.

Supporting additional cities should primarily require:
- Configuring new data sources.
- Adding geographical identifiers.
- Loading city-specific datasets.
- Creating or updating municipal knowledge bases.
- Configuring city-specific processing rules.

The core processing and application components should remain reusable.

## 12. Design Principles

The architecture follows these principles:

- Open-source technologies.
- Modular service design.
- Data quality and traceability.
- Separation of raw and processed data.
- Responsible AI usage.
- Privacy-conscious data processing.
- Platform independence.
- Extensibility across municipalities.
