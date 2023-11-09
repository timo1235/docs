---
cover: ../../.gitbook/assets/mainboard_banner.png
coverY: 0
---

# Mainboard

## Kurzbeschreibung

Das OPEN-CNC-Shield 2 ist eine Weiterentwicklung des ersten OPEN-CNC-Shields. Die Steuerung besteht aus einer Hauptplatine (Mainboard) und beliebigen Erweiterungen. Dadurch ist sie vielseitig einsetzbar und individuell konfigurierbar. Die Platine ist zu großen teilen SMD gefertigt und die Schaltpläne sind öffentlich einsehbar.&#x20;

Durch die Möglichkeit verschiedener Controller Module ist der Einsatz mit verschiedenen Steuerungssoftwares möglich. Ausgelegt ist die Platine für den hobby- und semiprofessionellen Einsatz. Auch bei dieser Version des Shields ist es möglich, zunächst klein mit z.B. Aufstecktreibern  anzufangen und dann im späteren aufzurüsten.&#x20;

#### Kurzübersicht der Features(Kann je nach Controller auch abweichen):

* 6 Achsen möglich
* Achsenkonfiguration zum Einrichten gleichlaufender Achsen
* 16 Eingänge und 8 Ausgänge im Standard
* Spindelgeschwindigkeitssteuerung mit 0-5V, 0-10V oder 5V PWM
* Spindel An-/Aus Anschluss zum Schalten eines Relais
* Treiberstrom für Aufstecktreiber auch unabhängig vom Boardstrom möglich (z.B. 24V Board und 40V Treiber)
* Genug Anschlussmöglichkeiten für externe Bedienelemente wie Bedienpults, Handräder etc.
* Onboard ESP32 für verschiedene Aufgaben
  * Autosquaring der Achsen
  * Temperaturüberwachung
  * Wi-Fi Bedienpanel
  * individuelle Programmierung möglich

## Board Übersicht

<figure><img src="../../.gitbook/assets/DSC00665.jpg" alt=""><figcaption></figcaption></figure>

Die Hauptplatine ist in mehrere Bereiche unterteilt. Es gibt Steckplätze für folgende Module:

* 1 x Controller Module
* 2 x InOut Module
* 6 x Driver Module
* 1 x Panel Module

Diese werden in den nächsten Abschnitten genauer erklärt. Es müssen nicht alle Module besetzt bzw. genutzt werden. Benötigt man beispielsweise nicht alle Ein- und Ausgänge reicht es auch, nur ein InOut Module zu nutzen.

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20mainboard" %}

###



###





