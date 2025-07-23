# CHEATSHEET_K8S
Kubernetes (k8s) permite orquestar contenedores independientemente de que sean un gran numero de ellos o funcionen sobre equipos independientes.

## TERMINOS IMPORTANTES (vocabulario)
ver [TERMS.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/TERMS.md)

## INSTALANDO K8S
ver [INSTALL.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/INSTALL.md)

## COMANDOS UTILES
VER [COMMANDS.md](https://github.com/elarreglador/cheatsheet_K8S/blob/main/COMMANDS.md)

### VER NODOS
```
kubectl get nodes
```
### LXC: SHELL A NODO (VM)
```
lxc shell worker1
```
### LXC: EJECUTAR COMANDO EN NODO (VM)
```
lxc exec worker1 -- ls -l /dev/ttyUSB0
```
### LXC: REINICIAR NODO (VM)
```
lxc restart worker1 -f
```
o mejor aun:
```
lxc stop worker1
lxc start worker1
```
### SHELL A POD
```
kubectl exec -it <NOMBRE_DEL_POD> -- sh
```
o algo mas funcional:
```
kubectl exec -it <NOMBRE_DEL_POD> -- bash
```
### VER PODS
```
kubectl get pods
```
### LOG DEL POD
```
kubectl logs <NOMBRE_DEL_POD>
```
### APLICAR YAML
```
kubectl apply -f archivo.yaml
```
### OBTENER YAML ACTUAL
```
kubectl get deployment zigbee-ch15 -o yaml
```


