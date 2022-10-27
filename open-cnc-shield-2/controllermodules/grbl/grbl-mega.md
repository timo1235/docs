---
cover: ../../../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# GRBL Arduino Mega

<div>

<figure><img src="../../../../.gitbook/assets/controller grbl-3-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../../.gitbook/assets/controller grbl-1200px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Dieser Controller ist für die Verwendung von GRBL gedacht. Es wird zusätzlich ein Arduino Mega 2560 benötigt. Als Steuerungssoftware kommen sämtliche Softwares mit GRBL Unterstützung infrage, zum Beispiel [LaserGRBL](https://lasergrbl.com/).

### Überblick

* 3-Achsen
* 5 Eingänge
* 3 Ausgänge
* Zusätzliche Eingänge zum Starten des Programms etc.
* Verbindung mit dem PC über USB

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                     |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :warning: Steuerung von 3 Achsen. Weitere Achsen können auf dem [Shield gleichlaufend konfiguriert ](../../mainboard/anschluesse-jumper.md#achsenkonfiguration)werden. |
| 16 Eingänge                                                             | :warning: 5 - Verwendet für Limit X,Y und Z, Safety Door und Probe Input aus GRBL                                                                                      |
| 8 Ausgänge                                                              | :warning: 3 - Verwendet für Flood, Mist und Spindle Direction aus GRBL                                                                                                 |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                   |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                   |
| **Externe Bedienelemente**                                              |                                                                                                                                                                        |
| Handrad / Encoder                                                       | :x:                                                                                                                                                                    |
| Motor Start Taster                                                      | :warning: Genutzt für "feed hold"                                                                                                                                      |
| Programm Start Taster                                                   | :white\_check\_mark: ("cycle start")                                                                                                                                   |
| OK Taster                                                               | :warning: Genutzt für "reset"                                                                                                                                          |
| Feedrate (Vorschubgeschwindigkeit)                                      | :x:                                                                                                                                                                    |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :x:                                                                                                                                                                    |
| 3-Achsen Joystick                                                       | :x:                                                                                                                                                                    |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :x:                                                                                                                                                                    |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :x:                                                                                                                                                                    |

### Pin Mapping <a href="#undefined" id="undefined"></a>

| GRBL Funktion           | OCS2 Anschluss                                                                                     |
| ----------------------- | -------------------------------------------------------------------------------------------------- |
| X-Limit                 | Eingang 1                                                                                          |
| Y-Limit                 | Eingang 2                                                                                          |
| Z-Limit                 | Eingang 3                                                                                          |
| Spindle Enable          | Spindle on/off                                                                                     |
| Spindle                 | Spindle pwm                                                                                        |
| Spindle Direction       | Ausgang 3                                                                                          |
| Flood                   | Ausgang 2                                                                                          |
| Mist                    | Ausgang 1                                                                                          |
| Reset                   | OK                                                                                                 |
| Feed hold               | Motor Start                                                                                        |
| Cycle Start             | Programm Start                                                                                     |
| Safety Door             | Eingang 4                                                                                          |
| Probe input             | Eingang 5                                                                                          |
| Driver Enable / Disable | ENA - Enable (:warning: nur wenn der Jumper JP1 gesteckt ist - siehe info Kommentar unter Tabelle) |

{% hint style="info" %}
Die ENA Verbindung ist über einen Jumper vorgesehen. Das hat den Grund, dass einige Softwares(zum Beispiel LaserGRBL) die Treiber nur aktivieren, wenn auch verfahren wird. Demnach haben die Motoren dann im Stillstand keinen Haltemoment. Je nach Konstruktion/CNC kann das aber Probleme bereiten. Daher kann über den Jumper eingestellt werden, ob ENA von der Software verwaltet werden kann, oder nicht.
{% endhint %}

Sämtliche ungenutzte Pins des Arduino Mega 2560 stehen in Form eines Pinout zur Verfügung:

<figure><img src="../../../../.gitbook/assets/grbl pinout.png" alt=""><figcaption></figcaption></figure>
