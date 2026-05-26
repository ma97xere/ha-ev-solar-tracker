# EV Solar Charging Tracker (Admin Panel Edition)

Ein natives Home Assistant Paket zur exakten Trennung von Ladestrom (E-Auto) in PV-Überschuss und Netzbezug. 
Diese Edition installiert sich nicht als normales Dashboard, sondern als **eigenständige Verwaltungsplattform** (Backend) mit einem cleanen, Apple-like UI in der linken Seitenleiste.

## Highlights
* **Eigener Menüpunkt:** Nistet sich nahtlos in die Home Assistant Seitenleiste ein.
* **Apple-like UI:** Nutzt das moderne Sections-Layout für eine aufgeräumte Backend-Optik.
* **Zero-Code Konfiguration:** Alle Tarife, Entitäten und Speicherverluste werden direkt über die Oberfläche verwaltet.
* **Smarte Abrechnung:** Automatische, dynamische Jahrestabelle (Jan - Dez) für die exakte Kostenabrechnung.

## 🚀 Installation (In 5 Minuten)

### 1. Ordnerstruktur anlegen
Erstelle in deinem Home Assistant `config`-Verzeichnis zwei neue Ordner:
* `packages`
* `panels`

### 2. Dateien ablegen
* Kopiere die Datei `ev_solar_tracker.yaml` aus diesem Repository in den Ordner `packages`.
* Kopiere die Datei `ev_billing_ui.yaml` aus diesem Repository in den Ordner `panels`.

### 3. configuration.yaml anpassen
Öffne deine `configuration.yaml` und füge folgende Zeilen ein, um das Backend zu aktivieren und das neue Panel in der Seitenleiste zu registrieren:

```yaml
homeassistant:
  packages: !include_dir_named packages

lovelace:
  mode: yaml
  dashboards:
    ev-abrechnung:
      mode: yaml
      title: Abrechnung
      icon: mdi:invoice-text-outline
      show_in_sidebar: true
      filename: panels/ev_billing_ui.yaml
