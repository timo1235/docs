---
description: >-
  Hier sammle ich Fehlerbeschreibungen, welche mich immer mal wieder erreichen
  und verweise auf die Lösungen.
---

# Fehlersammlung

[#motoren-drehen-manchmal-in-die-falsche-richtung-beim-autosquaring.-motoren-fahren-gegen-ihre-endstop](fehlersammlung.md#motoren-drehen-manchmal-in-die-falsche-richtung-beim-autosquaring.-motoren-fahren-gegen-ihre-endstop "mention")

[#der-esp32-auf-dem-open-cnc-shield-2-blinkt-blau-im-serial-monitor-steht-pca9555\_1-not-found-oder-pca](fehlersammlung.md#der-esp32-auf-dem-open-cnc-shield-2-blinkt-blau-im-serial-monitor-steht-pca9555\_1-not-found-oder-pca "mention")

[#die-motoren-fahren-los-sobald-estlcam-gestartet-wird-auch-bei-mittelstellung-des-joysticks-bewegen-s](fehlersammlung.md#die-motoren-fahren-los-sobald-estlcam-gestartet-wird-auch-bei-mittelstellung-des-joysticks-bewegen-s "mention")

[#joystick-laesst-sich-nicht-mittig-einstellen-am-panelmodule-breakout](fehlersammlung.md#joystick-laesst-sich-nicht-mittig-einstellen-am-panelmodule-breakout "mention")

## Lösungen

### Motoren drehen manchmal in die falsche Richtung beim Autosquaring. Motoren fahren gegen ihre Endstops nach dem Autosquaring

Siehe diesen Beitrag: [autosquaring.md](autosquaring.md "mention"). Autosquaring sollte immer vor dem Start der Software ausgeführt werden, da diese ansonsten den Prozess beeinflussen kann.

### Der ESP32 auf dem OPEN-CNC-Shield 2 blinkt blau / Im Serial Monitor steht "PCA9555\_1 not found!!" oder "PCA9555\_2 not found!!"

Das deutet darauf hin, dass die beiden oder einer beiden PCA9555 Chips nicht gefunden wird. Diese Chips sind In-Out-Expander für den ESP32 und stelle zusätzliche In- und Outputs zur Verfügung.\
**Die Chips funktionieren nur, wenn auch Boardspannung anliegt**. Ein USB-Kabel am ESP32 oder dem Estlcam-Arduino reichen nicht aus. Wenn einer der Chips trotz passender Stromversorgung nicht gefunden wird, muss dieser ausgetauscht werden.

### Die Motoren fahren los, sobald Estlcam gestartet wird / Auch bei Mittelstellung des Joysticks bewegen sich die Motoren

Prüfen, ob die Achsen des Joysticks richtig kalibriert sind. Bei Estlcam -> Einstellungen -> CNC-Steuerung -> Bedienelemente kann der Joystick kontrolliert werden. Ist der Joystick in Mittelstellung, sollten auch dort die blauen Balken alle relativ mittig sein. Kleine Abweichungen sind normal und lassen sich in Estlcam über den "Leerweg" abfangen. Sollte die Abweichung zu groß sein, kann man einfach die Kalibrierung starten, falls man die ESP32 Panel Platine nutzt, siehe [esp32-panel-platine.md](../esp32-panel-platine.md "mention"). Diese kann den Joystick selbst kalibrieren.\
Ansonsten kann man die Potis direkt am Joystick einstellen. Dazu die kleine Schraube lösen und den Poti ein wenig drehen, bis der Ausschlag des Balkens in Estlcam nahezu mittig ist. Kleine Schwankungen wird es immer geben.&#x20;

### Joystick lässt sich nicht mittig einstellen am PanelModule Breakout

Das ist vermutlich auf ein Problem auf der Platine zurückzuführen. Siehe dazu [https://github.com/timo1235/cnc-werkstatt/issues/3](https://github.com/timo1235/cnc-werkstatt/issues/3)\
Die einfachste Lösung ist, einen ESP32 mit der OCS2 Firmware auf das OCS2 aufzustecken.&#x20;
