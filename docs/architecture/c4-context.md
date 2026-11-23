# C4 Model — Level 1: System Context

## Overview

This diagram illustrates the relationship between Akim AI, its external data sources, and its primary users.

```mermaid
flowchart TB
    Citizen["Citizens and Public Information Sources"]
    Government["Municipal Authorities"]
    Admin["Platform Administrators"]

    subgraph External["External Data Sources"]
        Statistics["Stat.gov.kz"]
        APIs["Government Open APIs"]
        Threads["Threads"]
        News["News Media"]
        OSM["OpenStreetMap"]
    end

    Akim["Akim AI Platform"]

    Government -->|"Explore urban problems"| Akim
    Admin -->|"Manage platform"| Akim

    Statistics -->|"Statistical data"| Akim
    APIs -->|"Municipal datasets"| Akim
    Threads -->|"Public discussions"| Akim
    News -->|"News information"| Akim
    OSM -->|"Geospatial data"| Akim
    Citizen -->|"Publicly available reports"| Akim
```

## Primary Actors

### Municipal Authorities

Use the platform to explore recurring urban problems, analyze their geographical distribution, and receive AI-generated recommendations.

### Platform Administrators

Manage data sources, platform configuration, and system operations.

### External Data Sources

Provide statistical, geographical, governmental, and publicly available information for analysis.
```
