<div align="center">

# 🛒 DevOps Microservices

**E-commerce app built with Spring Boot microservices, Docker & CI/CD**
*Application e-commerce en micro-services Spring Boot, conteneurisée avec Docker, avec CI/CD*

![Java](https://img.shields.io/badge/Java_17-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=flat&logo=apachemaven&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

🇬🇧 [English](#-english) · 🇫🇷 [Français](#-français)

</div>

---

## 🇬🇧 English

### 💡 About
An e-commerce application split into Spring Boot microservices, containerized with Docker and orchestrated with Docker Compose.
🎓 Lab project, "Containerization techniques and microservices" course (2026). Kubernetes follow-up: [minikube-lab](https://github.com/Meli-ileM/minikube-lab).

### 🧩 Microservices
| Service | Role |
|---|---|
| 📦 `catalogue-service` | Product management |
| 🧾 `commande-service` | Order management |
| 💳 `paiement-service` | Payment management |
| 🚪 `gateway-service` | API Gateway, single entry point |
| 🧭 `discovery-service` | Service discovery (Eureka) |
| ⚙️ `config-service` | Centralized configuration |

Each service follows a layered architecture: `controller`, `service`, `domain`, `repository`, `dto`.

### ✨ What I did
- 🛠️ REST APIs with error handling, logging, validation, DTO mapping and unit tests
- 🔗 Inter-service communication with OpenFeign
- 🐳 One Dockerfile per service + full orchestration with Docker Compose (ports, env variables, internal network, databases, healthchecks)
- ✅ CI pipeline with GitHub Actions (build, tests and code quality on every push)
- 🧪 `Dockerfile.test` to test `catalogue-service` in a dedicated container

![GitHub Actions success](images/github-action-success.png)

### 🚀 Getting started
```bash
mvn clean package                  # build
docker compose up                  # run everything
docker compose down                # stop
```
| Service | URL |
|---|---|
| Eureka | http://localhost:8761 |
| Config Server | http://localhost:8888 |
| Gateway | http://localhost:8084 |
| Catalogue | http://localhost:8081 |

---

## 🇫🇷 Français

### 💡 À propos
Application e-commerce découpée en micro-services Spring Boot, conteneurisés avec Docker et orchestrés avec Docker Compose.
🎓 TP du module « Techniques de conteneurisation et micro-services » (2026). Suite sur Kubernetes : [minikube-lab](https://github.com/Meli-ileM/minikube-lab).

### ✨ Étapes réalisées
1. 🧰 **Environnement** : IDE, JDK, Maven, Docker et variables d'environnement
2. 🌱 **Génération** des micro-services avec Spring Initializr
3. 🛠️ **Développement** : API REST, gestion des erreurs, logging, validation, DTO, tests unitaires, communication via OpenFeign
4. 🐳 **Conteneurisation** : un Dockerfile par micro-service et création des images
5. 🚢 **Déploiement local** avec Docker puis Docker Compose (ports, variables, dépendances, réseau interne)
6. ✅ **Tests et validation** : enregistrement dans Eureka, appels via la Gateway, logs, bases de données et healthchecks
7. 🔁 **CI/CD** avec GitHub Actions et test du service catalogue avec `Dockerfile.test`

```bash
docker build -f Dockerfile.test -t catalogue-service-test .
docker run catalogue-service-test
```

---

<div align="center">

Made with 💜 by **Meli**

</div>
