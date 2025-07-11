# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES

**WORKER** maquina virtual en el que correran los contenedores

**RACK** dispositivo fisico en el que corren los workers

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
