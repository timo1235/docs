# Micropod

### Überblick

* bis zu 6-Achsen
* 5 Eingänge
* 3 Ausgänge
* Zusätzliche Eingänge zum Starten des Programms etc.
* **Verbindung mit dem PC über RJ45 - LAN**

### Unterstützung der OCS2 Funktionen <a href="#unterstuetzung-des-ocs2-funktionen" id="unterstuetzung-des-ocs2-funktionen"></a>

| Möglichkeiten OCS2                                                      | Unterstützung des Estlcam Adapters                                                                                                                                     |
| ----------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 6 Achsen                                                                | :warning: Steuerung von 4 Achsen. Weitere Achsen können auf dem [Shield gleichlaufend konfiguriert ](../../mainboard/anschluesse-jumper.md#achsenkonfiguration)werden. |
| 16 Eingänge                                                             | :warning: 6                                                                                                                                                            |
| 8 Ausgänge                                                              | :warning: 2                                                                                                                                                            |
| Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM                | :white\_check\_mark:                                                                                                                                                   |
| Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters | :white\_check\_mark:                                                                                                                                                   |
| **Externe Bedienelemente**                                              |                                                                                                                                                                        |
| Handrad / Encoder                                                       | :x:                                                                                                                                                                    |
| Motor Start Taster                                                      | :x:                                                                                                                                                                    |
| Programm Start Taster                                                   | :x:                                                                                                                                                                    |
| OK Taster                                                               | :x:                                                                                                                                                                    |
| Feedrate (Vorschubgeschwindigkeit)                                      | :x:                                                                                                                                                                    |
| Rotation Speed (Spindelgeschwindigkeit)                                 | :x:                                                                                                                                                                    |
| 3-Achsen Joystick                                                       | :x:                                                                                                                                                                    |
| Auwahl X, Y, Z zur Wahl der Achsen für den Encoder                      | :x:                                                                                                                                                                    |
| Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit         | :x:                                                                                                                                                                    |

### Pin Mapping <a href="#undefined" id="undefined"></a>

Auszug aus dem Handbuch:

<figure><img src="../../../../.gitbook/assets/micropod.png" alt=""><figcaption></figcaption></figure>

| Micropod Pin/Funktion                               | OCS2 Anschluss     |
| --------------------------------------------------- | ------------------ |
| Pin 1 - freier Ausgang / Spindel                    | Spindle on/off     |
| Pin 3,5,7,9,11,13,15,17 - Achsen X,Y,Z und 4. Achse | Achsen X,Y,Z und A |
| Pin 19 - freier Eingang / Ref Z                     | Eingang 3          |
| Pin 21 - Nothalt                                    | Eingang 5          |
| Pin 23 - freier Eingang / Ref Y                     | Eingang 2          |
| Pin 25 - freier Eingang / Ref X                     | Eingang 1          |
| Pin 2 - freier Ausgang / Kühlung                    | Ausgang 1          |
| Pin 4 - freier Eingang / Werzeuglängensensor        | Eingang 4          |
| Pin 6 - freier Ausgang / Stromabsenkung             | Ausgang 2          |
| Pin 8 - freier Ausgang / PWM                        | Spindle pwm        |
| Pin 22 - freier Eingang / Ref A                     | Eingang 6          |

