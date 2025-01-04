
# Virtuelle Server

## Abgabe

1. **Funktionierende Webseiten:**
![alt Funktionierendes HTML](FunktionierendesHTML.png)
![alt Funktionierendes PHP](FunktionierendesPHP.png)
![alt Funktionierendes PHP DB](FunktionierendesPHPDB.png) 

---

2. **Details der Instanz:**
![alt Instanz-Details](InstanzDetails.jpg) 

---

3. **Regeln der Sicherheitsgruppen:**
![alt Regeln der Sicherheitsgruppen](SicherheitsgruppenRegeln.png) 

---

4. **MariaDB-Abfragen:**
![alt Einloggen in MariaDB](EinloggenMariaDB.png)
![alt DB-Abfrage](DBAbfrage.png)  

---


# Leitfragen / Checkpoints

## 3. Bedeutung der Pakete `apache2`, `php` und `mariadb-server`

- **`apache2`**: Installiert den Apache HTTP-Server für die Bereitstellung von Webseiten und Webanwendungen.
- **`php`**: Installiert die Programmiersprache PHP für serverseitige Webentwicklung.
- **`mariadb-server`**: Installiert den MariaDB-Datenbankserver zur Verwaltung von relationalen Datenbanken.

## 4. Notwendigkeit der Pakete `libapache2-mod-php` und `php-mysqli`

- **`libapache2-mod-php`**: Ein Modul für Apache, das es ermöglicht, PHP-Dateien direkt über den Webserver auszuführen.
- **`php-mysqli`**: Eine PHP-Erweiterung, die die Kommunikation mit MySQL/MariaDB-Datenbanken ermöglicht.

## 5. Sicherheitsgruppen und Änderungen an Regeln

- **Bedeutung:**  
  Sicherheitsgruppen sind virtuelle Firewalls, die den Netzwerkzugriff auf Serverressourcen regeln.
  
- **Änderungen vornehmen:**
  - Regeln für eingehenden oder ausgehenden Datenverkehr definieren.
  - Beispiel: Port 80 für HTTP oder Port 443 für HTTPS öffnen.

## 6. Was ist ein Port und wie macht man ihn öffentlich zugänglich?

- **Was ist ein Port?**  
  Ein Port ist eine virtuelle Schnittstelle, über die Netzwerkverbindungen auf einem Computer akzeptiert werden. Jede Anwendung nutzt spezifische Ports (z. B. Port 80 für HTTP).
  
- **Port öffentlich zugänglich machen:**  
  - Beispiel: Öffnen von Port 80 in einer Sicherheitsgruppe:
    ```bash
    sudo ufw allow 80/tcp
    ```

## 7. Anwendung der MySQL-Konsole

- **Zugriff auf die MySQL-Konsole:**
  ```bash
  sudo mysql -u root -p
  ```
  
- **Beispiele für MySQL-Befehle:**
  - Anzeigen aller Datenbanken:
    ```sql
    SHOW DATABASES;
    ```
  - Auswahl einer Datenbank:
    ```sql
    USE datenbankname;
    ```
  - Anzeigen der Tabellen einer Datenbank:
    ```sql
    SHOW TABLES;
    ```
  - Abfrage von Daten aus einer Tabelle:
    ```sql
    SELECT * FROM tabelle;
    ```

## 8. Nutzung von `systemctl`

- **Bedeutung:**  
  Mit `systemctl` können Systemdienste verwaltet werden.
  
- **Beispiele:**
  - Starten eines Dienstes:
    ```bash
    sudo systemctl start apache2
    ```
  - Stoppen eines Dienstes:
    ```bash
    sudo systemctl stop apache2
    ```
  - Neustarten eines Dienstes:
    ```bash
    sudo systemctl restart apache2
    ```
  - Anzeigen des Status eines Dienstes:
    ```bash
    sudo systemctl status apache2
    ```

## 9. Nutzung des Befehls `cp`

- **Bedeutung:**  
  Mit `cp` können Dateien und Verzeichnisse kopiert werden.
  
- **Beispiele:**
  - Einzelne Datei kopieren:
    ```bash
    cp quelle ziel
    ```
    Beispiel:
    ```bash
    cp datei.txt /home/benutzer/
    ```
  - Verzeichnis kopieren:
    ```bash
    cp -r ordnername ziel
    ```
    Beispiel:
    ```bash
    cp -r /etc/apache2/ /home/backup/
    ```

---

**Hinweis:** Diese Befehle und Konzepte gelten für die Verwaltung von Linux-Servern, insbesondere auf Debian-basierten Distributionen wie Ubuntu. Bitte prüfe die Dokumentation und stelle sicher, dass du die richtigen Berechtigungen hast, um Änderungen am System vorzunehmen.
