# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES

**WORKER** 

maquina virtual en el que correran los contenedores

**NODO** 

dispositivo fisico en el que corren los workers

**CLUSTER** 

conjunto de racks

**Namespace**

una forma de dividir los recursos de tu clúster en grupos lógicos, permiten aislamiento logico, organizacion, seguridad, control de acceso y gestion de recursos

Cuando instalas Kubernetes (o Minikube), ya vienen con algunos Namespaces predefinidos:

- default: Este es el Namespace predeterminado. Si no especificas un Namespace al crear un recurso, este se ubicará en default. Es útil para clústeres pequeños o para empezar, pero no recomendado para entornos de producción.

- kube-system: Contiene todos los recursos creados por el propio sistema Kubernetes (componentes del plano de control, DNS del clúster, etc.). Nunca debes desplegar tus propias aplicaciones en kube-system ni modificar sus recursos.

- kube-public: Contiene recursos que son visibles públicamente para todos los usuarios, incluso para aquellos no autenticados. Se usa raramente.

- kube-node-lease: Contiene objetos Lease que proporcionan latidos (heartbeats) de los nodos para que el plano de control pueda detectar fallos de nodos rápidamente.

**kubectl** 

cliente de terminal para k8s


## INSTALANDO K8S
ver [INSTALL.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/INSTALL.md)

## COMANDOS UTILES
**kubectl --help**

Muestra la ayuda de kubectl

**kubectl get nodes** 

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
