# TERMINOS IMPORTANTES

## WORKER

maquina virtual en el que correran los contenedores

## NODO

dispositivo fisico en el que corren los workers

## CLUSTER 

conjunto de racks

## Namespace

una forma de dividir los recursos de tu clúster en grupos lógicos, permiten aislamiento logico, organizacion, seguridad, control de acceso y gestion de recursos

Cuando instalas Kubernetes (o Minikube), ya vienen con algunos Namespaces predefinidos:

- default: Este es el Namespace predeterminado. Si no especificas un Namespace al crear un recurso, este se ubicará en default. Es útil para clústeres pequeños o para empezar, pero no recomendado para entornos de producción.

- kube-system: Contiene todos los recursos creados por el propio sistema Kubernetes (componentes del plano de control, DNS del clúster, etc.). Nunca debes desplegar tus propias aplicaciones en kube-system ni modificar sus recursos.

- kube-public: Contiene recursos que son visibles públicamente para todos los usuarios, incluso para aquellos no autenticados. Se usa raramente.

- kube-node-lease: Contiene objetos Lease que proporcionan latidos (heartbeats) de los nodos para que el plano de control pueda detectar fallos de nodos rápidamente.

## kubectl

cliente de terminal para k8s.
