# Simulator für openWB 1.x
Mit diesem Flow für Node-Red kann das Regelverhalten von openWB untersucht werden.
Der Flow simuliert das EVU-Modul, ein PV- sowie Speicher-Modul und drei Ladepunkte. In openWB müssen hierzu jeweils die MQTT-Module eingestellt werden.

## Voraussetzungen
- Node-Red (getestet mit 2.2.2)
- node-red-contrib-interval-length
- node-red-contrib-pid
- node-red-dashboard
- node-red-node-smooth

## erforderliche Anpassungen nach dem Import
- der MQTT Konfigurations-Node muss an die IP oder den Hostnamen der eigenen openWB angepasst werden
- in openWB muss bei der Modulkonfiguration auf das jeweilige MQTT-Modul umgestellt werden

## Bedienung
Mit dem Flow wird ein Dashboard eingerichtet, mit dem alle Parameter beliebig angepasst werden können.
