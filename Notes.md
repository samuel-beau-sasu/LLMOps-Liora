# Récupération du repository de formation
git clone https://github.com/DataScientest/LLMOps-setup-course.git

cd LLMOps-setup-course

# initialiser l'environnement avec UV
sudo snap install astral-uv --classic

# synchroniser pour installer les librairies
uv sync

# Configuration de votre clé API
cp .env.template .env

# choix du model 

#Bash
hermes model google/gemma-4-31b-it:free

#dans une session Hermes 
/model google/gemma-4-31b-it:free
/model google/step-3.7-flash:free

# Liste des models
step-3.7-flash:free
google/gemma-4-31b-it:free
qwen/qwen3-coder:free
nvidia/nemotron-3-ultra-550b-a55b:free
nousresearch/hermes-3-llama-3.1-405b:free
openai/gpt-oss-120b:free
z-ai/glm-4.5-air:free

# en utilisant uv (en restant à la racine du repository)
uv run src/groq_simple_completion.py


ubuntu@ip-172-31-28-100:~/LLMOps-setup-course/litellm$ docker-compose up -d --build


curl http://3.253.82.27:5000/health

# Vérification que tous les services sont opérationnels
curl http://localhost:8000/docs  # FastAPI
curl http://localhost:8001/health  # LiteLLM
curl http://localhost:5001         # MLflow