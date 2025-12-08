## n8n docker compose quickstart

This project includes `n8n-compose.yaml` to run n8n via Docker Compose.

### Prerequisites
- Docker Desktop (or Docker Engine) running.
- The external volume `n8n_data` must exist.

### One-time setup
1) Create the external volume:
```
docker volume create n8n_data
```
2) Optional: adjust the host download path. By default the compose file mounts `/Users/flamurmaliqi/Downloads` into the container at `/downloads`. Set `HOST_DOWNLOADS` in a `.env` file (same folder) to override, e.g.:
```
HOST_DOWNLOADS=/Users/yourname/Downloads
```

### Start n8n
```
docker compose -f /Users/flamurmaliqi/git/BlauTech/BlauTechn8N/n8n-compose.yaml up -d
```
This runs the `n8nio/n8n:latest` image and exposes the UI at http://localhost:5678.

### Check logs
```
docker compose -f /Users/flamurmaliqi/git/BlauTech/BlauTechn8N/n8n-compose.yaml logs -f n8n
```

### Stop the stack
```
docker compose -f /Users/flamurmaliqi/git/BlauTech/BlauTechn8N/n8n-compose.yaml down
```


