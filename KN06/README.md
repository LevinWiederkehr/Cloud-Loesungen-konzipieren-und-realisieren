# KN06: Skalierung

## A) Installation App 

### Reverse Proxy
Ein Reverse Proxy liegt vor mehreren Servern. Er nimmt die Pakete an inspektiert diese und leitet diese dann an den richtigen Server.

### Cloud-Init Probleme
Man sollte die Benutzerdaten für das Login nicht im Klartext ins File einfügen.

Unnötig dass das Proxy File zuerst im Home erstellt wird und danach kopiert wird.

## B) Vertikale Skalierung

![Swagger Aufruf](Swagger.png)
![GetProducts](GetProducts.png)
![Collections](Auszug_Collection.png)

### Erklärung:

In der Instanz unter Storage, findet man die aktuelle Disk.

Auf die Disk klicken.

![Bild](Bild.jpg)

Dann oben rechts unter Actions > Modify Volume kann man die Disk Grösse erhöhen

![Bild](Bild2.png)
![Bild](Bild3.jpg)

Um den Instanz Typ zu ändern muss man zuerst die Instanz stoppen.

Dann unter "Actions > Instance Settings > Change Instance Type" kann man den neuen Instanztyp auswählen.

![Bild](Bild4.png)
![Bild](Bild5.png)

### Nachher

![Bild](Bild6.png)
![Bild](Bild7.png)
![Bild](Bild8.jpg)

## C) Horizontale Skalierung

Um die Webserver mit der URL app.tbz-m346.ch zu erreichen, müsste man einen CNAME RECORD erstellen und dort die bestehende URL von aws einfügen.

Hier sieht man noch, dass der Load Balancer funktioniert.

![Bild](Bild9.png)


## D) Auto Scaling

### Auto Scaling:
Passt automatisch die Anzahl der Instanzen je nach Bedarf an, um die Leistung zu optimieren und Kosten zu sparen.

### Health Checks:
Überprüfen regelmässig, ob Instanzen funktionsfähig sind. Ungesunde Instanzen werden nicht genutzt.

### Load Balancer:
Verteilt den eingehenden Traffic gleichmässig auf mehrere Instanzen, um Überlastungen zu vermeiden und die Verfügbarkeit zu sichern.


### Monitoring:
Es bezieht sich auf die Überwachung von Ressourcen wie EC2-Instanzen und Load Balancern, um ihre Leistung zu messen und Probleme frühzeitig zu erkennen. Dies wird hauptsächlich durch Amazon CloudWatch durchgeführt, das Metriken (Metriken = messbare Größen/auch Messwerte) wie CPU-Auslastung, Arbeitsspeicher und Netzwerkaktivität bereitstellt. 

Für Auto Scaling werden diese Metriken verwendet, um automatisch Instanzen hinzuzufügen oder zu entfernen. CloudWatch-Alarme überwachen festgelegte Schwellenwerte (z.B. CPU-Auslastung > 80 %) und lösen Auto Scaling Policies aus, um Instanzen zu starten oder zu stoppen.

Damit Auto Scaling funktioniert, müssen Health Checks eingerichtet sein, damit nur gesunde funktionierende Instanzen skaliert werden. Zudem muss die Auto Scaling-Gruppe mit einem Load Balancer integriert sein, um den Traffic effizient zu verteilen und Instanzen bei Bedarf automatisch zu ersetzen.

#### Auto Scaling Policies:
Das sind Regeln, die festlegen, wann und wie AWS Auto Scaling Instanzen hinzufügen oder entfernen soll, um die Leistung und Verfügbarkeit einer Anwendung zu optimieren. Diese Policies basieren auf den Metriken wie CPU-Auslastung, Arbeitsspeicher oder Anfragen pro Sekunde.

#### Traffic:
Die 2 Hauptarten:
- Website-Traffic - Anzahl Besuchende (Beispiel: Seitenaufrufe, Klicks)
- Netzwerk-Traffic - Gesamter Datenverker im Netzwerk

Traffic kann in Verbindung mit Auto-Scaling gebracht genutzt werden.
Beispiel: Zu viele Benutzer auf der Webseite.

---

#### Quellen für diese Informationen
1. AWS-Dokumentation: [AWS-Dokumentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-monitoring-features.html)
2. Was ist Traffic: [WasIstTraffic](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-monitoring-features.html)
3. ChatGPT: Prompt - Was sind Ato Scaling Policies?