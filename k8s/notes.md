# Pod

Содержит в себе контейнеры (преимущественно 1, но при сильной необходимости можно и более)

```yaml
---
apiVersion: v1
kind: Pod
metadata:
  name: <pod name>
spec:
  containers:
    - name: <name for container inside a pod>
      image: <container image>
      ports:
        - containerPort: 80 // Probably unrequired thing
```


# Replicaset

Запускает множество pod'ов по заданному шаблону.
С помощью selectors определяют pod'ы, которые принадлежит ему и регулирует их кол-во в соответствии с полем `replicas`.

```yaml
---
apiVersion: apps/v1  # Тут нужна другая версия апи
kind: ReplicaSet
metadata:
  name: my-replicaset
spec:
  replicas: 5
  selector:        # Описываем селекторы
    matchLabels:   # Совпадают лейблы
      app: my-app  # labels[app] == my-app
  template:
    metadata:
    labels:
      app: my-app
    spec:
      containers:
        - name: nginx
          image: nginx:1.27
          ports:
            - containerPort: 80
```

