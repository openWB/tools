# Simulator für openWB 2.x
Mit diesem Flow kann eine komplette virtuelle Umgebung für openWB bereitgestellt werden.
Die Umgebung besteht aus einem Zähler (muss als "EVU" in der Hierarchie eingerichtet sein),
einem PV-Modul, einem Batteriespeicher sowie drei Ladepunkten.

## Voraussetzungen
- Node-Red (getestet bis 3.0.2)
- node-red-contrib-interval-length
- node-red-contrib-pid
- node-red-dashboard
- node-red-node-smooth
- node-red-node-random

## Hintergrundwissen
Die PV-Anlage ist aktuell an alle drei Phasen "angeschlossen" und verteilt die Leistung gleichmäßig.
_(ToDo: Anschluss variabel auf einzelne Phasen konfigurierbar)_

Der Batteriespeicher verteilt seine Leistung ebenfalls gleichmäßig auf alle drei Phasen.
_(ToDo: Anschluss variabel auf einzelne Phasen konfigurierbar)_

Die Leistung des Speichers wird durch einen PID-Regler gesteuert. Die Parameter sind noch nicht optimal
eingestellt. Es kann vorkommen, dass die Regelung anfängt zu schwingen.
_(ToDo: PID-Regler optimieren)_

## Einrichtung
**Da alle Komponenten in openWB 2.x dynamisch vergeben werden, müssen nach dem Import des Flows
die Komponenten-IDs an die jeweiligen Gegebenheiten der eigenen Installation angepasst werden!**

Die Komponenten-IDs können in den Eigenschaften der Sub-Flows "EVU", "PV1", "Bat", "LP1", "LP2" und "LP3"
festgelegt werden.

In den Sub-Flow Eigenschaften der Ladepunkte kann ebenfalls festgelegt werden, an welcher Phase L1 des
EVU angeschlossen ist. Dadurch können auch komplexe Setups mit (gut oder ungünstig) rotierten Phasen
abgebildet werden.

---

# Steuerungsmöglichkeiten im Dashboard

## EVU Zähler
Der virtuelle Hausverbrauch kann im Dashboard je Phase festgelegt werden. Dadurch können gezielt Schieflasten
für das Lastmanagement erzeugt werden.

Die Netzfrequenz des Zählers kann variiert werden, um den Netzschutz seitens des Energieversorgers zu testen.

## PV
Die aktuelle Leistung des Wechselrichters kann zwischen 0W und 10kW variiert werden.

## Batteriespeicher
Der aktuelle Ladestand (SoC) kann gezielt eingestellt werden.

Die maximale Leistung des Speichers kann zwischen 0W und 5kW eingestellt werden.

Die virtuelle Kapazität des Batteriespeichers kann auf bis zu 15kWh angepsst werden.

## Ladepunkte
Es kann ein Fahrzeug "angesteckt" werden.

Es kann angegeben werden, wieviele Phasen das angeschlossene Fahrzeug maximal nutzen kann.
