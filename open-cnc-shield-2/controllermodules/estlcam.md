---
cover: ../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# Estlcam

<div>

<figure><img src="../../.gitbook/assets/DSC00670.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/DSC00671.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/DSC00755.jpg" alt=""><figcaption><p>OPEN-CNC-Shield 2 mit Estlcam ControllerModule und Arduino</p></figcaption></figure>

</div>

Dieser Controller ist für die Verwendung der Software [Estlcam ](https://www.estlcam.de/Fertigungsunterlagen\_Klemmen.php)gedacht. Die Software wird von Christian Knüll entwickelt und deckt die Bedürfnisse im Hobby-Bereich sehr gut ab. Es wird außerdem ein Arduino Mega 2560 benötigt. Dieser wird auf das ControllerModule aufgesteckt.

Videoanleitung OPEN-CNC-Shield 2 - Estlcam:

### Überblick

* 3-Achsen
* CAM und Steuersoftware in einem
* 16 Eingänge
* 8 Ausgänge
* Zusätzliche Eingänge für Bedienelemente, Handrad, Joystick etc.
* Verbindung mit dem PC über USB

### Unterstützung der OCS2 Funktionen

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                  |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :warning: Steuerung von 3 Achsen. Weitere Achsen können auf dem [Shield gleichlaufend konfiguriert ](../mainboard/anschluesse-jumper.md#achsenkonfiguration)werden. |
| 16 Eingänge                                                             | :white\_check\_mark: 16                                                                                                                                             |
| 8 Ausgänge                                                              | :white\_check\_mark: 8                                                                                                                                              |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                |
| **Externe Bedienelemente**                                              |                                                                                                                                                                     |
| Handrad / Encoder                                                       | :white\_check\_mark:                                                                                                                                                |
| Motor Start Taster                                                      | :white\_check\_mark:                                                                                                                                                |
| Programm Start Taster                                                   | :white\_check\_mark:                                                                                                                                                |
| OK Taster                                                               | :white\_check\_mark:                                                                                                                                                |
| Feedrate (Vorschubgeschwindigkeit)                                      | :white\_check\_mark:                                                                                                                                                |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :white\_check\_mark:                                                                                                                                                |
| 3-Achsen Joystick                                                       | :white\_check\_mark:                                                                                                                                                |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :white\_check\_mark:                                                                                                                                                |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :white\_check\_mark:                                                                                                                                                |

### Pin Mapping

Die Pins sind nach dem originalen Estlcam Schema angeschlossen und können auch nicht verändert werden.

<figure><img src="../../.gitbook/assets/estlcam mega pinout.png" alt=""><figcaption></figcaption></figure>

Pins, welche auf dem OCS2 nicht genutzt werden, stehen auf dem Adapter als Pinout zur Verfügung. Dazu gehören:

* Speed 3-6
* Motor Stop (Funktion ist auch durch zweimaliges Auslösen von Motor Start verfügbar)
* Programm Stop (Funktion ist auch durch zweimaliges Auslösen von Programm Start verfügbar)
* LED X, Y, Z

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/ControllerModules/ControllerModule%20Estlcam" %}
