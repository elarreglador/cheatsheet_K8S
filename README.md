# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES (vocabulario)
ver [TERMS.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/TERMS.md)

## INSTALANDO K8S
ver [INSTALL.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/INSTALL.md)

## COMANDOS UTILES
### kubectl --help**
Muestra la ayuda de kubectl

### kubectl apply -f mi-deployment.yaml --namespace=mi-namespace
Permite desplegar un recurso en un Namespace específico

### kubectl create namespace mi-proyecto
Crea un nuevo namespace

### kubectl get namespaces o kubectl get ns
Obtiene los namespaces
```
kubectl get namespaces

NAME                   STATUS   AGE
default                Active   39m
kube-node-lease        Active   39m
kube-public            Active   39m
kube-system            Active   39m
kubernetes-dashboard   Active   35m
```

### kubectl get nodes
mostrar una lista de todos los nodos (máquinas físicas o virtuales) que forman parte de tu clúster de Kubernetes

- NAME: El nombre del nodo (en el caso de Minikube, generalmente será minikube).

- STATUS: El estado actual del nodo. Lo ideal es que diga Ready, lo que significa que el nodo está funcionando correctamente y listo para aceptar Pods. Otros estados pueden ser NotReady (indica un problema con el nodo) o SchedulingDisabled.

- ROLES: El rol que desempeña el nodo en el clúster. En un clúster de producción, verás control-plane (para los nodos maestros) o <none> (para los nodos trabajadores). En Minikube, al ser un solo nodo que combina ambos roles, podría mostrar control-plane,master o solo control-plane.

- AGE: El tiempo que el nodo lleva en funcionamiento desde que fue añadido al clúster.

- VERSION: La versión de Kubernetes que se está ejecutando en ese nodo.
```
kubectl get nodes

NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   10m   v1.33.1

```
