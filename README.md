# 🚀 GKE Docker CI/CD Pipeline

Pipeline completo de deploy com Docker e Kubernetes no Google Cloud Platform (GKE).
Inclui backend Node.js, frontend React, build de imagens Docker, push para Artifact Registry
e deploy automatizado via GitHub Actions.

---

## 📌 Arquitetura

Usuário → LoadBalancer (Frontend) → Backend Service → Pods Backend  
Cluster Kubernetes rodando no GKE (Google Cloud)

---

## 🛠️ Tecnologias Utilizadas

- Node.js (Backend)
- React (Frontend)
- Docker
- Kubernetes
- Google Kubernetes Engine (GKE)
- Artifact Registry
- GitHub Actions (CI/CD)


## ⚙️ Backend

API simples em Express que retorna:

GET /api

Resposta:
{
  "message": "Backend funcionando no Kubernetes 🚀"
}

---

## 💻 Frontend

Aplicação React que consome a API do backend
e exibe a mensagem retornada.

---

## 🐳 Docker

Cada aplicação possui seu próprio Dockerfile.

Backend:
- Base node:18-alpine
- Expõe porta 3000

Frontend:
- Build com node
- Servido via nginx
- Expõe porta 80

---

## ☸️ Kubernetes

Backend:
- Deployment com 2 réplicas
- Service ClusterIP

Frontend:
- Deployment com 2 réplicas
- Service LoadBalancer

---

## ☁️ Configuração GCP

1. Criar projeto no Google Cloud
2. Ativar:
   - Kubernetes Engine API
   - Artifact Registry API
3. Criar repositório Docker
4. Criar cluster GKE
5. Configurar Service Account para CI/CD

---

## 🚀 CI/CD

Pipeline GitHub Actions executa:

1. Build das imagens Docker
2. Push para Artifact Registry
3. Autenticação no GKE
4. Deploy automático no cluster

Deploy ocorre automaticamente ao realizar push na branch main.

---

## ▶️ Como Executar Localmente

Backend:
cd backend
npm install
npm start

Frontend:
cd frontend
npm install
npm start

---

## 📦 Deploy Manual no Kubernetes

kubectl apply -f k8s/

Verificar serviços:
kubectl get svc