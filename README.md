# CentralSeed

## Intro
CentralSeed is a multi-ecosystem full-stack AI generated platform, including：
- Java Spring Boot Backend：user management、generated api、biz logic
- Python AI Service（FastAPI）：using LLM API to make docs Vector-based generation
- Golang Micro-service：async tasks and service bridging
- Vue Frontend：Generated content UX/UI, Docs upload, History content
- Docker + Docker Compose：modularization

---

## Repo Infrastructure

CentralSeed/  
backend-java/  
ai-python/  
microservice-go/  
frontend-vue/  
docker-compose.yml  
README.md

---

## Docker Compose

1. Build Up：

docker-compose up --build

2. Module Build Details：

| Module | Dir | Command | Default Port |
|------|------|----------|----------|
| Python AI | ai-python/ | uvicorn app:app --host 0.0.0.0 --port 8000 | 8000 |
| Java Backend | backend-java/ | ./gradlew bootRun | 8080 |
| Golang Micro-service | microservice-go/ | go run main.go | 9000 |
| Vue Frontend | frontend-vue/ | npm install && npm run serve | 5173 |

> Start Queue：Python → Java → Go → Vue，make sure dependency。

---

## Port Details

| Module | Default | Func |
|------|----------|------|
| Vue Frontend | 5173 | UX/UI |
| Java Backend | 8080 | REST API, generation API |
| Python AI | 8000 | AI module, Vector-based search |
| Golang Micro-service | 9000 | async task, service bridging |
| MySQL | 3306 | data storage |
| Redis | 6379 | cache |
| MongoDB | 27017 | docs database |
| MinIO | 9000 | object database |
