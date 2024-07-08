# Base image with Python

FROM python:3.10-slim



# Create working directory

WORKDIR /app



# Copy poetry.lock and pyproject.toml

COPY poetry.lock ./

COPY pyproject.toml ./



# Install dependencies using Poetry (assuming Poetry is not pre-installed)

#RUN apt-get update && apt-get install -y --no-install-recommends \

#    curl  # needed for installing Poetry



#RUN curl -sSL https://install.python-poetry.org | python3 -  # Install Poetry

RUN pip install poetry



ENV PATH="$PATH:/opt/poetry/bin"



# Copy application code

COPY . .



RUN poetry install



# Expose port for FastAPI (typically 8000)

EXPOSE 8000



# Postgres

# Environment variables for database connection

ENV POSTGRES_SERVER=localhost

ENV POSTGRES_PORT=5432

ENV POSTGRES_DB=app

ENV POSTGRES_USER=app

ENV POSTGRES_PASSWORD=hngapptolu



# Set working directory within the container (optional)

WORKDIR /app



# Database setup using Poetry script

#RUN poetry run bash ./prestart.sh



# Entrypoint command

CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000
