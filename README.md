<p>
  <img alt="Schema" src="./img/deployment.png" />
  
</p>

<h1 align="center">Alura cursos Projeto Portal de noticias </h1>

### Curso de Kubernetes: Pods, Services e ConfigMaps

## 1 - Instalação.

### Kubectl

Kubernetes command-line tools(<a href="https://kubernetes.io/docs/tasks/tools/">kubectl</a>) permite executar comandos em seus clusters kubernetes

### Kind

<p>
  <img alt="Schema" src="./img/kind.png" />
</p>

<a href='https://kind.sigs.k8s.io/' target="_blank">Kind</a> kubernetes in Docker é uma ferramenta que permite executar clusters kubernetes num ambiente local utilizando docker.

```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.19.0/kind-linux-amd64

chmod +x ./kind

sudo mv ./kind /usr/local/bin/kind

```

## 2 - Criando cluster com multiplos nós com kind

`kind create cluster --name kind-multinodes --config ./kind-3nodes.yaml`

<p>
  <img alt="Schema" src="./img/kind_create.png" />
</p>

## 3 - Aplicando as configurações

- portal-configmap.yml - Alterar IP_SISTEMA para o INTERNAL_IP de um dos nós

`kubectl get nodes -o wide`

Criar os seguintes items nessa ordem:

```markdown
├── db-deployment.yml
├── db-noticias-configmap.yml
├── db-noticias-svc.yml
├── db-noticias.yml
├── portal-configmap.yml
├── portal-deployment.yml
├── portal-hpa.yml
├── portal-service.yml
├── sistema-noticias-configmap.yml
├── sistema-noticias-deployment.yml
├── sistema-noticias-service.yml
└── sistema-noticias.yml
```

`kubectl apply -f item`

## 4 - Acessando o Portal de Noticias

- Portal de Noticias - http://ip_node:30000
- Sistema Noticias - http://ip_node:30002

Acessar as URLs geradas no navegador

## 4 - Acessando o Kubernetes Dashboard

<p>
  <img alt="Schema" src="./kubernetes_dashboard.png" />
  
</p>

Kubernetes Dashboard é ferramenta web onde é possível criar e modificar recursos como Deployments, Jobs, Services, verificar de forma visual consumo de CPU e memoria e monitorar o estado dos pods

<a href="https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/" target="_blank">Documentação</a>

## Autor

👤 **Marcus Vinicius**

- Github: [marcusjava](https://github.com/marcusjava)
