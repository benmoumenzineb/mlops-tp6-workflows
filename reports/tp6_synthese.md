# Orchestrateur ou integration continue ? (TP06)

| Critere | Prefect (orchestrateur) | GitHub Actions (CI) |
|---|---|---|
| Ce qui declenche l'execution | Planification (cron) ou bouton manuel | Un `git push` ou un bouton "Run workflow" |
| Ou s'execute le traitement | Sur ta machine (serveur Prefect local) | Sur les serveurs GitHub (Ubuntu) |
| Qui surveille, et ou | L'equipe sur http://127.0.0.1:4200 | Tout le monde sur l'onglet Actions de GitHub |
| Ce qui se passe en cas d'echec | La tache passe en rouge, l'equipe est notifiee dans l'interface | Le job est rouge, GitHub envoie un e-mail |
| Type de tache adapte | Traitements recurrents, planifies, longs | Verification rapide du code a chaque commit |
| Ce qui est versionne dans Git | Le code du flow (`flow_mlops.py`), `prefect.yaml` | Le fichier `.github/workflows/ci.yml`, `requirements-ci.txt` |

## Conclusion (5 lignes)
1. Prefect orchestre des workflows recurrents et planifies.
2. GitHub Actions verifie le code a chaque modification (CI).
3. Les deux sont complementaires, aucun ne remplace l'autre.
4. Prefect est ideal pour les taches longues et repetitives.
5. GitHub Actions est indispensable pour la qualite continue du code.