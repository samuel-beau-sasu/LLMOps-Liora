# Mémoire du projet LLMOps Liora

## Projet
- Projet LLMOps pédagogique situé sous `/home/ubuntu/LLMOps-setup-course`.
- Stack : FastAPI + LiteLLM + MLflow + Docker Compose.
- Providers : OpenAI, Gemini 2.0 Flash, Groq, OpenRouter.
- Routage avec fallback et autotraçage via MLflow + LiteLLM.

## Remotes
- Cible de push : `https://github.com/samuel-beau-sasu/LLMOps-Liora.git`
- Upstream original : `https://github.com/DataScientest/LLMOps-setup-course.git`

## Sécurité / points d'attention
- Fichier `.env` contient les clés API : il ne doit pas être commité.
- Debug verbeux présent dans `src/api/main.py` : risque d'exposition de prompts/réponses.
- Aucune authentification sur l'API FastAPI : non adapté pour une exposition directe en production.
- MLflow exposé sur un port HTTP sans restriction d'accès documentée.

## Fichiers utiles
- `/home/ubuntu/LLMOps-setup-course/src/api/main.py`
- `/home/ubuntu/LLMOps-setup-course/litellm/litellm-config.yaml`
- `/home/ubuntu/LLMOps-setup-course/docker-compose.yml`

## Tests / vérifications utiles
- `make setup`
- `make start`
- `make api-test`
- `make test`
- `python test_traces.py`
