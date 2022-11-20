---
cover: ../../.gitbook/assets/drivermodule_banner.png
coverY: 0
---

# RJ45 - LAN Anschluss

<div>

<figure><img src="../../.gitbook/assets/driver rj45-2-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/driver rj45-1200px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Mit diesem DriverModule können externe Motortreiber über ein RJ45 Kabel verbunden werden.

### Überblick

* RJ45 Anschluss&#x20;
* Kompatibel zu Beamicon Mapping

### Pinout

![](<../../.gitbook/assets/driver rj45 pin out.png>)

| Pin   | Beschreibung                                                              |
| ----- | ------------------------------------------------------------------------- |
| ENA   | ENA bzw. Enable der Treiber. Dient dazu, die Motoren Stromlos zu schalten |
| STEP  | Signal für die Schritte. Manchmal auch PUL(+) genannt.                    |
| DIR   | Signal für die Richtung.                                                  |
| ALARM | Signal für Fehler am Treiber.                                             |

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/DriverModules/DriverModule%20RJ45" %}
