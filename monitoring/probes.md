# Pods monitoren bei Konfigurationsänderung/Betrieb 

## Liveness - probe 

```
# Ist mein System live ? 
-> Läuft es. 

# Standardmäßig guckt er, ob es ein Prozess mit der PID 1 der läuft

```

## ReadiNess - probe 

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
##
