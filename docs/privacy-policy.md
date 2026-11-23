# Akim AI — Privacy Policy

## 1. Introduction

Akim AI is designed to analyze publicly available information about urban problems and support municipal decision-making.

The platform follows privacy-conscious data processing principles and aims to minimize the collection and storage of personal information.

## 2. Data Sources

The platform may process information from:

- Public government datasets.
- Open government APIs.
- Public social media content.
- News media.
- OpenStreetMap.
- Other publicly accessible sources.

## 3. Data Minimization

Akim AI aims to collect only information necessary for identifying and analyzing urban problems.

Personal identifiers that are not required for analytical purposes should be excluded or anonymized where possible.

## 4. Data Storage

Different categories of information are stored in separate infrastructure components:

- MinIO: raw and processed datasets.
- ClickHouse: analytical datasets.
- PostgreSQL: operational application information.
- Qdrant: vector representations of relevant documents.

Access to sensitive information should be restricted.

## 5. Data Security

The platform intends to implement:

- Access control.
- Secure API communication.
- Secret management.
- Data anonymization.
- Appropriate retention policies.
- Protection against unauthorized access.

## 6. AI and Automated Processing

Machine learning models and LLMs are used to classify information and generate recommendations.

AI-generated outputs are advisory and should not be treated as verified facts or final administrative decisions.

## 7. Data Retention

Data retention periods should depend on the source, purpose of processing, and applicable legal requirements.

## 8. Transparency

The project aims to document its data sources, processing methods, and privacy-related practices.

## 9. Current Status

This document describes the intended privacy principles and planned safeguards.

Actual processing practices will be documented and updated as the platform develops.
