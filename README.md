# FastAPI EC2 CI/CD Demo

API dimostrativa per pipeline CI/CD con Docker, GitHub Actions e deploy su EC2 Ubuntu tramite SSH.

## Endpoint disponibili

- `GET /` - messaggio generale
- `GET /courses` - elenco corsi
- `GET /courses/{course_id}` - dettaglio corso
- `GET /health` - stato del servizio
- `GET /docs` - documentazione automatica Swagger

## Avvio locale

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

## Avvio con Docker Compose

```bash
docker compose up -d --build
```

## Deploy

Ogni push sul branch `main` attiva automaticamente la pipeline GitHub Actions, che builda l'immagine Docker e la distribuisce sulla EC2 tramite SSH.
