# Anschlüsse / Jumper

Neben den Steckplätzen für die Erweiterungen bietet das Mainboard verschiedene Anschlüsse und Jumper.

### Stromversorgung

<figure><img src="../../.gitbook/assets/OCS2 mini-Power.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="197">Beschriftung</th><th width="300">Funktion</th><th>Technisches</th></tr></thead><tbody><tr><td>12-32V IN - GND</td><td>GND</td><td></td></tr><tr><td>12-32V IN - VCC</td><td>Stromversorgung für das Shield inkl. Erweiterungen</td><td>Spannung: 12-32V <br>Strom: etwa 1A </td></tr></tbody></table>

### Spindel / Motor / Laser Steuerung

<figure><img src="../../.gitbook/assets/OCS2 mini-Spindel.png" alt=""><figcaption></figcaption></figure>

Diese Anschlüsse können für die Steuerung einer Spindel oder eines Lasers genutzt werden.&#x20;

<table><thead><tr><th width="203">Beschriftung</th><th width="334">Funktion</th><th>Technisches</th></tr></thead><tbody><tr><td>Spindle Relais OUT</td><td>Open-Collector Ausgang für das Signal "Spindle on/off". Hier liegt im geschalteten Zustand GND an.</td><td>max. 500mA </td></tr><tr><td>COM2</td><td>Spannung für den Open-Collector Ausgang "Spindel Relais OUT". Kann am Jumper JP3 eingestellt werden. Mögliche Spannung ist dort 5V oder V-Board  - also die Spannung, die am Board anliegt. Es kann auch eine eigene Spannung angelegt werden.</td><td>Entweder 5V, V-Board oder eigene Spannung - max. 50V(ULN2003 IC)</td></tr><tr><td>PWM</td><td>PWM Signal zur Steuerung der Leistung von z.B. Lasern.</td><td>5V PWM</td></tr><tr><td>VCC</td><td>Analoge Spannung für die Spindel Geschwindigkeit. Diese wird aus dem PWM Signal erzeugt und kann am Jumper JP2 entweder auf 0-5V oder auf 0-10V eingestellt werden.<br>Dieser Ausgang kann mit dem Drehpotentiometer kalibriert werden. Dazu in dem Controller(z.b. Estlcam) die Spindel voll aufdrehen und mit einem Messgerät zwischen VCC und GND messen. Durch Verstellen des Potis lässt sich die Spannung auf 10V einstellen.</td><td>0-5V oder 0-10V</td></tr><tr><td>GND</td><td>GND</td><td></td></tr><tr><td>DCM</td><td>Wird beim FU an "DCM" oder "GND" oder ähnlichem angeschlossen.</td><td>Siehe "FOR"</td></tr><tr><td>FOR</td><td>Galvanische getrennter Ausgang für Frequenzumrichter(FU). Wird bei dem FU an "vorwärts" oder "start" oder ähnlichem angeschlossen. DCM muss ebenfalls angeschlossen werden.</td><td><img src="../../.gitbook/assets/for_dcm.png" alt=""></td></tr></tbody></table>

{% hint style="info" %}
Für den Anschluss diverser Spindeln gibt es hier Bespiele: [spindel-laser-fu-motor-anschluss.md](../guides-zubehoer/spindel-laser-fu-motor-anschluss.md "mention")
{% endhint %}

### Motortreiber

Für die Steuerung von Motoren werden externe Treiber benötigt. Die Platine arbeitet mit 5V Steuersignalen - manche Treiber besitzen einen DIP-Schalter für die Steuerspannung. Dieser muss entsprechend eingestellt sein.

Alle Achsen besitzen folgende Anschlüsse:

| Anschluss | Funktion                                               |
| --------- | ------------------------------------------------------ |
| STEP      | Signal für die Schritte. Manchmal auch PUL(+) genannt. |
| DIR       | Signal für die Richtung.                               |
| GND       | GND                                                    |

