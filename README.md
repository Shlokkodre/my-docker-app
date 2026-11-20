# my-docker-app

![FastAPI CI](https://github.com/Shlokkodre/my-docker-app/actions/workflows/ci.yml/badge.svg)
[![CI](https://github.com/Omi7590/docker-project/actions/workflows/ci.yml/badge.svg)](https://github.com/Omi7590/docker-project/actions/workflows/ci.yml)

A FastAPI application containerized with Docker, with automated testing via GitHub Actions.

## Features

- REST API built with FastAPI
- Dockerized for consistent deployment
- Automated CI pipeline with GitHub Actions

## Endpoints

| Method | Route | Description |
|--------|-------|-------------|
| GET | `/` | Home — returns a welcome message |
| GET | `/about` | About — project description |
| GET | `/health` | Health check |
| GET | `/products` | Returns a list of products |

## Getting Started

### Run with Docker

```bash
docker build -t my-docker-app .
docker run -p 8000:8000 my-docker-app
```

### Run locally

```bash
# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\activate        # Windows
source .venv/bin/activate     # Linux / macOS

# Install dependencies
pip install -r requirements.txt

# Start the server
uvicorn main:app --reload
```

API will be available at `http://localhost:8000`  
Interactive docs at `http://localhost:8000/docs`

## Running Tests

```bash
pytest -v
```

## Project Structure

```
my-docker-app/
├── .github/
│   └── workflows/
│       └── ci.yml        # GitHub Actions CI pipeline
├── tests/
│   └── test_main.py      # API tests
├── main.py               # FastAPI app
├── Dockerfile            # Docker image definition
├── requirements.txt      # Python dependencies
└── README.md
```

## CI Pipeline

On every push and pull request, GitHub Actions automatically:
1. Sets up Python 3.11
2. Installs dependencies
3. Runs all tests with pytest
