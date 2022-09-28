# Panel Module

{% hint style="info" %}
Diese Seite ist für die Entwicklung neuer Panel Module und die Fehlersuche relevant.  Für die unterschiedlichen PanelModule gibt es eigene Dokumentationsseiten. Dort werden die unterstützten Features und technische Details der einzelnen Module beschrieben. [panelmodules.md](../../panelmodules.md "mention")
{% endhint %}

Die Panel-Module sind für die Verbindung der Steuerung mit externen Bedienelementen wie Handräder oder Bedienpulte.

## Pin Belegung

<figure><img src="../../../../.gitbook/assets/panel pin map.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typ OUT: Das Signal geht vom Controller / Steuerungssoftware in Richtung PanelModule

Typ IN: Das Signal kommt vom PanelModule und geht zum Controller / der Steuerung
{% endhint %}

### **Anschluss:**

| Pin | Beschreibung                                                       | Typ | Pin | Beschreibung                                                                                                  | Typ |
| --- | ------------------------------------------------------------------ | --- | --- | ------------------------------------------------------------------------------------------------------------- | --- |
| 1   | **5V**                                                             | OUT | 2   | <p><strong>V-Board</strong><br><strong></strong>Gleiche Spannung wie die Stromversorgung der Hauptplatine</p> | OUT |
| 3   | **GND**                                                            | OUT | 4   | <p><strong>Encoder B</strong><br><strong></strong>Digital</p>                                                 | IN  |
| 5   | **GND**                                                            | OUT | 6   | <p><strong>Encoder A</strong><br><strong></strong>Digital</p>                                                 | IN  |
| 7   | <p><strong>Rotation Speed</strong><br><strong></strong>Analog</p>  | IN  | 8   | <p><strong>Joystick X</strong><br><strong></strong>Analog</p>                                                 | IN  |
| 9   | <p><strong>Feedrate</strong><br><strong></strong>Analog</p>        | IN  | 10  | <p><strong>Joystick Y</strong><br><strong></strong>Analog</p>                                                 | IN  |
| 11  | <p><strong>Motor start</strong><br><strong></strong>Digital</p>    | IN  | 12  | <p><strong>Joystick Z</strong><br><strong></strong>Analog</p>                                                 | IN  |
| 13  | <p><strong>Programm Start</strong><br><strong></strong>Digital</p> | IN  | 14  | <p><strong>ESP Panel LED</strong><br><strong></strong>Digital</p>                                             | OUT |
| 15  | <p><strong>OK</strong><br><strong></strong>Digital</p>             | IN  | 16  | <p><strong>ESP TX2</strong><br><strong></strong>Serieller Ausgang am ESP32</p>                                |     |
| 17  | <p><strong>Auswahl X</strong><br><strong></strong>Digital</p>      | IN  | 18  | <p><strong>ESP RX2</strong><br><strong></strong>Serieller Eingang am ESP32</p>                                |     |
| 19  | <p><strong>Auswahl Y</strong><br><strong></strong>Digital</p>      | IN  | 20  | **3.3V**                                                                                                      | OUT |
| 21  | <p><strong>Auswahl Z</strong><br><strong></strong>Digital</p>      | IN  | 22  | <p><strong>Autosquare</strong><br><strong></strong>Digital</p>                                                | IN  |
| 23  | <p><strong>Speed 1</strong><br><strong></strong>Digital</p>        | IN  | 24  | <p><strong>ENA</strong><br><strong></strong>Digital</p>                                                       | IN  |
| 25  | <p><strong>Speed 2</strong><br><strong></strong>Digital</p>        | IN  | 26  | **GND**                                                                                                       | OUT |

## Technische Daten

| Beschreibung      | Details                                                                                                                       |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Encoder A/B       | Signale eines 5V Encoders                                                                                                     |
| Analoge Eingänge  | Spannung 0-5V                                                                                                                 |
| Digitale Eingänge | Sind mit 10K Ohm Pullup(5V) Widerständen versehen und schalten gegen GND.                                                     |
| ESP Panel LED     | <p>Ist dazu gedacht eine LED am PanelModule zu steuern, welche den Status der Verbindung zum Handrad anzeigt.<br>0 - 3,3V</p> |
| Maße der Module   | 27 mm x 40,68 mm, können bei manchen Modulen abweichen. Das PanelModule Breakout hat z.B. Maße von 34 mm x 40,68 mm.          |