Außerdem gibt es zwei Anschluss-Terminals für ENA ( bzw. Enable der Treiber) welcher dazu, dient die Motoren Stromlos zu schalten. Alle Motoren teilen sich die ENA Anschlüsse. Möchte man die Enable Funktion nutzen, kann jeder Motortreiber an die ENA Leitung angeschlossen werden.

### Eingänge

* Eingänge schalten entweder mit GND/Masse oder mit 5-24V (über einen Switch direkt auf der Platine umschaltbar)
* Anzeige der aktuellen Stati über LEDs

{% hint style="info" %}
**Damit die Eingänge funktionieren, muss eine Spannung am Jumper JP4(COM1) ausgewählt sein! Im normalfall sollte der Jumper auf 5V gesteckt werden.**
{% endhint %}

Siehe das Kapitel [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention") für weitere Informationen und Beispielen für die Beschaltung.

### Ausgänge

* Ausgänge sind mit Darlington Relays versehen - **schalten also GND/Masse an den OUTs**
* 500mA pro Ausgang
* COM-Spannung für Ausgänge wählbar zwischen 5V und Eingangsspannung des Shields (normalerweise 24V)
* Anzeige der aktuellen Stati über LEDs

Die Spannung der Ausgänge wird am Jumper JP3(COM2) gesetzt.

{% hint style="info" %}
Beachte, dass die Ausgänge GND schalten! Das bedeutet, dass die Terminals folgendermaßen verdrahtet werden müssen:\
\- COM2 an den positiven Anschluss (+) des Relais\
\- OUT an GND des Relais
{% endhint %}

Siehe das Kapitel [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention") für weitere Informationen und Beispielen für die Beschaltung.

### Jumper und sonstige Anschlüsse

<table><thead><tr><th width="189">Beschriftung</th><th>Funktion</th></tr></thead><tbody><tr><td><p>JP1<br>ENA-Jumper <br>Beschriftung:</p><p><strong>5V/ENA/GND</strong></p></td><td>Jumper für den Enable der Treiber. Kann gesetzt werden, wenn die Treiber selbst keinen Pullup oder Pulldown Widerstand besitzen.<img src="../../.gitbook/assets/ena.png" alt=""><br>Gilt für alle Treiber.</td></tr><tr><td>JP2<br>Spindel-Jumper<br>Beschriftung: <strong>10V/Sp/5V</strong></td><td>Jumper für den analogen Spindel Ausgang. Wählt zwischen 0-5V und 0-10V</td></tr><tr><td>JP3<br>OUT Jumper<br>Beschriftung:<br><strong>VIN/COM2/5V</strong></td><td>Wählt die Spannung für die Ausgänge 1-6 und den "Spindel Relais OUT" bzw. die Open-Collector Spannung "COM2". Wahlmöglichkeiten sind 5V oder die Boardspannung V-Board. Wenn der Jumper frei gelassen wird, kann auch eine eigene Spannung bis 50V angelegt werden. </td></tr><tr><td>J2<br>Temp-Stecker</td><td>Anschluss für einen oder mehrere DS18B20 Temperatursensoren. Diese können mit dem ESP32 ausgelesen werden.</td></tr></tbody></table>

### General Pinout

<figure><img src="../../.gitbook/assets/OCS2 mini-General-Pinout.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80">Pin</th><th>Funktion</th><th width="67">Pin</th><th>Funktion</th></tr></thead><tbody><tr><td>1</td><td>ENA</td><td>2</td><td>5V</td></tr><tr><td>3</td><td>DAC_08</td><td>4</td><td>GND</td></tr><tr><td>5</td><td>DAC_06</td><td>6</td><td>DAC_A07</td></tr></tbody></table>

### ESP32 Pinout

<figure><img src="../../.gitbook/assets/OCS2 mini-ESP32-Pinout.png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80">Pin</th><th>Funktion</th><th width="67">Pin</th><th>Funktion</th></tr></thead><tbody><tr><td>1</td><td>+5V </td><td>2</td><td>GND</td></tr><tr><td>3</td><td>ESP32_D35</td><td>4</td><td>ESP32_D19</td></tr><tr><td>5</td><td>ESP32_D34 - Fn</td><td>6</td><td>ESP32_D4</td></tr><tr><td>7</td><td>Autosquare (siehe Hinweis unten)</td><td>8</td><td>ESP32_D2</td></tr><tr><td>9</td><td>ESP32_SCL</td><td>10</td><td>ESP32_SDA</td></tr><tr><td>11</td><td>ESP32_TX</td><td>12</td><td>ESP32_RX</td></tr></tbody></table>

{% hint style="info" %}
Um die Autosquare-Funktion an diesem Pinout zu nutzen muss ein Schalter/Taster zwischen GND und dem Autosquare-Pin angeschlossen werden. Dieser Taster kann parallel zum Autosquare Button des Bedienpanels/Wifi Panels genutzt werden.
{% endhint %}

### Achsenkonfiguration

Diese Pin Leisten können mit Jumpern versehen werden, um Achsen **unabhängig vom verwendeten Controller** gleich laufen zu lassen. Die Konfiguration keinen Einfluss auf die Funktionalität des Autosquaring vom ESP32. Die Achsen-Einstellungen für das Autosquaring werden direkt in der Software des ESP32 getätigt.

<figure><img src="../../.gitbook/assets/OCS2 mini-Axis-Config.png" alt=""><figcaption></figcaption></figure>

Bei einigen Controllern, wie zum Beispiel FluidNC, können gleichlaufende Achsen direkt in der Software des Controllers konfiguriert werden. Bei anderen, wie Estlcam, ist dies nicht möglich. In diesen Fällen können die Pin-Header verwendet werden, um die Achsen entsprechend zu konfigurieren.

#### Beispiel Estlcam mit zwei X und zwei Y Achsen

Estlcam kann nur 3 Achsen steuern: X, Y und Z. Bei einer Fräse mit zwei Motoren auf einer Achse, wie beispielsweise der MPCNC oder LowRider, können die Achsen synchron betrieben werden. Im folgenden Bild sind die Jumper so gesteckt, dass die Achse A synchron mit der X-Achse und die Achse B synchron mit der Y-Achse läuft.

<figure><img src="../../.gitbook/assets/OCS2 mini-Axis-Config-MPCNC.png" alt=""><figcaption><p>Rote Balken stellen die Jumper dar</p></figcaption></figure>

#### Beispiel Beamicon mit 4 Achsen und zwei Motoren auf X

Die CNC-Pod Controller von Beamicon unterstützen 4 Achsen: X, Y, Z und A. Daher sollte die A-Achse nicht für die Konfiguration verwendet werden. Die B-Achse ist jedoch frei. Der zweite Motor für die X-Achse kann beispielsweise auf die B-Achse gelegt werden. Das folgende Bild zeigt die Jumper-Einstellung dafür.

<figure><img src="../../.gitbook/assets/OCS2 mini-Axis-Config-beamicon.png" alt=""><figcaption><p>Rote Balken stellen die Jumper dar</p></figcaption></figure>

### Buttons / Taster

Es gibt drei Taster auf der Platine, welche für den integrierten ESP32 sind.

<figure><img src="../../.gitbook/assets/OCS2 mini-Buttons.png" alt=""><figcaption></figcaption></figure>

| Taster   | Funktion                                                                                                                                                                                        |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reset    | Typischer ESP32 Taster - startet den ESP32 neu                                                                                                                                                  |
| Boot     | Typischer ESP32 Taster - versetzt den ESP32 in den Boot Modus (muss eigentlich nie benutzt werden)                                                                                              |
| Function | <p>Mit PIN D34 des ESP32 verbunden. <br>Wenn die OCS2 Firmware auf den ESP32 aufgespielt ist, kann hiermit das Webinterface manuell gestartet werden, falls dieses zuvor deaktiviert wurde.</p> |
