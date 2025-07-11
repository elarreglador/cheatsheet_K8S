# COMANDOS UTILES

### kubectl --help**
Muestra la ayuda de kubectl

### kubectl -n kube-system delete pod coredns-674b8bbfcf-4kr9x
Elimina el pod coredns-674b8bbfcf-4kr9x del namespace kube-system delete
```
kubectl -n kube-system delete pod coredns-674b8bbfcf-4kr9x
pod "coredns-674b8bbfcf-4kr9x" deleted
```

### kubectl -n kube-system get pods
Muestra los pods disponibles dentro del namespace kube-system (pods de sistema)
```
kubectl -n kube-system get pods

NAME                               READY   STATUS    RESTARTS   AGE
coredns-674b8bbfcf-4kr9x           1/1     Running   0          53m
etcd-minikube                      1/1     Running   0          53m
kube-apiserver-minikube            1/1     Running   0          53m
kube-controller-manager-minikube   1/1     Running   0          53m
kube-proxy-8drm4                   1/1     Running   0          53m
kube-scheduler-minikube            1/1     Running   0          53m
storage-provisioner                1/1     Running   0          53m
```

### kubectl -n kube-system get pods -o wide
Muestra los pods disponibles dentro del namespace kube-system (pods de sistema) mostrando su IP y el nodo en el que corre
```
kubectl -n kube-system get pods -o wide

NAME                               READY   STATUS    RESTARTS   AGE   IP             NODE       NOMINATED NODE   READINESS GATES
coredns-674b8bbfcf-4kr9x           1/1     Running   0          69m   10.244.0.2     minikube   <none>           <none>
etcd-minikube                      1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
kube-apiserver-minikube            1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
kube-controller-manager-minikube   1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
kube-proxy-8drm4                   1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
kube-scheduler-minikube            1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
storage-provisioner                1/1     Running   0          69m   192.168.49.2   minikube   <none>           <none>
```

### kubectl apply -f mi-deployment.yaml --namespace=mi-namespace
Permite desplegar un recurso, por ejemplo un pod, en un Namespace específico. Si no se indica namespace se creara en namespace=default

### kubectl create namespace mi-proyecto
Crea un nuevo namespace

### kubectl exec -it my-pod -- bash
ejecutar un comando dentro del contenedor principal de my-pod en ejecución en tu clúster. En este caso el terminal bash

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
