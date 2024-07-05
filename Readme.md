# Imersão DevOps && Cloud 

## Extensões recomendadas para VS Code

- Kubernetes (autor: Microsoft)

## Aula 2 - Kubernetes: do zero ao deploy

### K3D

Ferramenta para auxiliar na montagem de um cluster kubernetes local para provas de conceito e utilizar como ambiente de estudo. O processo de instalação pode ser consultado no site da ferramenta: https://k3d.io/

> [!NOTE]
> Outras ferramentas existentes para criar um cluster kubernetes local:
> - K3S
> - MicroK8S
> - Kind
> - Minikube

> [!IMPORTANT]
> É recomendado a intalação do **kubectl**, que é uma ferramenta de linha de comando para interagir com o cluster.

#### Criação de cluster com k3d

##### k3d cluster create
Cria cluster kubernetes com apenas um workernode.

Parâmetros:
- <nome>
- --servers <numero de servers>
- --agents <número de agents>

Visualizar os nodes: `kubectl get nodes`

#### k3d cluster list
Lista os clusters criados

#### k3d cluster delete

#### Comando para criar o cluster com k3d e executar a aplicação:
```Bash
k3d cluster create meucluster -p "8080:30000@loadbalancer"
```

### Subir uma aplicação no cluster Kubernetes local

#### Principais elementos de deploy do Kubernetes
##### Pod
Menor objeto dentro de um cluster kubernetes. É nele que serão executados os containers.

Deve-se colocar cada container da nossa aplicação dentro de um pod pois é ele quem escalamos quando precisamos de melhorar o desempenho da aplicação num curto espaço de tempo (a exceção é quando utilizamos o padrão Sidecar).

##### ReplicaSet
Elemento que gerencia os pods do cluster. Será responsável pela resiliência da aplicação (quando um pod parar, ele automaticamente inicializa outro).

##### Deployment
Gerencia os replicaSets do cluster.
Cria o replicaSet especificando a versão da aplicação que está sendo executada. 

##### Labels e Selectors
Forma de conectar os objetos dentro do cluster.

Labels são elementros chave/valor que são utilizados para marcar os objetos no cluster kubernetes.
Exemplo: marcar um pod com as seguintes labels:
- app: web-color
- versao: v2
- ambiente: homolog

Selectors é a seleção de objetos baseado em algumas labels.
Exemplo: marcar o deplayment e o replicaSet com o seguinte selector:
- app: web-color
- versao: v2
- ambiente: homolog

Labels marca os objetos dentro do cluser e selectors fazem a ligação entre objetos.

#### Service Discovere
Ponto único de comunicação entre aplicações dentro do Kubernetes.
Responsável por fazer balanceamento de carga da comunicação.

##### Tipos de Service

- ClusterIP: ponto único de comunicação para serviços rodando dentro do mesmo cluster (apenas comunicação interna).
- NodePort: cria acesso externo para os pods.
- LoadBalancer: cria um load balancer no cloud provider e expões um IP público.

### Deploy de uma aplicação

#### Preparando o cluster
Criar cluster kubernetes: `k3d cluster create <nome-cluster> --servers 3 --agents 3 -p "30000:30000@loadbalancer"`

Listar os nós criados: kubectl get nodes

#### Preparando a aplicação




Aula 03
Template de rede para o EKS do CloudFormations:

https://s3.us-west-2.amazonaws.com/amazon-eks/cloudformation/2020-10-29/amazon-eks-vpc-private-subnets.yaml

Aula 04

Aula 05 
