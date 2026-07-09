# Démarrer Hermes

## Step 2: Set Your API Key

hermes config set OPENROUTER_API_KEY <YOUR_API_KEY>

## Step 3: Configure Your Model

hermes chat --provider openrouter --model 'google/gemma-4-31b-it:free'
hermes chat --provider openrouter --model 'google/gemma-4-31b-it'
hermes chat --provider openrouter --model 'z-ai/glm-5.2'



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

54.78.248.179:5001
54.78.248.179:8000
54.78.248.179:8001

curl -X POST http://localhost:8000/generate -H "Content-Type: application/json" -d '{"model": "groq", "prompt": "Décrire le LLMOps en une phrase."}'


#
docker-compose up -d --build
docker-compose down

# Chap 2

git checkout chap2-multi-LLM

Le paramètre --force-recreate pour force la reconstruction des services.
docker-compose up --build -d --force-recreate

curl -X POST http://localhost:8000/generate \
  -H "Content-Type: application/json" \
  -d '{
    "model": "groq",
    "prompt": "Décrire le LLMOps en une phrase.",
    "system_prompt": "Tu es un expert en DevOps et MLOps. Réponds toujours de manière très technique et précise, en utilisant le jargon professionnel."
  }'

  {
  "response": "LLMOps est la discipline MLOps spécialisée dans le pipeline complet de cycle de vie des grands modèles linguistiques, orchestrant l'entraînement distribué sur GPU/TPU, le registry de checkpoints versionnés, le fine-tuning PEFT/LoRA via pipelines CI/CD as-code, le déploiement sur clusters Kubernetes avec autoscaler GPU, le serving haute-débit via TensorRT-LLM ou vLLM, la surveillance des métriques de génération (perplexité, latency, TPS), la gestion des prompts et des embeddings dans des vectordb opérés, la garde-fou de sécurité",
  "model": "moonshotai/kimi-k2-instruct",
  "prompt_tokens": 57,
  "completion_tokens": 150,
  "total_tokens": 207,
  "cost": 0.0
}

curl -X POST http://localhost:8000/generate \
  -H "Content-Type: application/json" \
  -d '{
    "model": "groq",
    "prompt": "Quels sont les avantages du LLMOps ?",
    "system_prompt": "Réponds toujours sous forme de liste à puces avec exactement 3 points. Chaque point doit commencer par un emoji."
  }'

 {"response":"LLMOps est une solution basée sur l'intelligence artificielle qui offre de nombreux avantages dans divers domaines. Voici quelques-uns des principaux avantages du LLMOps :\n\n1. 
 **Amélioration de l'efficacité opérationnelle** : LLMOps permet d'automatiser et d'optimiser les processus opérationnels, ce qui conduit à une augmentation de la productivité et à une réduction des coûts.\n\n2. 
 **Prise de décision basée sur les données** : Grâce à l'analyse avancée des données et à l'apprentissage automatique, LLMOps fournit des informations précieuses pour prendre des décisions éclairées.\n\n3. 
 **Gestion des risques** : LLMOps peut aider à identifier et à atténuer les risques potentiels en analysant les","model":"groq","prompt_tokens":19,"completion_tokens":150,"total_tokens":169,"cost":0.0}ubuntu@ip-172-31-28-100:~/LLMOps-setup-course$ 