# EV Solar Charging Tracker for Home Assistant

Ein natives Home Assistant Paket zur exakten Trennung von Ladestrom (E-Auto) in PV-Überschuss und Netzbezug. Das Setup erfordert keine Drittanbieter-Software und wird nach der Installation vollständig über die Home Assistant Benutzeroberfläche konfiguriert.

## Funktionen

* **Echtzeit-Aufteilung:** Berechnet den Anteil von Netz- und PV-Strom anhand der aktuellen Ladeleistung und des Hausverbrauchs.
* **UI-Konfiguration:** Sensoren, Stromtarife und Speicherverluste werden direkt über das Dashboard eingestellt. Kein Eingriff in den YAML-Code nötig.
* **Speicher- und Ladeverluste:** Optionaler prozentualer Aufschlag, um AC/DC-Wandlungsverluste (Heimspeicher) realistisch abzubilden.
* **Dynamische Abrechnungstabelle:** Eine Markdown-Tabelle fasst die monatlichen Kosten und kWh-Werte für das aktuelle Jahr zusammen. Leere Monate werden automatisch ausgeblendet.

## Voraussetzungen

Das System benötigt lediglich zwei bestehende Sensoren in Home Assistant:
1.  Aktuelle Ladeleistung des Fahrzeugs in Watt.
2.  Aktueller Netzbezug des Hauses in Watt.

## Installation

### 1. Packages aktivieren
Stelle sicher, dass Home Assistant YAML-Pakete unterstützt. Füge dazu Folgendes in deine `configuration.yaml` ein, falls noch nicht vorhanden:

```yaml
homeassistant:
  packages: !include_dir_named packages
