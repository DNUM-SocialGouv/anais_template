# Template des projets sur la plateforme ANAIS

## Structure 
# Structure du projet `elt_project`

project-root/
├── ingestion/
│   ├── pipelines/
│   │   ├── __init__.py
│   │   └── dlt_pipeline.py        # Main DLT ingestion script(s)
│   ├── config/
│   │   ├── base_config.yaml       # Common config parameters
│   │   ├── local.yaml             # Local (DuckDB/Parquet) settings
│   │   ├── onprem.yaml            # On-prem deployment settings
│   │   └── saagie.yaml            # Saagie deployment settings
│   ├── utils/
│   │   └── logger.py              # Shared utilities (e.g., logging)
│   └── tests/
│       └── test_dlt_pipeline.py   # Unit tests for ingestion
│
├── transformations/
│   ├── dbt_project/               # Standard dbt project directory
│   │   ├── models/
│   │   │   └── example_model.sql  # Example SQL transformation model
│   │   ├── dbt_project.yml        # dbt project configuration
│   │   └── profiles.yml           # dbt profiles (can be templated)
│   └── tests/
│       └── test_dbt_models.sql    # Tests to validate transformations
│
├── local_env/                     # Local environment artifacts
│   ├── duckdb/                    # DuckDB-specific files/configs
│   └── parquet/                   # Sample parquet files for testing
│
├── deployment/                    # Deployment scripts & configs
│   ├── onprem/
│   │   ├── deploy.sh              # On-prem deployment script
│   │   └── config_onprem.yaml     # On-prem specific settings
│   ├── saagie/
│   │   ├── deploy.sh              # Saagie deployment script
│   │   └── config_saagie.yaml     # Saagie-specific settings
│   └── Dockerfile                 # (Optional) Containerization if needed
│
├── .github/
│   └── workflows/                 # CI/CD pipeline definitions for GitHub Actions
│       ├── ci.yml               # Continuous integration jobs
│       └── cd.yml               # Continuous deployment jobs
│
├── pyproject.toml                 # Poetry dependency and project configuration
├── poetry.lock                    # Locked dependencies
└── README.md                      # Project overview and documentation



## Stack
- **CI CD** : Github
- **Gestion des environnements virtuels** : Pyenv
    - Pyenv nous permet de spécifier la version de Python à utiliser
- **Gestion des dépendances** : Poetry
- **Ingestion** : DLT
- **Transformation** : DBT
