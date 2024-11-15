# Hypervisor – Übersicht

Ein **Hypervisor** ermöglicht es, mehrere virtuelle Maschinen (VMs) auf einem einzigen physischen Rechner auszuführen.
Dabei verwaltet er die Ressourcen wie CPU, Speicher und Speicherplatz.

## Typen von Hypervisoren

### Typ 1: Bare-Metal-Hypervisor
- Läuft direkt auf der Hardware ohne ein zugrunde liegendes Betriebssystem.  
- Effizienter und für professionelle Anwendungen geeignet.  
- Beispiele: VMware ESXi, Microsoft Hyper-V.  

### Typ 2: Hosted-Hypervisor
- Läuft auf einem bestehenden Betriebssystem.  
- Einfacher einzurichten, aber weniger performant.  
- Beispiele: VirtualBox, VMware Workstation.  

## Unterschied
- **Typ 1**: Direkter Hardwarezugriff, hohe Effizienz.  
- **Typ 2**: Abhängig vom Host-Betriebssystem, mehr Overhead.

---

---

# Hypervisor-Typ-Test und Ressourcenanalyse

## Vermutung des Hypervisor-Typs
Wir vermuten, dass unser System einen **Hypervisor Typ 2** verwendet, da wir eine Virtualisierungssoftware (VMware Workstation) auf einem bestehenden Betriebssystem nutzen.

---

## Schritte zur Überprüfung

### 1. Host-System überprüfen
- **Ressourcen des Host-Systems ausgelesen:**
  - **Logische Prozessoren:** [Anzahl eintragen]  
  - **RAM:** [Anzahl in GB eintragen]

### 2. Virtuelle Maschine erstellen
- **Erstellte VM:** [Name des Betriebssystems, z. B. Ubuntu]  
- **Zugewiesene Ressourcen:**
  - Prozessoren: Mehr als die verfügbaren logischen Prozessoren des Host-Systems.  
  - RAM: Mehr als den verfügbaren RAM des Host-Systems.  

---

## Ergebnisse

### CPU-Test
- [Screenshot einfügen]  
- Ergebnis: [Beschreiben, ob mehr Prozessoren zugewiesen werden konnten oder eine Fehlermeldung angezeigt wurde.]

### RAM-Test
- [Screenshot einfügen]  
- Ergebnis: [Beschreiben, ob mehr RAM zugewiesen werden konnte oder eine Fehlermeldung angezeigt wurde.]

---

## Erklärung und Fazit

### Warum gibt es Fehlermeldungen?  
Falls keine zusätzlichen Ressourcen zugewiesen werden konnten, liegt dies daran, dass der Hypervisor nur die verfügbaren Ressourcen des Host-Systems nutzen kann. Dies bestätigt, dass es sich um einen Typ-2-Hypervisor handelt, der keine direkte Hardwaresteuerung hat.

### Wie ist Überzuweisung möglich?  
Falls mehr Ressourcen zugewiesen werden konnten, ist dies durch **Overcommitment** möglich. Der Hypervisor emuliert Ressourcen, die physisch nicht vorhanden sind, was jedoch die Stabilität beeinträchtigen kann.

### Fazit  
- Unsere Vermutung, dass es sich um einen **Hypervisor Typ 2** handelt, wurde [bestätigt/nicht bestätigt].  
- [Kurze Begründung auf Basis der Tests].
