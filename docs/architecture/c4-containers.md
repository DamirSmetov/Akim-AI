# C4 Model — Level 2: Container Diagram

## Overview

The following diagram describes the main technical components of Akim AI and their interactions.

```mermaid
flowchart TB
    Sources["External Data Sources"]

    subgraph AKIM["Akim AI Platform"]

        subgraph ING["Ingestion Layer"]
            Scrapers["Web Scrapers"]
            Connectors["API Connectors"]
        end

        subgraph LAKE["Data Lake - MinIO"]
            Bronze["Bronze Layer"]
            Silver["Silver Layer"]
        end

        subgraph PROCESSING["Processing Layer"]
            ETL["ETL / Data Validation"]
            ML["ML Classification"]
        end

        Gold["Gold Layer"]

        subgraph STORAGE["Storage Layer"]
            CH[("ClickHouse")]
            PG[("PostgreSQL")]
            QD[("Qdrant")]
        end

        subgraph AI["AI Layer"]
            RAG["RAG Pipeline"]
            LLM["Large Language Model"]
        end

        API["FastAPI Backend"]
        Dashboard["Web Dashboard"]
    end

    Sources --> Scrapers
    Sources --> Connectors

    Scrapers --> Bronze
    Connectors --> Bronze

    Bronze --> ETL
    ETL --> Silver
    Silver --> ML
    ML --> Gold

    Gold --> CH
    Gold -->|"Knowledge preparation"| RAG

    PG --> API
    CH --> API

    QD --> RAG
    RAG --> LLM
    LLM --> API

    API --> Dashboard
```

## Container Responsibilities

| Container | Responsibility |
|---|---|
| Web Scrapers | Extract publicly accessible information |
| API Connectors | Integrate external APIs |
| MinIO | Store raw and intermediate datasets |
| ETL Processing | Validate and transform information |
| ML Classification | Categorize urban problems |
| ClickHouse | Analytical data storage |
| PostgreSQL | Operational database |
| Qdrant | Vector search and semantic retrieval |
| RAG Pipeline | Retrieve relevant municipal knowledge |
| LLM | Generate contextual recommendations |
| FastAPI | Expose backend functionality |
| Web Dashboard | Provide user interaction |

Note: This represents the proposed logical architecture. Individual components may be implemented as separate services or modules depending on development requirements.
