# Pods monitoren bei Konfigurationsänderung/Betrieb 

## Liveness - probe 

```
# Ist mein System live ? 
-> Läuft es. 

# Standardmäßig guckt er, ob es ein Prozess mit der PID 1 der läuft

```

## Readiness - probe 

```
# Ist mein Pod ready?
# Nimmt er Anfragen an ? 

# Eigentlich nur pods, die services nach aussen bereitstellen 

# z.B. Überprüfung durch port / http-Abfrage 

```

## Wie frage ich ab ? 

```
http 

oder

exec 

```
## Example 

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 4 # tells deployment to run 2 pods matching the template
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
        livenessProbe:
          exec:
            command:
            - /bin/sh
            - -c
            - "[ -f /run/nginx.pid ]"
          initialDelaySeconds: 10
          periodSeconds: 5

        readinessProbe:
          httpGet:
            scheme: HTTP
            path: /
            port: 80
          initialDelaySeconds: 10
          periodSeconds: 5
```

