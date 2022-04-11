# Infrastructure as code, AZURE instance with terraform
Proyecto para crear clúster de Kubernetes en Azure con terraform.

## Provisionamiento de la infraestructura

- Instalar la CLI de Azure.
- Logeo con Azure CLI
```sh
$ az login
```
- Instalación de Terraform
- Configuración de Terraform
- Revisión y creación de la instractura:

```sh
# Este comando es necesario para descargar los plugins necesarios para el provider.
$  terraform init
```
```sh
# Con este comando es posible ver los recursos que se crearan con la definición.
$ terraform plan
```
```sh
# Esto creara la infraestructura que definimos que en este caso es una instance en Azure.
$ terraform apply
```

Entre los recusos que se creará están:
- Grupo de recursos **aks_tf_devops**
- Registro de Contenedores **acrdevopsbp**
- Clúster de Kubernetes **devops-bp-aks**, con las siguientes características:
     Ubicación:WestUS2
     Recuento de nodos: 2 nodos
     Escalado automático: desactivado.
     Tipo de instancia: Standard_d2s_v5 (CPU: 2; RAM: 8 GB)
     
## Gestión K8s
- Instalación de Kubectl
- Copiar el archivo kubeconfig al path correcto
- Comandos para revisar objetos y supervisar el clúster
```sh
$ kubectl config view
$ kubectl get nodes
$ kubectl get services
$ kubectl get deploymentes
$ kubectl get pods
```
## Otros Comandos de terraform
Para poder ejecutar los comandos de terraform es necesario estar dentro de la carpeta donde se encuentran los archivos de definicion.
```sh
$ terraform fmt
# Este comando es util para dar un formato uniforme a todos los archivos de terraform.
```
```sh
$ terraform validate
# Este comando es util para validar la sintaxis de los archivos de definición de terraform.
```
```sh
$ terraform destroy
# Terraform tambien nos permite destruir la infraestructura creada.
```
