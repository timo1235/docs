---
cover: ../../.gitbook/assets/OCS2 Mini-4-osc2-mini-banner.png
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Mainboard Mini

## Kurzbeschreibung

Das OPEN-CNC-Shield 2 Mini ist die kompakte und kosteneffiziente Weiterentwicklung des erfolgreichen OPEN-CNC-Shield 2. Trotz seiner geringeren Größe bietet es umfassende Funktionen und ist vollständig kompatibel mit allen Controller- und Panelmodulen des großen Bruders. Dank fest verbautem ESP32 und identischer Firmware bleiben die erweiterten Funktionen erhalten. Das Shield eignet sich ideal für den Hobby- und semiprofessionellen Einsatz.

#### Kurzübersicht der Features(Kann je nach Controller auch abweichen):

* 100 % kompatibel zu allen [ControllerModules](../controllermodules/)
* 100 % kompatibel zu allen [PanelModules](../panelmodules/)
* Fest verbauter ESP32:&#x20;
  * Die gleiche Firmware wie beim OPEN-CNC-Shield 2 Mainboard
  * Autosquaring der Achsen
  * Temperaturüberwachung
  * Wi-Fi Bedienpanel
  * individuelle Programmierung möglich
* 5 Achsen möglich:
  * &#x20;Ideal für vielfältige Anwendungen und Erweiterungen.
  * Achsenkonfiguration zum Einrichten gleichlaufender Achsen
* 8 Eingänge: Flexibel beschaltbar mit GND oder VCC.
* 6 Ausgänge: Für vielseitige Steuerungsmöglichkeiten.
* Kostenersparnis: Keine zusätzlichen [InOutModule ](../inoutmodules/)erforderlich, sowie keine [DriverModule ](../drivermodules/)notwendig. Es sollten externe Treiber verwendet werden, vergleichbar mit dem Arduino Club Board oder dem Estlcam Klemmenadapter.
* Spindelgeschwindigkeitssteuerung mit 0-5V, 0-10V oder 5V PWM
* Spindel An-/Aus Anschluss zum Schalten eines Relais
* Genug Anschlussmöglichkeiten für externe Bedienelemente wie Bedienpults, Handräder etc.

## Board Übersicht

<figure><img src="../../.gitbook/assets/ocs2-mini.png" alt=""><figcaption></figcaption></figure>

Die Hauptplatine ist in mehrere Bereiche unterteilt. Es gibt Steckplätze für folgende Module:

* 1 x Controller Module
* 1 x Panel Module

Diese werden in den nächsten Abschnitten genauer erklärt. Es müssen nicht alle Module besetzt bzw. genutzt werden.&#x20;

### Technische Details

Die schematischen Zeichnungen und DXF Files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20mainboard" %}

<figure><img src="../../.gitbook/assets/OCS2 Mini-5-dimensions.png" alt=""><figcaption></figcaption></figure>



