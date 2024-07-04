# Imersão DevOps && Cloud 

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
> É necessário instalar o X que é uma ferramenta de linha de comando para interagir com o cluster.



### Comando para criar o cluster com k3d e executar a aplicação:
```Bash
k3d cluster create meucluster -p "8080:30000@loadbalancer"
```

Aula 03
Template de rede para o EKS do CloudFormations:

https://s3.us-west-2.amazonaws.com/amazon-eks/cloudformation/2020-10-29/amazon-eks-vpc-private-subnets.yaml

Aula 04

Aula 05 
