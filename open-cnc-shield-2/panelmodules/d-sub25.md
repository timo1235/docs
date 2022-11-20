---
cover: broken-reference
coverY: 0
---

# D-SUB25

<div>

<figure><img src="../../.gitbook/assets/panel d-sub25-3-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/panel d-sub25-4-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/panel d-sub25-1200px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Mit diesem PanelModule kann ein externes Bedienelement / Handrad über ein D-SUB25 Kabel angeschlossen werden. Da das Kabel über 25 Adern verfügt, gibt es für jede Funktion eine separate Datenleitung.

### Überblick

* D-SUB25 Anschluss
* Eigene Datenleitung für jede Funktion

### LED

Es gibt eine LED auf dem Board, welche durch den ESP32 auf dem OPEN-CNC-Shield 2 gesteuert werden kann.

### Pinout

| D-SUB25 Pin | Funktion                                       | D-SUB25 Pin | Funktion                                       |
| ----------- | ---------------------------------------------- | ----------- | ---------------------------------------------- |
| 1           | 5V                                             | 14          | GND                                            |
| 2           | 5V                                             | 15          | GND                                            |
| 3           | Encoder A                                      | 16          | Encoder B                                      |
| 4           | Joystick X                                     | 17          | Joystick Y                                     |
| 5           | Joystick Z                                     | 18          | Feedrate - Vorschubgeschwindigkeit             |
| 6           | Rotation Speed - Spindelgeschwindigkeit        | 19          | Programm Start                                 |
| 7           | Motor Start                                    | 20          | OK                                             |
| 8           | Auswahl X                                      | 21          | Auswahl Y                                      |
| 9           | Auswahl Z                                      | 22          | Speed 1                                        |
| 10          | Speed 2                                        | 23          | ENA - Enable der Treiber                       |
| 11          | Autosquare                                     | 24          | ESP TX - Serielle Verbindung                   |
| 12          | ESP RX - Serielle Verbindung                   | 25          | Frei - Kann am Pin Header selbst belegt werden |
| 13          | Frei - Kann am Pin Header selbst belegt werden |             |                                                |

Die Pins D13 und D25 stehen zusätzlich auf der Platine als Pin Header zur Verfügung und können selbst belegt werden.

### Technische Details

Bis auf die serielle Verbindung(ESP TX und RX) arbeiten alle Ein- und Ausgänge am D-SUB25 mit einem 5V Pegel.

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/PanelModules/PanelModule%20D-SUB25" %}
