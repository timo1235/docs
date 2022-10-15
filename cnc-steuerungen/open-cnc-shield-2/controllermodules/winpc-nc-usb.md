---
cover: ../../../.gitbook/assets/ControllerModule_trans.png
coverY: 0
---

# WinPC NC USB

Dieser Controller ist für die Verwendung mit einem WinPC NC USB Modul gedacht. Demnach wird das entsprechende [WinPC Modul](https://www.lewetz.de/de/sample-sites-2/winpc-nc/winusb) zusätzlich benötigt.

### Überblick

* 4-Achsen
* 10 Eingänge
* 5 Ausgänge
* Zusätzliche Eingänge zum Starten des Programms etc.
* Verbindung mit dem PC über USB

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                  |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :warning: Steuerung von 4 Achsen. Weitere Achsen können auf dem [Shield gleichlaufend konfiguriert ](../mainboard/anschluesse-jumper.md#achsenkonfiguration)werden. |
| 16 Eingänge                                                             | :warning: 10                                                                                                                                                        |
| 8 Ausgänge                                                              | :warning: 5                                                                                                                                                         |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                |
| **Externe Bedienelemente**                                              |                                                                                                                                                                     |
| Handrad / Encoder                                                       | :x:                                                                                                                                                                 |
| Motor Start Taster                                                      | :x:                                                                                                                                                                 |
| Programm Start Taster                                                   | :x:                                                                                                                                                                 |
| OK Taster                                                               | :x:                                                                                                                                                                 |
| Feedrate (Vorschubgeschwindigkeit)                                      | :x:                                                                                                                                                                 |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :x:                                                                                                                                                                 |
| 3-Achsen Joystick                                                       | :x:                                                                                                                                                                 |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :x:                                                                                                                                                                 |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :x:                                                                                                                                                                 |

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
