# Driver Module

{% hint style="info" %}
Diese Seite ist für die Entwicklung neuer Driver Module und die Fehlersuche relevant.  Für die unterschiedlichen Driver Module gibt es eigene Dokumentationsseiten. Dort werden die unterstützten Features und technische Details der einzelnen Module beschrieben. [drivermodules](../../drivermodules/ "mention")
{% endhint %}

Die Driver Module sind für die Verbindung der Steuerung mit den verschiedenen Motortreibern. Je nachdem, was für Treiber an der Maschine eingesetzt werden, eignen sich andere Driver Module.

## Pin Belegung

<figure><img src="../../../../.gitbook/assets/driver pin map.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typ OUT: Das Signal geht vom Controller / Steuerungssoftware in Richtung DriverModule

Typ IN: Das Signal kommt vom DriverModule und geht zum Controller / der Steuerung
{% endhint %}

### **Anschluss:**

| Pin | Beschreibung                                                              | Typ | Pin | Beschreibung                                                                                            | Typ |
| --- | ------------------------------------------------------------------------- | --- | --- | ------------------------------------------------------------------------------------------------------- | --- |
| 1   | **GND**                                                                   | OUT | 2   | <p><strong>V-Mot</strong><br><strong></strong>Hier liegt die Spannung der Motor Stromversorgung an.</p> | OUT |
| 3   | <p><strong>ENA</strong><br><strong></strong>Enable <strong></strong> </p> | OUT | 4   | **5V**                                                                                                  | OUT |
| 5   | <p><strong>ALARM</strong><br><strong></strong>Alarmausgang</p>            | IN  | 6   | <p><strong>DIR</strong><br><strong></strong>Richtungssignal</p>                                         | OUT |
| 7   | <p><strong>STEP</strong><br><strong></strong>Schrittsignal</p>            | OUT | 8   | **-**                                                                                                   | -   |

## Technische Daten

| Beschreibung    | Details                                       |
| --------------- | --------------------------------------------- |
| STEP            | Gepufferte Schrittsignale. 5V mit max. 20mA   |
| DIR             | Gepufferte Richtungssignale. 5V mit max. 20mA |
| Maße der Module | 22 mm x 35 mm                                 |

