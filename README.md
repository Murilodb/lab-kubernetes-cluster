<img width="462" height="291" alt="image" src="https://github.com/user-attachments/assets/b42bbe5c-37dd-43e0-a4f5-964b71734568" />

# LABORATORIO KUBERNETES UTILIZANDO O MINIKUBE
Crie um cluster no minikube utilizando docker como driver

<code> minikube start -p skeelo --driver=docker --nodes=3</code>

<img width="721" height="241" alt="image" src="https://github.com/user-attachments/assets/87d627b0-960c-44f9-b9be-c05c613bea44" />

para validar como está o cluster pode ser utilizado o comando

<code>minikube profile list</code>
<img width="1011" height="151" alt="image" src="https://github.com/user-attachments/assets/13ec87c2-f674-4dda-9a6d-f96d53fc5194" />

## Criando um deployment no cluster

Utilize um editor de código e crie um deployment em yaml

ex:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: skeelo-deployment
  labels:
    app: skeelo
spec:
  replicas: 3
  selector:
    matchLabels:
      app: skeelo
  template:
    metadata:
      labels:
        app: skeelo
    spec:
      containers:
      - name: skeelo
        image: murilodb/skeelo-api:1.0
        ports:
        - containerPort: 3000
```
realize o apply

<img width="411" height="85" alt="image" src="https://github.com/user-attachments/assets/c421749a-8477-4045-b7fd-6492e0ea1edd" />

Para visualizar o deployment em modo gráfico utilize o dashboard do kubernetes que está disponível no minikube 

<code>minikube dashboard -p skeelo --url</code>
<img width="1618" height="975" alt="image" src="https://github.com/user-attachments/assets/4a936f6c-21a6-4f0c-8f00-9786f06de2e2" />

