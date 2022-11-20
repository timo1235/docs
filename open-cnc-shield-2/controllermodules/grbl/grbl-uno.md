---
cover: ../../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# GRBL Arduino Uno

Dieser Controller ist für die Verwendung von GRBL gedacht. Es wird zusätzlich ein Arduino Uno benötigt. Als Steuerungssoftware kommen sämtliche Softwares mit GRBL Unterstützung infrage, zum Beispiel [LaserGRBL](https://lasergrbl.com/).

### Überblick

* 3-Achsen
* 5 Eingänge
* 2 Ausgänge
* Zusätzliche Eingänge zum Starten des Programms etc.
* Verbindung mit dem PC über USB

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                     |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :warning: Steuerung von 3 Achsen. Weitere Achsen können auf dem [Shield gleichlaufend konfiguriert ](../../mainboard/anschluesse-jumper.md#achsenkonfiguration)werden. |
| 16 Eingänge                                                             | :warning: 5 - Verwendet für Limit X,Y und Z, Feed Hold und Probe Input aus GRBL                                                                                        |
| 8 Ausgänge                                                              | :warning: 2 - Verwendet für Flood und Mist aus GRBL                                                                                                                    |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                   |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                   |
| **Externe Bedienelemente**                                              |                                                                                                                                                                        |
| Handrad / Encoder                                                       | :x:                                                                                                                                                                    |
| Motor Start Taster                                                      | :x:                                                                                                                                                                    |
| Programm Start Taster                                                   | :white\_check\_mark: (GRBL "cycle start")                                                                                                                              |
| OK Taster                                                               | :warning: Genutzt für GRBL "reset"                                                                                                                                     |
| Feedrate (Vorschubgeschwindigkeit)                                      | :x:                                                                                                                                                                    |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :x:                                                                                                                                                                    |
| 3-Achsen Joystick                                                       | :x:                                                                                                                                                                    |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :x:                                                                                                                                                                    |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :x:                                                                                                                                                                    |

### Pin Mapping <a href="#undefined" id="undefined"></a>

| GRBL Funktion                    | OCS2 Anschluss                                                                                     |
| -------------------------------- | -------------------------------------------------------------------------------------------------- |
| X-Limit                          | Eingang 1                                                                                          |
| Y-Limit                          | Eingang 2                                                                                          |
| Z-Limit                          | Eingang 3                                                                                          |
| Spindle Enable                   | Spindle on/off                                                                                     |
| Spindle                          | Spindle pwm                                                                                        |
| Spindle Direction/Spindle Enable | Spindle on/off                                                                                     |
| Flood                            | Ausgang 2                                                                                          |
| Mist                             | Ausgang 1                                                                                          |
| Reset                            | OK                                                                                                 |
| Feed hold                        | Eingang 4 :warning: GRBL bedingt geteilt mit Safety Door                                           |
| Cycle Start                      | Programm Start                                                                                     |
| Safety Door                      | Eingang 4 :warning:GRBL bedingt geteilt mit Feed Hold                                              |
| Probe input                      | Eingang 5                                                                                          |
| Driver Enable / Disable          | ENA - Enable (:warning: nur wenn der Jumper JP1 gesteckt ist - siehe info Kommentar unter Tabelle) |

{% hint style="info" %}
Die ENA Verbindung ist über einen Jumper vorgesehen. Das hat den Grund, dass einige Softwares(zum Beispiel LaserGRBL) die Treiber nur aktivieren, wenn auch verfahren wird. Demnach haben die Motoren dann im Stillstand keinen Haltemoment. Je nach Konstruktion/CNC kann das aber Probleme bereiten. Daher kann über den Jumper eingestellt werden, ob ENA von der Software verwaltet werden kann, oder nicht.
{% endhint %}

Für ungenutzte Pins und weitere Funktionen steht ein Pinout zur Verfügung:

<figure><img src="../../../.gitbook/assets/grbl_uno_pinout.png" alt=""><figcaption></figcaption></figure>

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/ControllerModules/ControllerModule%20GRBL%20Uno" %}
