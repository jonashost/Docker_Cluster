📘 README.md
markdown
Copiar
Editar
# 🐳 Docker_Cluster com Vagrant e Docker Swarm

Este projeto é uma simulação prática de um ambiente DevOps com foco em redes, orquestração de containers e automação. Utilizando **Vagrant**, **VirtualBox** e **Docker Swarm**, foi criado um cluster Docker local com 1 nó master e 3 nós workers.

---

## 📌 Objetivo

O principal objetivo é estudar na prática conceitos fundamentais de:

- 🔧 Docker e containers
- 🐝 Docker Swarm (orquestração)
- 💻 Vagrant (infraestrutura como código)
- 🌐 Redes virtuais e comunicação entre containers
- 📦 Deploy de aplicações simples em cluster

---

## 🏗️ Estrutura do projeto

- `Vagrantfile`: Define 4 VMs (1 master + 3 workers)
- `scripts/install_docker.sh`: Script que instala o Docker em cada VM
- `site/index.html`: Página HTML personalizada servida pelo Nginx
- `Dockerfile`: Criação de imagem customizada do Nginx
- `.vagrant/`: Pasta local gerada automaticamente pelo Vagrant (não necessária no GitHub)

---

## 🚀 Como usar

> **Pré-requisitos:**  
> - VirtualBox  
> - Vagrant  
> - Git

### 1. Clone o repositório

```bash
git clone https://github.com/jonashost/Docker_Cluster.git
cd Docker_Cluster
2. Suba as VMs
bash
Copiar
Editar
vagrant up
3. Acesse o nó master
bash
Copiar
Editar
vagrant ssh master
4. Inicialize o Swarm (caso necessário)
bash
Copiar
Editar
docker swarm init --advertise-addr 192.168.56.10
5. Faça build e deploy da aplicação
bash
Copiar
Editar
cd /home/vagrant/site
docker build -t jonascraxs/meu-nginx-customizado .
docker push jonascraxs/meu-nginx-customizado
docker service create --name meu-web --replicas 4 -p 8080:80 jonascraxs/meu-nginx-customizado
🌱 Aprendizado
Durante o desenvolvimento, foram explorados conceitos como:

Criar clusters com Docker Swarm

Gerenciar múltiplos nós com Vagrant

Criar imagens Docker personalizadas

Deploy distribuído de serviços web

Compartilhar imagens com DockerHub

Versionamento de infraestrutura com Git e GitHub

📸 Resultado
A aplicação foi distribuída em 4 réplicas, cada uma rodando em diferentes nós do Swarm. Acesse via:

cpp
Copiar
Editar
http://192.168.56.10:8080
🧠 Autor
Jonas (zerocall)
🔗 GitHub: @jonashost

📄 Licença
Este projeto está sob a licença MIT. Sinta-se livre para estudar, modificar e contribuir!

yaml
Copiar
Editar

---








