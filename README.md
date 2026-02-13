# 🚀 Implementação Completa de Pipeline CI/CD Avançado com Principais Ferramentas DevOps

![DevOps Pipeline](https://imgur.com/WcCpKVU.png)

## 📌 Sobre o Projeto

Este projeto demonstra a implementação completa de um pipeline CI/CD end-to-end utilizando as principais ferramentas do ecossistema DevOps moderno.

A solução cobre todo o ciclo de vida da aplicação — desde o provisionamento da infraestrutura até o deploy em Kubernetes com monitoramento ativo — simulando um ambiente corporativo real.

O objetivo foi construir um fluxo automatizado, escalável e observável, aplicando boas práticas de Infraestrutura como Código (IaC), integração contínua, entrega contínua e monitoramento.

---

# 🏗️ Arquitetura da Solução

O pipeline foi estruturado em múltiplas camadas:

### 🔹 Infraestrutura como Código
- Provisionamento automatizado via Terraform
- Criação de VPC, Security Groups e instâncias EC2
- Criação de cluster EKS

### 🔹 Configuração Automatizada
- Configuração de Jenkins Master e Agents via Ansible
- Setup de ambiente Maven Build Server

### 🔹 Integração Contínua
- Multibranch Pipeline no Jenkins
- Integração com GitHub via Webhooks
- Análise de qualidade com SonarQube
- Publicação de artefatos no JFrog Artifactory

### 🔹 Containerização
- Build de imagem Docker a partir do `.jar`
- Push automatizado para registry privado (JFrog)

### 🔹 Orquestração
- Deploy em cluster EKS
- Uso de Deployment e Service
- Exposição via LoadBalancer

### 🔹 Observabilidade
- Monitoramento com Prometheus
- Dashboards com Grafana

---

# 🧠 Decisões Arquiteturais

- Separação clara entre provisionamento e configuração
- Uso de IaC para garantir reprodutibilidade
- Pipeline orientado a qualidade de código
- Containerização para padronização de ambientes
- Kubernetes para escalabilidade horizontal
- Monitoramento integrado desde o deploy

---

# ⚙️ Stack Tecnológica

- Terraform  
- Ansible  
- Jenkins  
- SonarQube / SonarCloud  
- JFrog Artifactory  
- Docker  
- Amazon EKS  
- Kubernetes  
- Prometheus  
- Grafana  
- AWS (EC2, VPC, IAM, EKS, ELB)

---

# 🔄 Fluxo do Pipeline

## 1️⃣ Provisionamento (Terraform)

- Criação de:
  - VPC
  - Security Groups
  - Ansible Controller
  - Jenkins Master
  - Jenkins Agents
  - Cluster EKS

---

## 2️⃣ Configuração (Ansible)

- Configuração do Jenkins Master
- Configuração de Jenkins Agent como Maven Build Server
- Setup de SSH password-less

---

## 3️⃣ Integração com GitHub

- Criação de Multibranch Pipeline
- Configuração de credenciais
- Trigger automático via Webhook

---

## 4️⃣ Quality Gate (SonarQube)

Etapas adicionadas no Jenkinsfile:

- Stage de Code Quality
- Stage de Unit Tests
- Stage de Build

---

## 5️⃣ Gerenciamento de Artefatos

- Publicação de artefatos no JFrog Artifactory
- Controle de versionamento de builds

---

## 6️⃣ Containerização

- Build da imagem Docker
- Push automatizado para registry privado

```bash
docker build -t app:latest .
docker push <registry-url>
```

---

## 7️⃣ Deploy no Kubernetes (EKS)

Configuração do kubeconfig:

```bash
aws eks update-kubeconfig --region <region> --name <cluster>
```

Deploy utilizando:

- Deployment
- Service (LoadBalancer)
- Kubernetes Secrets para acesso ao registry

---

## 8️⃣ Monitoramento

- Instalação do Prometheus via Helm
- Instalação do Grafana
- Exposição via LoadBalancer
- Dashboards para métricas de cluster e aplicação

---

# 📊 Observabilidade Implementada

✔ Monitoramento de Pods  
✔ Monitoramento de Nodes  
✔ Métricas de CPU e memória  
✔ Visualização via dashboards  
✔ Ambiente preparado para troubleshooting  

---

# 🔐 Segurança Aplicada

- Uso de credenciais seguras no Jenkins
- Secrets no Kubernetes
- Controle de acesso IAM
- Separação de ambientes
- Registry privado para imagens Docker

---

# 📈 Resultados Técnicos

✔ Pipeline totalmente automatizado  
✔ Deploy contínuo em Kubernetes  
✔ Integração de múltiplas ferramentas DevOps  
✔ Ambiente escalável e reprodutível  
✔ Monitoramento integrado  
✔ Estrutura próxima de ambiente corporativo real  

---

# ⭐ Se este projeto foi útil

Considere:

- Dar uma estrela ⭐  
- Compartilhar  
- Contribuir com melhorias  

---

> Este projeto simula um pipeline corporativo completo, demonstrando integração entre múltiplas ferramentas DevOps modernas e práticas de engenharia aplicadas a ambientes reais.
