# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES

**WORKER** maquina virtual en el que correran los contenedores

**NODO** dispositivo fisico en el que corren los workers

**CLUSTER** conjunto de racks

**kubectl** cliente de terminal para k8s

## INSTALANDO K8S
ver [INSTALL.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/INSTALL.md)

## COMANDOS UTILES
**AYUDA**
```
kubectl --help
```

**LISTADO DE NODOS** 

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
