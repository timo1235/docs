# Anschlüsse / Jumper

Neben den Steckplätzen für die Erweiterungen bietet das Mainboard verschiedene Anschlüsse und Jumper.

### Stromversorgung

<figure><img src="../../../.gitbook/assets/power.png" alt=""><figcaption></figcaption></figure>

| Beschriftung | Funktion                                                                                                                                                                                                  | Technisches                                                               |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Board GND    | GND                                                                                                                                                                                                       |                                                                           |
| Board VCC    | Stromversorgung für das Shield inkl. Erweiterungen                                                                                                                                                        | <p>Spannung: 12-24V <br>Strom: etwa 3A </p>                               |
| Driver GND   | GND                                                                                                                                                                                                       |                                                                           |
| Driver VCC   | Stromversorgung ausschließlich für die Aufstecktreiber. Kann die gleiche Spannung wie das Board besitzen - Es kann aber auch eine andere Spannung genutzt werden. Zum Beispiel Board 24V und Treiber 40V. | <p>max. 50V<br>Unbedingt das Datenblatt der Aufstecktreiber beachten!</p> |

### Spindel / Motor / Laser Steuerung

<figure><img src="../../../.gitbook/assets/spindel.png" alt=""><figcaption></figcaption></figure>

Diese Anschlüsse können für die Steuerung einer Spindel oder eines Lasers genutzt werden.&#x20;

| Beschriftung | Funktion                                                                                                                                                                                                                       | Technisches                                                      |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------- |
| GND          | GND                                                                                                                                                                                                                            |                                                                  |
| OUT          | Open-Collector Ausgang für das Signal "Spindle on/off". Hier liegt im geschalteten Zustand GND an.                                                                                                                             | max. 500mA                                                       |
| COM          | Spannung für den Open-Collector Ausgang "OUT". Kann am Jumper JP3 eingestellt werden. Mögliche Spannung ist dort 5V oder V-Board  - also die Spannung die am Board anliegt. Es kann auch eine eigene Spannung angelegt werden. | Entweder 5V, V-Board oder eigene Spannung - max. 50V(ULN2003 IC) |
| GND          | GND                                                                                                                                                                                                                            |                                                                  |
| VCC          | Analoge Spannung für die Spindel Geschwindigkeit. Diese wird aus dem PWM Signal erzeugt und kann am Jumper JP2 entweder auf 0-5V oder auf 0-10V eingestellt werden.                                                            | 0-5V oder 0-10V                                                  |
| PWM          | PWM Signal zur Steuerung der Leistung von z.B. Lasern.                                                                                                                                                                         | 5V PWM                                                           |
| FOR          | Galvanische getrennter Ausgang für Frequenzumrichter(FU). Wird bei dem FU an "vorwärts" oder "start" oder ähnlichem angeschlossen. DCM muss ebenfalls angeschlossen werden.                                                    | ![](../../../.gitbook/assets/for\_dcm.png)                       |
| DCM          | Wird beim FU an "DCM" oder "GND" oder ähnlichem angeschlossen.                                                                                                                                                                 | Siehe "FOR"                                                      |

### Jumper und sonstige Anschlüsse

| Beschriftung | Funktion                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JP1          | <p>Jumper für den Enable der Treiber. Kann gesetzt werden, wenn die Treiber selbst keinen Pullup oder Pulldown Widerstand besitzen.<img src="../../../.gitbook/assets/ena.png" alt=""><br>Gilt für alle Treiber.</p>                                                                                                                                                                                                        |
| JP2          | Jumper für den analogen Spindel Ausgang. Wählt zwischen 0-5V und 0-10V                                                                                                                                                                                                                                                                                                                                                      |
| JP3          | Wählt die Spannung für den "Spindel on/off" Ausgang bzw. die Open-Collector Spannung "COM". Wahlmöglichkeiten sind 5V oder die Boardspannung V-Board. Wenn der Jumper frei gelassen wird, kann auch eine eigene Spannung bis 50V angelegt werden.                                                                                                                                                                           |
| J1           | Anschluss eines 2-Pin oder 3-Pin 12V Lüfters.                                                                                                                                                                                                                                                                                                                                                                               |
| J2           | Anschluss für einen oder mehrere DS18B20 Temperatursensoren. Dies können mit dem ESP32 ausgelesen werden.                                                                                                                                                                                                                                                                                                                   |
| J3           | <p>Verbindet die Board Spannung mit der Motortreiber Spannung.<br>Achtung:<br>- nur nutzen, wenn die Aufstecktreiber weniger als 2A nutzen(zum Beispiel nur die z-Achse ist mit einem Aufstecktreiber versehen)<br>- nur nutzen, wenn Driver VCC und Driver GND nicht verbunden sind<br><strong>Eine Kabelbrücke oder ein extra Netzteil an den Anschlüssen Driver GND und Driver VCC ist immer zu bevorzugen</strong>.</p> |

### Achsenkonfiguration

Diese Pin Leisten können mit Jumpern versehen werden, um Achsen **unabhängig vom verwendeten Controller** gleich laufen zu lassen. Ebenfalls hat die Konfiguration keinen Einfluss die Funktionalität des Autosquaring vom ESP32. Die Achsen-Einstellungen für das Autosquaring werden direkt in der Software des ESP32 getätigt.

<figure><img src="../../../.gitbook/assets/axis.png" alt=""><figcaption></figcaption></figure>

Bei einigen Controllern kann man gleichlaufende Achsen direkt in der Software des Controllers einstellen, aber bei manchen auch nicht. Dafür können dann diese Pin-Header genutzt werden.

#### Beispiel Estlcam mit zwei X und zwei Y Achsen

Estlcam kann nur 3 Achsen steuern. X, Y und Z. Hat man nun aber eine Fräse mit zwei Motoren auf einer Achse wie zum Beispiel der MPCNC oder der LowRider kann man hier die Achsen gleich laufend einstellen. Im folgenden Bild sind die Jumper so gesteckt, dass die Achse A gleichlaufend mit der x-Achse und die Achse B gleichlaufend mit der y-Achse ist.

<figure><img src="../../../.gitbook/assets/as_x_y.png" alt=""><figcaption></figcaption></figure>

#### Beispiel Beamicon mit 4 Achsen und zwei Motoren auf X

Die CNC-Pod Controller von Beamicon unterstützt 4 Achsen. Die belegten Achsen sind X, Y, Z und A. Daher sollte die a-Achse nicht mehr für die Konfiguration verwendet werden. Aber die b- und c-Achse sind frei. Demnach kann man den zweiten Motor für die x-Achse zum Beispiel auf die b-Achse legen. Das folgende Bild zeigt die Jumper-Einstellung dafür.

<figure><img src="../../../.gitbook/assets/as_x.png" alt=""><figcaption></figcaption></figure>
