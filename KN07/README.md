# KN07: PAAS

## A) Datenbank im PAAS Modell

![Datenbankabfrage](Datenbankabfrage.png)

### Wieso PAAS/SAAS anstatt einer eigenen Datenbank?

- Die Wartung, Sicherstellung der Verfügbarkeit und das Skalieren der Datenbank wird von den Anbietern übernommen.
- Die Kosten für Mitarbeiter, die sich um die Server kümmern, sind wahrscheinlich höher als die Kosten für eine PAAS oder SAAS Datenbank.

## B) PAAS Applikation erstellen

### Veränderte Bereiche:

### Datenbankabfrage
![Datenbank festlegen](Datenbankfestlegen.png)
Wir erstellen eine MySQL-Datenbank für das Applikations-Environment. Somit wird die Datenbank in der Applikation verwendet.

---

### Auto Scaling aktivieren
![Auto Scaling aktivieren](Autoscaling.png)
Wir können direkt in den Environment-Einstellungen das Auto Scaling aktivieren – weshalb also nicht?

---

### Subnet auswählen
![Subnet auswählen](Subnetz.png)
Wir wählen das Subnet aus, in dem die Applikation laufen soll.

---

### Monitoring aktivieren
![Monitoring aktivieren](Monitoring.jpg)
Wir aktivieren das Monitoring für die Applikation und stellen dieses auf "Erweitert".

---

### Managed Platform Updates aktivieren
![Managed Platform Updates aktivieren](ManagedPlatformUpdates.png)
Mit den erweiterten Monitoring-Einstellungen können wir die Managed Platform Updates aktivieren.

## B) Erstellte Ressourcen/Objekte und ColoudFormation

### Was ist CloudFormation?
AWS CloudFormation ist ein Service, der es ermöglicht, Infrastruktur als Code zu erstellen und zu verwalten. Mit CloudFormation können Sie eine Vorlage erstellen, die die Ressourcen und Konfigurationen definiert, die Sie in Ihrer AWS-Umgebung bereitstellen möchten. Sie können die Vorlage dann verwenden, um die Infrastruktur in Ihrer AWS-Umgebung zu erstellen und zu verwalten.

### Erstellte Instanz
![Erstellte Instanz](ErstellteInstanz.png)

### Erstellte Security Group
![Security Group](SecurityGroup.png)

### Load Balancer
![Load Balancer](LoadBalancer.jpg)

### Cloud Formation Ressourcen
![Cloud Formation Ressourcen](CloudFormation.png)