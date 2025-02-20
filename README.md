# Template des projets sur la plateforme ANAIS

## Structure 
# Structure du projet `elt_project`

- **config/**
  - `config.json` – Configuration générale (chemins, SFTP, PostgreSQL, etc.)
  - `sftp_keys/` – Clés SSH pour le SFTP
  - `secrets.env` – Variables sensibles (ex: mot de passe DB)

- **data/**
  - `input/` – Fichiers source bruts (temporaire avant ingestion)
  - `decrypted/` – Fichiers après déchiffrement PGP
  - `output/` – Export des données finales avant envoi SFTP

- **dbt/**
  - **models/**
    - `staging/` – Transformation initiale des données (staging tables)
    - `marts/` – Modèles finaux (data marts)
    - `sources.yml` – Définition des sources
    - `dbt_project.yml` – Config principale DBT

- **modules/**
  - `ingestion.py` – Module d'ingestion avec DLT (SFTP -> PostgreSQL)
  - `decryption.py` – Module de déchiffrement PGP
  - `export.py` – Module d'export (PostgreSQL -> SFTP)

- **utils/**
  - `sftp_utils.py` – Fonctions de connexion SFTP
  - `db_utils.py` – Connexion et requêtes PostgreSQL
  - `logging_config.py` – Configuration des logs

- **logs/** – Logs de l'application

- **tests/** – Tests unitaires et d'intégration

- `main.py` – Script principal orchestrant les étapes ELT
- `requirements.txt` – Dépendances du projet
- `README.md` – Documentation du projet
- `.env` – Variables d'environnement
- `.gitignore` – Fichiers à ignorer (clés SSH, fichiers temporaires, etc.)


## Stack
- **CI CD** : Github
- **Gestion des environnements virtuels** : Pyenv
    - Pyenv nous permet de spécifier la version de Python à utiliser
- **Gestion des dépendances** : Poetry
- **Ingestion** : DLT
- **Transformation** : DBT
