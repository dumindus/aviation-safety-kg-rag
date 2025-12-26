# KG-based RAG for Querying Aviation Safety Data | Phase 01
This repository contains Phase 01 of the Knowledge Graph-based Retrieval-Augmented Generation (RAG) system. The project focuses on preprocessing real-world National Transportation Safety Board (NTSB) aviation accident data to prepare it for ingestion into a Neo4j Graph Database.

# 🎯 Project Overview
The goal of this phase is to transform raw aviation datasets (Accidents, Aircraft, Engines) into structured Nodes and Relationships. This structure allows for complex semantic queries that traditional vector databases struggle with, such as "Find all engine failures in CESSNA aircraft occurring in high-altitude regions."

# 🛠️ Technical Stack
* Language: Python 3.x
* Data Processing: `Pandas`, `NumPy`
* Entity Extraction: `Spacy`, `SentenceTransformer`
* Graph Preparation: Cypher (Neo4j), APOC
* Environment: Google Colab / Jupyter Notebook

# 🚀 Data Pipeline
The current script (phase_01.py) performs the following operations:
1. Data Ingestion: Loads NTSB event and aircraft data from CSV/Excel.
2. Standardization: Cleans column headers, parses dates, and handles missing values.
3. Feature Engineering: Extracts temporal features (year, month, day of week) and geographic markers.
4. Graph Transformation: Generates a unique entity_id for every accident and manufacturer. Creates separate CSV files for nodes.csv and relationships.csv.
5. Cypher Scripting: Automatically generates a neo4j_import.cypher script to automate the loading process into a Neo4j instance.

⚠️ Note: If you plan to run the resulting Cypher script, you will need a Neo4j instance with the APOC plugin enabled.
For this RAG, in phase 02, we are using a Neo4J Aura instance.

