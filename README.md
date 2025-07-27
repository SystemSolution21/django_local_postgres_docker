# Django Local PostgreSql Docker

Django application run locally but the database PostgreSql is run in a Docker container.

## Requirements

- Docker
- Python 3.13
- pip
- uv
- Postgresql

## Virtual Environment

```pwsh
uv venv
.venv\Scripts\activate
```

## Dependencies Installation

```pwsh
uv pip install --upgrade pip
uv pip install -r requirements.txt
```

## Run Docker Container

```pwsh
docker compose up -d
```

## Generate secret key(if required)

```pwsh
python manage.py shell
from django.core.management.utils import get_random_secret_key
print(get_random_secret_key())
exit()
```

## Database Migrations

```pwsh
python manage.py makemigrations
python manage.py migrate
```

## Run Django Application

```pwsh
python manage.py runserver
```

## PostgreSql container database confirmation

```pwsh
docker exec -it postgres-container bash
psql -U postgres -d postgres
\dt
```
