# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES

**WORKER** maquina virtual en el que correran los contenedores

**NODO** dispositivo fisico en el que corren los workers

**CLUSTER** conjunto de racks

**kubectl** cliente de terminal para k8s

## INSTALANDO K8S
### REQUISITOS
2 CPUs o más, 2 GB de memoria libre o más, 20 GB de espacio libre en disco o más, conexión a Internet y docker.

### INSTALANDO DOCKER

Actualizar el índice de paquetes y permitir HTTPS:
```
sudo apt update
sudo apt install ca-certificates curl gnupg
```
Añadir la clave GPG oficial de Docker:
```
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
Añadir el repositorio de Docker a APT sources:
```
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
Actualizar el índice de paquetes e instalar Docker Engine, containerd y Docker Compose (CLI):
```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Añadir tu usuario al grupo docker
```
sudo usermod -aG docker $USER
newgrp docker
```
Verificar la instalación:
```
sudo docker run hello-world
```
Deberías ver un mensaje que indica que la instalación es exitosa.

## INSTALAR kubectl
Descarga la última versión estable de kubectl para Linux (amd64)
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
Haz el binario ejecutable
```
chmod +x ./kubectl
```
Mueve el binario a un directorio en tu PATH (por ejemplo, /usr/local/bin)
```
sudo mv ./kubectl /usr/local/bin/kubectl
```
Verifica que kubectl se ha instalado correctamente y muestra la versión del cliente
```
kubectl version --client
```

# INSTALAR Minikube
Descarga la última versión de Minikube para Linux (amd64)
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
Mueve el binario a un directorio en tu PATH y establece permisos de ejecución
```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
Elimina el archivo descargado (ya no es necesario)
```
rm minikube-linux-amd64
```
Verifica que Minikube se ha instalado correctamente
```
minikube version
```

## INICIAR CLUSTER K8S CON minikube
```
minikube start --driver=docker

😄  minikube v1.36.0 on Ubuntu 24.04
✨  Using the docker driver based on user configuration
📌  Using Docker driver with root privileges
👍  Starting "minikube" primary control-plane node in "minikube" cluster
🚜  Pulling base image v0.0.47 ...
💾  Downloading Kubernetes v1.33.1 preload ...
    > preloaded-images-k8s-v18-v1...:  347.04 MiB / 347.04 MiB  100.00% 36.26 M
    > gcr.io/k8s-minikube/kicbase...:  502.26 MiB / 502.26 MiB  100.00% 31.80 M
🔥  Creating docker container (CPUs=2, Memory=2200MB) ...
🐳  Preparing Kubernetes v1.33.1 on Docker 28.1.1 ...
    ▪ Generating certificates and keys ...
    ▪ Booting up control plane ...
    ▪ Configuring RBAC rules ...
🔗  Configuring bridge CNI (Container Networking Interface) ...
🔎  Verifying Kubernetes components...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🌟  Enabled addons: storage-provisioner, default-storageclass
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

```

## VERIFICAR ESTADO DEL CLUSTER
Verifica el estado de Minikube
```
minikube status

minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured
```
Verifica los nodos de Kubernetes
```
kubectl get nodes

NAME       STATUS   ROLES           AGE     VERSION
minikube   Ready    control-plane   2m26s   v1.33.1
```

