# RoadUSP

[🇺🇸 English](#english) | [🇧🇷 Português](#português)

---

## English

### Overview

RoadUSP is a web application for visualizing USP (University of São Paulo) curriculum prerequisites as an interactive force-directed graph. It helps students understand course dependencies and plan their academic path.

Featured in Jornal USP.

### Quick Start

```bash
# Clone with submodules
git clone --recursive https://github.com/Augusto-Ildefonso/roadusp.git
cd roadusp

# Frontend
cd front-end && npm install && npm start

# Backend
cd back-end
cp .env.example .env  # Add: SUPABASE_URL, SUPABASE_KEY, JWT_SECRET_KEY
make run
```

### Architecture

```
Frontend (React+D3)  →  Backend (Flask)  →  Supabase
                              ↑
                        Scraper (Selenium)
```

### Components

| Component | Tech | Port | Description |
|-----------|------|------|-------------|
| Frontend | React, D3.js | 3000 | Graph visualization |
| Backend | Flask | 3010 | REST API |
| Scraper | Selenium | - | Data ingestion |

### API Endpoints

| Endpoint | Description |
|----------|-------------|
| `GET /ping` | Health check |
| `GET /api/v1/cursos/lista?unidade=X` | List courses |
| `GET /api/v1/cursos/disciplinas?unidade=X&curso=Y` | Graph data |

### Deployment

| Component | Platform | URL |
|-----------|----------|-----|
| Frontend | Vercel | https://roadusp.vercel.app |
| Backend | Render | https://roadusp-backend.onrender.com |

### Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 19, D3.js 7, Axios |
| Backend | Flask, Flask-CORS, Flask-JWT-Extended |
| Database | Supabase (PostgreSQL) |
| Scraper | Selenium, BeautifulSoup 4 |

### Project Structure

```
roadusp/                    # Main repository (git submodules)
├── front-end/              # React frontend
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   └── style/
│   └── package.json
├── back-end/               # Flask backend
│   ├── src/
│   │   ├── api/
│   │   ├── core/
│   │   ├── repositories/
│   │   └── services/
│   └── server.py
└── scraper/                # Selenium scraper
    ├── scraper_jupiter.py
    ├── supabase_controller.py
    └── main.py
```

---

## Português

### Visão Geral

RoadUSP é uma aplicação web para visualização de pré-requisitos das disciplinas da USP (Universidade de São Paulo) como um grafo interativo direcionado por força. Ajuda estudantes a entender dependências de cursos e planejar sua trajetória acadêmica.

Publicado no Jornal USP.

### Início Rápido

```bash
# Clonar com submódulos
git clone --recursive https://github.com/Augusto-Ildefonso/roadusp.git
cd roadusp

# Frontend
cd front-end && npm install && npm start

# Backend
cd back-end
cp .env.example .env  # Adicionar: SUPABASE_URL, SUPABASE_KEY, JWT_SECRET_KEY
make run
```

### Arquitetura

```
Frontend (React+D3)  →  Backend (Flask)  →  Supabase
                              ↑
                        Scraper (Selenium)
```

### Componentes

| Componente | Tech | Porta | Descrição |
|-----------|------|-------|-----------|
| Frontend | React, D3.js | 3000 | Visualização do grafo |
| Backend | Flask | 3010 | API REST |
| Scraper | Selenium | - | Ingestão de dados |

### Endpoints da API

| Endpoint | Descrição |
|----------|----------|
| `GET /ping` | Health check |
| `GET /api/v1/cursos/lista?unidade=X` | Lista cursos |
| `GET /api/v1/cursos/disciplinas?unidade=X&curso=Y` | Dados do grafo |

### Deploy

| Componente | Plataforma | URL |
|-----------|-----------|-----|
| Frontend | Vercel | https://roadusp.vercel.app |
| Backend | Render | https://roadusp-backend.onrender.com |

### Stack Tecnológica

| Camada | Tecnologia |
|--------|-----------|
| Frontend | React 19, D3.js 7, Axios |
| Backend | Flask, Flask-CORS, Flask-JWT-Extended |
| Banco de Dados | Supabase (PostgreSQL) |
| Scraper | Selenium, BeautifulSoup 4 |

### Estrutura do Projeto

```
roadusp/                    # Repositório principal (git submodules)
├── front-end/              # Frontend React
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   └── style/
│   └── package.json
├── back-end/               # Backend Flask
│   ├── src/
│   │   ├── api/
│   │   ├── core/
│   │   ├── repositories/
│   │   └── services/
│   └── server.py
└── scraper/                # Scraper Selenium
    ├── scraper_jupiter.py
    ├── supabase_controller.py
    └── main.py
```