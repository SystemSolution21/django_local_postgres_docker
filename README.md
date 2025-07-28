# Django Local PostgreSql Docker

## Django application run locally and database PostgreSql run in Docker container

<br>

## Requirements

- Docker
- Python 3.13
- pip
- uv
- Postgresql

<br>

## Virtual Environment

```pwsh
uv venv
.venv\Scripts\activate
```

<br>

## Dependencies Installation

```pwsh
uv pip install --upgrade pip
uv pip install -r requirements.txt
```

<br>

## Run Docker Container

```pwsh
docker compose up -d
```

<br>

## Generate secret key(if required)

```pwsh
python manage.py shell
from django.core.management.utils import get_random_secret_key
print(get_random_secret_key())
exit()
```

<br>

## Database Migrations

```pwsh
python manage.py makemigrations
python manage.py migrate
```

<br>

## Run Django Application

```pwsh
python manage.py runserver
```

<br>

## PostgreSql container database confirmation

```pwsh
docker exec -it postgres-container bash
psql -U postgres -d postgres
\dt
```
