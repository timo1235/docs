---
cover: ../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# WinPC NC USB

<div>

<figure><img src="../../.gitbook/assets/controller winpc-2-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/controller winpc-4-1200px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Dieser Controller ist für die Verwendung mit einem WinPC NC USB Modul gedacht. Demnach wird das entsprechende [WinPC Modul](https://www.lewetz.de/de/sample-sites-2/winpc-nc/winusb) zusätzlich benötigt.

### Überblick

* 4-Achsen
* 10 Eingänge
* 5 Ausgänge
* Verbindung mit dem PC über USB
* **WinPC unterstützt externe Handräder generell per USB-Verbindung an den Rechner und diese sind damit unabhängig vom OPEN-CNC-Shield 2**

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

<table><thead><tr><th width="313">Möglichkeiten OCS2</th><th width="432">Unterstützung des Estlcam Adapters</th></tr></thead><tbody><tr><td>6 Achsen</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> Steuerung von 4 Achsen. Weitere Achsen können auf dem <a href="../mainboard-mini/anschluesse-jumper.md#achsenkonfiguration">Shield gleichlaufend konfiguriert </a>werden.</td></tr><tr><td>16 Eingänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> 10</td></tr><tr><td>8 Ausgänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> 5</td></tr><tr><td>Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Externe Bedienelemente</strong></td><td></td></tr><tr><td>Handrad / Encoder</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Motor Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> Theoretisch über die Eingänge realiserbar</td></tr><tr><td>Programm Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> Theoretisch über die Eingänge realisierbar</td></tr><tr><td>OK Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Feedrate (Vorschubgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Rotation Speed (Spindelgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>3-Achsen Joystick </td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Auwahl X, Y, Z zur Wahl der Achsen für den Encoder</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr></tbody></table>

### Pin Mapping <a href="#undefined" id="undefined"></a>

| LPT Pins                              | OCS2 Anschluss                |
| ------------------------------------- | ----------------------------- |
| **LPT1**                              |                               |
| Pin 2-9 - Achsen X,Y,Z und 4. Achse   | Achsen X,Y,Z und A            |
| Pin 1 - Bohrspindel an/aus            | Spindle on/off                |
| Pin 14  - Kühlmittelpumpe an/aus      | Ausgang 1                     |
| Pin 16 - Stromabsenkung               | ENA - Enable                  |
| Pin 10 - Referenzschalter X           | Eingang 1                     |
| Pin 11 - Referenzschalter Y           | Eingang 2                     |
| Pin 12 - Referenzschalter Z           | Eingang 3                     |
| Pin 13 - Taster / Tasterblock         | Eingang 4                     |
| Pin 15 - frei                         | Eingang 5                     |
| **LPT2**                              |                               |
| Pin 2-9 - Analogausgang binar codiert | Pinout J1 am ControllerModule |
| Pin 1 - frei                          | Ausgang 2                     |
| Pin 14 - frei                         | Ausgang 3                     |
| Pin 16 - frei                         | Ausgang 4                     |
| Pin 17 - frei                         | Ausgang 5                     |
| Pin 10 - frei                         | Eingang 6                     |
| Pin 11 - frei                         | Eingang 7                     |
| Pin 12 - frei                         | Eingang 8                     |
| Pin 13 - frei                         | Eingang 9                     |
| Pin 14 - frei                         | Eingang 10                    |

Alle Eingänge an den Pins 10, 11, 12, 13 und 15 und die zusätzlichen Ausgänge der Pins  1, 14, 16 und 17 können freizügig definiert und den gewünschten Signalen zugeordnet werden. Im Auslieferungszustand der Software sind oben aufgeführte Signale zugeordnet.

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/ControllerModules/ControllerModule%20WinPC-NC" %}
