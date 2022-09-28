# InOut Module

{% hint style="info" %}
Diese Seite ist für die Entwicklung neuer InOut Module und die Fehlersuche relevant.  Für die unterschiedlichen InOut Module gibt es eigene Dokumentationsseiten. Dort werden die unterstützten Features und technische Details der einzelnen Module beschrieben. [inoutmodules](../../inoutmodules/ "mention")
{% endhint %}

Das InOutModule ist für die Ein- und Ausgänge der Platine zuständig. Die verschiedenen InOut Module unterscheiden sich in der Anschlussart und Ausstattung. Einige haben steckbare Anschlüsse, andere nutzen Federklemmen-Anschlüsse. Auch gibt es Varianten mit bereits installierten Relais zum Anschluss von geschalteten Verbrauchern.

## Pin Belegung

<figure><img src="../../../../.gitbook/assets/inout pin ma.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typ OUT: Das Signal geht vom Controller / Steuerungssoftware in Richtung InOutModule

Typ IN: Das Signal kommt vom InOutModule und geht zum Controller / der Steuerung
{% endhint %}

### **InOut  1:**

| Pin | Beschreibung                                                                                                  | Typ | Pin | Beschreibung  | Typ |
| --- | ------------------------------------------------------------------------------------------------------------- | --- | --- | ------------- | --- |
| 1   | **Ausgang 1**                                                                                                 | OUT | 2   | **Eingang 8** | IN  |
| 3   | **Ausgang 2**                                                                                                 | OUT | 4   | **Eingang 7** | IN  |
| 5   | **Ausgang 3**                                                                                                 | OUT | 6   | **Eingang 6** | IN  |
| 7   | **Ausgang 4**                                                                                                 | OUT | 8   | **Eingang 5** | IN  |
| 9   | **5V**                                                                                                        | OUT | 10  | **Eingang 4** | IN  |
| 11  | <p><strong>V-Board</strong><br><strong></strong>Gleiche Spannung wie die Stromversorgung der Hauptplatine</p> | OUT | 12  | **Eingang 3** | IN  |
| 13  | **GND**                                                                                                       | OUT | 14  | **Eingang 2** | IN  |
| 15  | **GND**                                                                                                       | OUT | 16  | **Eingang 1** | IN  |

### **InOut 2:**

| Pin | Beschreibung                                                                                                  | Typ | Pin | Beschreibung   | Typ |
| --- | ------------------------------------------------------------------------------------------------------------- | --- | --- | -------------- | --- |
| 1   | **Ausgang 5**                                                                                                 | OUT | 2   | **Eingang 16** | IN  |
| 3   | **Ausgang 6**                                                                                                 | OUT | 4   | **Eingang 15** | IN  |
| 5   | **Ausgang 7**                                                                                                 | OUT | 6   | **Eingang 14** | IN  |
| 7   | **Ausgang 8**                                                                                                 | OUT | 8   | **Eingang 13** | IN  |
| 9   | **5V**                                                                                                        | OUT | 10  | **Eingang 12** | IN  |
| 11  | <p><strong>V-Board</strong><br><strong></strong>Gleiche Spannung wie die Stromversorgung der Hauptplatine</p> | OUT | 12  | **Eingang 11** | IN  |
| 13  | **GND**                                                                                                       | OUT | 14  | **Eingang 10** | IN  |
| 15  | **GND**                                                                                                       | OUT | 16  | **Eingang 9**  | IN  |

## Technische Daten

| Beschreibung    | Details                                                                                                                    |
| --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Eingänge 1-16   | Die Eingänge sind typischerweise mit Pullup Widerständen versehen. Dies ist allerdings auch vom ControllerModule abhängig. |
| Ausgänge 1-8    | Die Ausgänge sind auf dem Mainboard mit 4,7K Ohm Pulldown Widerständen versehen.                                           |
| Maße der Module | 75 mm x 67,5 mm                                                                                                            |

