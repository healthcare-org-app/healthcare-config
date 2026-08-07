# config-service

config-service — domain: identity

- **Port:** 8005
- **Language:** Python 3.11 + Flask
- **Database:** `identity` (Postgres, table `config`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/config/`          |
| POST      | `/api/config/`          |
| GET       | `/api/config/<id>`      |
| PUT/PATCH | `/api/config/<id>`      |
| DELETE    | `/api/config/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `auth-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
