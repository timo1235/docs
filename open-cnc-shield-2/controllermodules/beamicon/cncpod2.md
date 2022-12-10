# CncPod2

<div>

<figure><img src="../../../.gitbook/assets/controller beamicon-3-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/controller beamicon-10-1200px (1).jpg" alt=""><figcaption></figcaption></figure>

</div>

Dieser Controller ist für die Verwendung mit dem Beamicon Hardware gedacht. Demnach wird das entsprechende Beamicon CncPod2 Modul zusätzlich benötigt.

Videoanleitung OPEN-CNC-Shield 2 - Beamicon:

{% embed url="https://youtu.be/ZSoPC3y04gI" %}

### Überblick

* bis zu 6-Achsen
* 9 Eingänge
* 8 Ausgänge
* **Verbindung mit dem PC über RJ45 - LAN**
* **Beamicon unterstützt externe Handräder generell per USB-/RJ45-Verbindung an den Rechner und diese sind damit unabhängig vom OPEN-CNC-Shield 2**

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                                                                     |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :white\_check\_mark: Es können alle Achsen individuell angesteuert werden. Die Konfiguration auf dem OCS2 sollte nicht genutzt werden. Gleichlaufende Achsen können auch in der Beamicon Software konfiguriert werden. |
| 16 Eingänge                                                             | :warning: 9                                                                                                                                                                                                            |
| 8 Ausgänge                                                              | :white\_check\_mark:                                                                                                                                                                                                   |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                                                                   |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                                                                   |
| **Externe Bedienelemente**                                              |                                                                                                                                                                                                                        |
| Handrad / Encoder                                                       | :x:                                                                                                                                                                                                                    |
| Motor Start Taster                                                      | :x:                                                                                                                                                                                                                    |
| Programm Start Taster                                                   | :x:                                                                                                                                                                                                                    |
| OK Taster                                                               | :x:                                                                                                                                                                                                                    |
| Feedrate (Vorschubgeschwindigkeit)                                      | :x:                                                                                                                                                                                                                    |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :x:                                                                                                                                                                                                                    |
| 3-Achsen Joystick                                                       | :x:                                                                                                                                                                                                                    |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :x:                                                                                                                                                                                                                    |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :x:                                                                                                                                                                                                                    |

### Pin Mapping <a href="#undefined" id="undefined"></a>

Auszug aus dem Handbuch des CncPod2:

<figure><img src="../../../.gitbook/assets/cncpod2.png" alt=""><figcaption></figcaption></figure>

| LPT Pins                              | OCS2 Anschluss                                                                                  |
| ------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **LPT1**                              |                                                                                                 |
| Pin 1 - freier Ausgang                | Spindle on/off                                                                                  |
| Pin 2-9 - Achsen X, Y, Z und 4. Achse | Achsen X,Y,Z und A                                                                              |
| Pin 10 - freier Eingang               | Eingang 3                                                                                       |
| Pin 11 - Nothalt                      | Eingang 8                                                                                       |
| Pin 12 - freier Eingang               | Eingang 2                                                                                       |
| Pin 13 - freier Eingang               | Eingang 1                                                                                       |
| Pin 14 - freier Ausgang               | Ausgang 1                                                                                       |
| Pin 15 - freier Eingang               | Eingang 4                                                                                       |
| Pin 16 - freier Ausgang               | Ausgang 3                                                                                       |
| Pin 17 - freier Ausgang               | Spindle pwm                                                                                     |
| **LPT2**                              |                                                                                                 |
| Pin 1 - freier Ausgang                | Ausgang 2                                                                                       |
| Pin 2-5 - 5. und 6. Achse             | Achse B und C                                                                                   |
| Pin 6 - freier Ausgang                | Ausgang 7                                                                                       |
| Pin 7 - freier Ausgang                | Ausgang 8                                                                                       |
| Pin 8 - freier Ausgang                | ENA - Enable                                                                                    |
| Pin 9 - freier Ausgang                | \*nicht verbunden                                                                               |
| Pin 10 - freier Eingang               | Alarm all - wird ausgelöst wenn ein Treiber ein alarm signal ausgibt(Überlastung / Fehler etc.) |
| Pin 11 - freier Eingang               | Eingang 5                                                                                       |
| Pin 12 - freier Eingang               | \*nicht verbunden                                                                               |
| Pin 13 - freier Eingang               | Eingang 7                                                                                       |
| Pin 14 - freier Ausgang               | Ausgang 4                                                                                       |
| Pin 15 - freier Eingang               | Eingang 6                                                                                       |
| Pin 16 - freier Ausgang               | Ausgang 5                                                                                       |
| Pin 17 - freier Ausgang               | Ausgang 6                                                                                       |

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/ControllerModules/ControllerModule%20Beamicon" %}

