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
### SHELL A NODO (VM)
```
lxc shell worker1
```
### VER PODS
```
kubectl get pods
```
### APLICAR YAML
```
kubectl apply -f archivo.yaml
```
