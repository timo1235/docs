---
cover: ../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# Estlcam Klemmenadapter XL

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-26 104322.png" alt=""><figcaption></figcaption></figure>

Dieser Controller ist speziell für die Verwendung mit der Software [Estlcam ](https://www.estlcam.de/)konzipiert, die von Christian Knüll entwickelt wurde und die Anforderungen im Hobby- und semiprofessionellen Bereich optimal erfüllt. Das Controller-Modul nutzt die neueste Estlcam-Hardware und bietet die erweiterten Funktionen des Klemmenadapters XL.

### Überblick

* 3-Achsen (eine Achse mit zwei individuellen Motoren zum Ausrichten einer Portalfräse über Estlcam)
* 16 Eingänge
* 8 Ausgänge
* 7 analoge Eingänge z.B. für Temperatursensoren, Druckmesser etc.
* Impulsmessung z.B. für Durchflusssensoren...
* Nutzung von originalen Estlcam Mini-Din Handrad oder OCS2 Handrad
* **Verbindung mit dem PC über galvanisch getrenntem USB-C-Anschluss**

### Unterstützung der OCS2 Funktionen

<table><thead><tr><th width="313">Möglichkeiten OCS2</th><th width="432">Unterstützung des Estlcam Adapters</th></tr></thead><tbody><tr><td>6 Achsen</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> Steuerung von 3 Achsen. Die Y-Achse ist auf Y-rechts und Y-Links aufgeteilt. Estlcam bietet für diese Achse eine Autosquaring-Funktion. Weitere Achsen können auf dem <a href="../mainboard-mini/anschluesse-jumper.md#achsenkonfiguration">Shield gleichlaufend konfiguriert </a>werden.</td></tr><tr><td>16 Eingänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> 16 </td></tr><tr><td>8 Ausgänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> 8</td></tr><tr><td>Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Externe Bedienelemente</strong></td><td></td></tr><tr><td>Handrad / Encoder</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Motor Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Programm Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>OK Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Feedrate (Vorschubgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Rotation Speed (Spindelgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>3-Achsen Joystick </td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr></tbody></table>

### Zusätzliche Funktionen direkt auf dem ControllerModule

* 7 analoge Eingänge
  * 3 x Widerstandsmessung (Beschriftung 1R, 2R, 3R)
  * 2 x 0-20mA Strommessung (Beschriftung 4I, 5I)
  * 2 x 0-10V Spannungsmessung (Beschriftung 6U, 7U)
* Anschluss des originalen Estlcam Handrads über eine Mini-Din Buchse
* 5V TTL Signal für einen Stepper Treiber
  * Dieser Ausgang erzeugt präzise getaktete Impulse. Z.B. für Nebelkühlung mit Injektorventilen oder zentrale Schmierstoffdosierung mit Magnetpumpen.
* Frequenz-/Impulszähleingang (5V TTL)
  * Z.B. zur Überwachung des Spindelkühlmittelflusses mit einem Turbinen-Durchflussmesser.

### Achsen Konfiguration

Eine neue Funktion der Estlcam-Hardware ermöglicht die individuelle Steuerung einer Achse mit zwei Motoren. Dies ist besonders bei Portalfräsen nützlich, um die Ausrichtung der Achse präzise einzustellen. Diese Funktion übernimmt die Aufgabe des Autosquarings, das bislang vom OCS2-System bereitgestellt wurde – allerdings nur für eine Achse. Müssen mehrere Achsen ausgerichtet werden, kann dafür weiterhin die [OCS2 Autosquare Funktion](../guides-zubehoer/autosquaring.md) genutzt werden (unbedingt auf die doppelte Y-Achse bei der Konfiguration achten!)&#x20;

| Estlcam Achse | OCS2 Achse |
| ------------- | ---------- |
| X             | X          |
| YL            | Y          |
| YR            | A          |
| Z             | Z          |

### Handrad Jumper

<figure><img src="../../.gitbook/assets/CM_Estlcam_AVR_Handwheel_Jumper.png" alt=""><figcaption></figcaption></figure>

Auf dem Controller-Modul befinden sich vier Jumper, die zur Auswahl des angeschlossenen Handrads verwendet werden. Die Jumper lassen sich entweder auf „OCS Handwheel“ oder „Mini-Din Handwheel“ einstellen.

**OCS Handwheel:** Diese Einstellung ermöglicht die Nutzung des Handrads in Estlcam, das an das OCS2 angeschlossen ist. Dabei spielt es keine Rolle, ob das Handrad über ein Panel-Modul oder per WiFi verbunden ist. \
_Technische Umsetzung (Hintergrundinformation): Auf dem Controller-Modul ist ein Atmega328 integriert, der die Signale vom OCS2 (Joystick, Taster etc.) einliest und über I2C an Estlcam weiterleitet – genauso wie es das originale Estlcam-Handrad macht._

**Mini-Din Handwheel:** In dieser Jumperstellung kann das originale Estlcam-Handrad mit Mini-Din-Stecker genutzt werden.

{% hint style="info" %}
**Hinweis für beide Varianten:** Zuerst die Stromversorgung einschalten und das Handrad anschließen, dann Estlcam starten und die Steuerung programmieren. Im „Programmierfenster“ von Estlcam sollte dann eine Meldung wie „Zusatzmodul Handrad 001“ erscheinen. \
\
Es ist außerdem nicht möglich, das Mini-Din-Handrad und ein OCS2-Handrad gleichzeitig zu verwenden. Nur eines von beiden kann genutzt werden.
{% endhint %}

### Pin Mapping

Hier einmal eine Übersicht über die Funktionen und Pins

| Klemmenadapter Pin | OCS2 Pin                           | zusätzliche Info                                                                        |
| ------------------ | ---------------------------------- | --------------------------------------------------------------------------------------- |
| Eingänge 1-16      | Eingänge 1-16 an den InOut-Modulen | [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention") |
| Ausgänge 1-8       | Ausgänge 1-8 an den InOutModulen   | [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention") |
| Ausgang 9          | ENA                                | mit Ausgang 9 in Estlcam kann der Enable der Treiber auf dem OCS2 geschaltet werden     |
| STEP X             | STEP X                             |                                                                                         |
| DIR X              | DIR X                              |                                                                                         |
| STEP YL            | STEP Y                             |                                                                                         |
| STEP YR            | STEP A                             |                                                                                         |
| DIR Y              | DIR Y, DIR A                       |                                                                                         |
| STEP Z             | STEP Z                             |                                                                                         |
| DIR Z              | DIR Z                              |                                                                                         |

### Analoge Eingänge auf dem ControllerModule

Es gibt insgesamt 7 analoge Eingänge auf dem ControllerModule, darunter

* 3 x Widerstandsmessung (Beschriftung 1R, 2R, 3R)
* 2 x 0-20mA Strommessung (Beschriftung 4I, 5I)
* 2 x 0-10V Spannungsmessung (Beschriftung 6U, 7U)

### Frequenz-/Impulszähleingang - 5V TTL (FRQ)

\-- Coming soon --

### 5V TTL Impulsausgang(FogPulse)

Dieser Ausgang erzeugt präzise getaktete Impulse. Z.B. für Nebelkühlung mit Injektorventilen oder zentrale Schmierstoffdosierung mit Magnetpumpen.

### Technische Details

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/ControllerModules/ControllerModule%20Estlcam%20KLemmenadapter%20XL" %}

