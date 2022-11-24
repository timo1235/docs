# ESP32 Panel Platine

<div>

<figure><img src="../.gitbook/assets/esp32 panel-2-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/esp32 panel-3-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/esp32 panel-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Handrad-1200px (1).jpg" alt=""><figcaption></figcaption></figure>

</div>

Die ESP32 Panel Platine ist für den Bau externer Bedienelemente gedacht. Der ESP32 auf der Platine kommuniziert dabei über WiFi mit dem OPEN-CNC-Shield 2. Der Funktionsumfang ist dabei auf die Verwendung mit dem Estlcam ControllerModule zugeschnitten. Wird ein anderer Controller genutzt, kann der Funktionsumfang stark eingeschränkt sein. Dazu bitte die Dokumentation der einzelnen ControllerModule beachten.

### Überblick

* WiFi kommunikation - 2,4GHz - ESPNOW Protokoll
* Stromversorgung über RJ45
* Eigene Signalleitung für den Encoder im RJ45 Kabel (das Encoder Signal wird nicht per WiFi übertragen)
* Stromversorgung durch Powerbank möglich
* Laden der Powerbank möglich (mit RJ45 Verbindung zum OPEN-CNC-Shield 2)
* Verschiedene, optionale Anschlussmöglichkeiten:
  * 4Pin - 5V Encoder
  * Joystick mit 3 Achsen und OK-Taster (zum Abnullen der Achsen)
  * Motor Start/Stop Taster
  * Programm Start/Stop Taster
  * Feedrate Poti (Vorschubgeschwindigkeit)
  * Rotation Speed Poti (Spindelgeschwindigkeit)
  * Autosquare Taster
  * Auswahl X, Y und Z (zur Auswahl der Achse für den Encoder)
  * 4 freie Buttons (kann zum Beispiel für die Stromlos-Funktion oder Speed1, Speed2 genutzt werden. Es können auch die Outputs 1-4 des OPEN-CNC-Shields 2 geschaltet werden)
  * Anschluss für I2C, typischerweise für ein Display

### Technische Details

| Eigenschaft       | Wert / Beschreibung                            |
| ----------------- | ---------------------------------------------- |
| Maße              | 65 mm x 56 mm x 19 mm(mit ESP32 bestückt)      |
| Digitale Eingänge | Interne Pullups - Schalten im Standard mit GND |
| Analoge Eingänge  | Spannung von 0-3,3V                            |

Schematische Darstellung und DXF Dateien zu der Platine sind auf Github zu finden:&#x20;

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/ESP32%20Panel%20PCB" %}

#### Stromversorgung

| Szenario                                                                                                                                | Beschreibung                                                                                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Szenario 1:<br>Nur RJ45 Kabel zur Stromversorgung.<br>Keine Powerbank</p>                                                            | Jumper JP1 und JP2 setzen. Das Bedienteil ist dann immer an, wenn Strom da ist                                                                                                    |
| <p>Szenario 2:<br>Powerbank für die Platine. Die Powerbank wird anderweitig geladen (z.B. Wireless Charger)</p>                         | Keine Jumper setzen. Powerbank mit dem USB-C IN Eingang verbinden. Ein An/Aus Schalter wird benötigt.                                                                             |
| <p>Szenario 3:<br>Powerbank für die Platine. Die Powerbank wird auch über die Platine geladen, wenn ein RJ45 Kabel angesteckt wird.</p> | Keine Jumper setzen. Powerbank mit dem USB-C IN Eingang verbinden. Zweites USB Kabel vom USB-A Anschluss zum Ladeeingang der Powerbank ziehen. Ein An/Aus Schalter wird benötigt. |

### Jumper

|     |                                                                                                                                                                                                                                                                                                                                      |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| JP1 | <p>Steuert die Stromversorgung. Diese Jumper muss gesetzt werden, wenn am USB-C IN Eingang nichts angeschlossen ist. Der Strom für den ESP32 wird dann aus dem RJ45 Kabel genommen. Kurz gesagt:<br><strong>Den Jumper setzen, wenn keine Powerbank angeschlossen wird und das Bedienteil per RJ45 Kabel bestromt wird.</strong></p> |
| JP2 | Dieser Jumper überbrückt den An/Aus Schalter. Wenn kein Schalter eingebaut wird, kann dieser Jumper gesetzt werden. Dann ist das Bedienteil immer an, wenn Strom anliegt.                                                                                                                                                            |

### Software / Firmware

Die Firmware kann auf Github heruntergeladen werden:&#x20;

{% embed url="https://github.com/timo1235/-ocs2.x-esp32-panel-software-" %}

Die Einstellungsmöglichkeiten sind in der \`configuration.h\` Datei zu finden.

### Beispiel Projekte

| Bild                                       | Beschreibung          | Links                                                                                                                                                                                           |
| ------------------------------------------ | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![](../.gitbook/assets/Handrad-1200px.jpg) | Handrad mit Powerbank | <ul><li><a href="https://blog.altholtmann.com/cnc-handrad-open-cnc-shield-2/">Blog Post mit Anleitung</a></li><li><a href="https://www.thingiverse.com/thing:5641305">Thingiverse</a></li></ul> |
