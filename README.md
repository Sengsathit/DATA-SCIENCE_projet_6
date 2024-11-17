![Implémentation d'un modèle de scoring](https://raw.githubusercontent.com/Sengsathit/OCR_data_scientist_assets/main/header_pret_a_depenser.png)

# PROJET : Implémentation d'un modèle de scoring

Pour ce projet nous considérons l’entreprise **Prêt à dépenser**, une société financière spécialisée dans les crédits à la consommation pour des personnes ayant peu ou pas d’historique de prêt. L’entreprise souhaite développer un modèle de scoring crédit afin d’évaluer la probabilité de remboursement des clients. Ce modèle permettra d’automatiser la décision d’accord ou de refus des crédits tout en tenant compte de la transparence des décisions pour les utilisateurs internes.

## Objectifs

1. Élaborer un modèle de scoring :
- Construire un modèle de classification pour prédire la probabilité de défaut d’un client.
- Optimiser le modèle en fonction d’un score métier qui pondère les faux positifs et les faux négatifs selon leur coût financier respectif.
2. Intégrer une démarche MLOps :
- Suivre le cycle de vie du modèle avec des outils comme MLFlow (tracking des expérimentations, enregistrement des modèles, serving).
- Automatiser les déploiements via GitHub Actions et gérer les versions de code.
3. Assurer la maintenance et la surveillance du modèle :
- Détecter les dérives de données (data drift) en production à l’aide de la librairie evidently.
- Tester la robustesse du modèle en comparant les distributions des données d’entraînement et des données de production.
4. Déployer une API et une interface utilisateur :
- Développer une API avec FastAPI ou Flask pour exposer le modèle en production.
- Créer une interface interactive avec Streamlit pour tester l’API et simuler des scénarios de scoring client.

## Structure du dépôt

```bash
DATA-SCIENCE_projet_6/
│
├── 1_notebook_data_preparation.ipynb           # Notebook pour l'analyse exploratoire et le feature engineering
├── 2_notebook_modelisation.ipynb               # Notebook pour la modélisation et la sélection du meilleur modèle
├── 3_dossier_code/                             # Dossier relatif à l'API de scoring et au dashboard
│    ├── data/                                  # Dossier pour les datasets
│    │    └── df_train_domain.csv.zip           # Dataset pour simuler et évaluer un client par le modèle
│    ├── scripts/                               # Dossier des scripts de déploiement de l'API et du dashboard
│    │    ├── api.py                            # Script de l'API (Flask)
│    │    ├── dashboard.py                      # Script du dashboard (Streamlit)
│    │    ├── run_api.sh                        # Script bash pour exécuter une instance de l'API sur le serveur
│    │    └── run_dashboard.py                  # Script bash pour exécuter une instance du dashboard sur le serveur
│    ├── tools/                                 # Dossier contenant divers outils de manipulation de données
│    │    ├── imputer.pkl                       # Imputer pour que les données de production soient ISO aux données d'entraînement
│    │    └── scaler.pkl                        # Scaler pour que les données de production soient ISO aux données d'entraînement
│    └── unit_tests/                            # Dossier des tests unitaires
│         └── unit_tests_api.py                 # Tests unitaires de l'API
├── 4_Tableau_HTML_data_drift_evidently.html    # Fichier de présentation des résultats de l'analyse du Data Drift
├── requirements.txt                            # Fichier des dépendances
└── README.md                                   # Ce fichier
```