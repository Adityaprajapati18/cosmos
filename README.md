# 🌌 Cosmos — AI-Powered Cloud Sandbox IDE

> A cloud-native, AI-assisted development environment that lets developers spin up isolated sandbox environments, write and execute code, and get real-time AI assistance — all in the browser.

---

## 🚀 Features

- 🤖 **AI Orchestration** — Intelligent AI backend that assists with code generation, debugging, and suggestions
- 🛡️ **Sandboxed Execution** — Isolated, secure code execution environments per user session
- 🔐 **Authentication** — Secure user auth and session management
- 🔔 **Notifications** — Real-time event and status notifications
- ☸️ **Kubernetes-Ready** — Fully containerized microservices with K8s deployment manifests
- ⚡ **Skaffold Integration** — Rapid local dev loop with Skaffold

---

## 🏗️ Architecture

```
cosmos/
├── ai-orchestration/     # AI service (Node.js) — handles AI requests & code assistance
│   ├── src/
│   ├── dockerfile
│   └── server.js
├── auth/                 # Authentication microservice
├── sandbox/              # Core sandbox environment
│   ├── agents/           # Sandbox execution agents
│   ├── router/           # Request routing
│   ├── server/           # Sandbox server
│   └── template/         # Sandbox templates
├── notification/         # Notification microservice
├── k8s/                  # Kubernetes manifests
├── ai-deployment.yml     # K8s deployment for AI service
├── ai-service.yml        # K8s service definition
└── skaffold.yml          # Skaffold dev config
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| AI Backend | Node.js |
| Containerization | Docker |
| Orchestration | Kubernetes |
| Dev Workflow | Skaffold |
| Architecture | Microservices |

---

## ⚙️ Getting Started

### Prerequisites
- [Docker](https://www.docker.com/)
- [Kubernetes](https://kubernetes.io/) (or [Minikube](https://minikube.sigs.k8s.io/))
- [Skaffold](https://skaffold.dev/)
- [Node.js](https://nodejs.org/) v18+

### Local Development

```bash
# Clone the repository
git clone https://github.com/Adityaprajapati18/cosmos.git
cd cosmos

# Start all services with Skaffold
skaffold dev
```

### Deploy to Kubernetes

```bash
# Apply Kubernetes manifests
kubectl apply -f k8s/
kubectl apply -f ai-deployment.yml
kubectl apply -f ai-service.yml
```

### AI Orchestration Service

```bash
cd ai-orchestration
npm install
npm start
# Runs on http://localhost:3000
```

#### Health Check Endpoints
- `GET /api/status/healthz` — Liveness probe
- `GET /api/status/readyz` — Readiness probe

---

## 📦 Kubernetes Deployment

The AI orchestration service is deployed with:
- **2 replicas** for high availability
- **Resource limits:** 500m CPU / 256Mi memory
- **Liveness & Readiness probes** for zero-downtime deployments

---

## 🗺️ System Workflow

See [`workflow.excalidraw`](./workflow.excalidraw) for the full system architecture diagram.

---

## 👨‍💻 Author

**Aditya Prajapati**
- GitHub: [@Adityaprajapati18](https://github.com/Adityaprajapati18)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
