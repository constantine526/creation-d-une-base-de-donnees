# SAE S104 – Base de données Climate-Related Disaster Frequency

## Présentation
Ce projet consiste à créer une base de données SQL sur la fréquence des catastrophes climatiques par pays et par année.  
L’objectif est de mettre en pratique les concepts fondamentaux de la modélisation et gestion de bases de données relationnelles.

## Fonctionnalités
- Création des tables : `region`, `sub_region`, `country`, `disaster`, `climate_disaster`
- Gestion des clés primaires et étrangères, y compris les clés composites
- Peuplement des tables à partir d’un fichier CSV
- Scripts SQL disponibles pour création manuelle ou génération automatique via AGL (pgModeler)

## Organisation du projet
- Scripts SQL manuels : `scripts/sql_manual/`
- Scripts générés par AGL : `scripts/sql_agl/`
- Fichier CSV source pour le peuplement : `data/climate_disasters.csv`

## Outils utilisés
- PostgreSQL pour la base de données
- pgModeler pour la génération de scripts SQL via AGL
- Terminal Linux pour l’exécution des scripts SQL

## Instructions pour lancer
Ouvrir un terminal dans le dossier du projet et exécuter les commandes suivantes :

```bash
# Créer la base de données
psql -c "CREATE DATABASE climate_disasters;"

# Exécuter le script SQL pour créer les tables (manuel ou AGL)
psql -d climate_disasters -f scripts/sql_manual/create_tables.sql

# Importer les données CSV dans la table temporaire
psql -d climate_disasters -c "\copy temporaire FROM 'data/climate_disasters.csv' CSV HEADER;"

# Vérifier que les tables sont correctement remplies
psql -d climate_disasters -c "SELECT * FROM region;"
psql -d climate_disasters -c "SELECT * FROM sub_region;"
psql -d climate_disasters -c "SELECT * FROM country;"
psql -d climate_disasters -c "SELECT * FROM disaster;"
psql -d climate_disasters -c "SELECT * FROM climate_disaster;"
Ce travail a été réalisé de manière autonome et individuelle.
