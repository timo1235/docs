# Pinbelegung

Der ESP32 Mikroprozessor kann zur individuellen Programmierung von Funktionen genutzt werden. Dabei spielt es meist keine Rolle, welcher Controller / Software genutzt wird. Zum Beispiel die Autosquaring Funktion wird von dem ESP32 ausgeführt und ist damit Controller unabhängig.

## Pin Belegung

<figure><img src="../../../../.gitbook/assets/esp32 pin map.jpg" alt=""><figcaption></figcaption></figure>

### **ESP32 pin map:**

| ESP Pin | Mainboard Pin | Funktion                                                                                                       |
| ------- | ------------- | -------------------------------------------------------------------------------------------------------------- |
| EN      | **-**         |                                                                                                                |
| GPIO36  | IO INT 1      | Interrupt Eingang von PortExpander 1                                                                           |
| GPIO39  | IO INT 2      | Interrupt Eingang von PortExpander 1                                                                           |
| GPIO34  | ESP D34       | Freier Pin am ESP Pinout                                                                                       |
| GPIO35  | ESP D35       | Freier Pin am ESP Pinout                                                                                       |
| GPIO32  | ESP D32       | Freier Pin am ESP Pinout                                                                                       |
| GPIO33  | DAC LD        | LD vom DAC Expander                                                                                            |
| GPIO25  | DS18B20       | Temperatur Sensor                                                                                              |
| GPIO26  | STEP Z        | Schrittsignal Z                                                                                                |
| GPIO27  | ESP D27       | Freier Pin am ESP Pinout                                                                                       |
| GPIO14  | STEP Y        | Schrittsignal Y                                                                                                |
| GPIO12  | STEP X        | Schrittsignal X                                                                                                |
| GPIO13  | STEP A        | Schrittsignal A                                                                                                |
| GND     | GND           | Stromversorgung                                                                                                |
| VIN     | 5V            | Stromversorgung                                                                                                |
| GPIO23  | MOSI          | SPI Verbindung zum DAC Expander                                                                                |
| GPIO22  | SCL           | I2C Pin. Steuert die PortExpander 1 und 2. Außerdem verfügbar am PanelModule, ControllerModule und ESP Pinout. |
| GPIO1   | TX            | Freier Pin am ESP Pinout                                                                                       |
| GPIO3   | RX            | Freier Pin am ESP Pinout                                                                                       |
| GPIO21  | SDA           | I2C Pin. Steuert die PortExpander 1 und 2. Zudem verfügbar am PanelModule, ControllerModule und ESP Pinout.    |
| GPIO19  | ESP D19       | Freier Pin am ESP Pinout                                                                                       |
| GPIO18  | CLK           | SPI Verbindung zum DAC Expander                                                                                |
| GPIO5   | ESP Panel LED | Pin zur Steuerung einer LED auf dem PanelModule                                                                |
| GPIO17  | TX 2          | Serielle Schnittstelle für das PanelModule                                                                     |
| GPIO16  | RX 2          | Serielle Schnittstelle für das PanelModule                                                                     |
| GPIO4   | STEP C        | Schrittsignal C                                                                                                |
| GPIO2   | ESP D2        | Freier Pin am ESP Pinout                                                                                       |
| GPIO15  | STEP B        | Schrittsignal B                                                                                                |
| GND     | GND           | Stromversorgung                                                                                                |
| 3V3     | 3,3V          | 3,3V Ausgang                                                                                                   |

### Port Expander:

{% hint style="info" %}
Die Port Expander sind per I2C mit dem ESP32 verbunden.
{% endhint %}

Die beiden Port Expander haben jeweils 16 digitale Ein- bzw. Ausgänge. Details zu den beiden ICs sind in deren Datenblättern zu finden. Es handel sich um PCA9555PW.

#### Port Expander 1

Adresse: A0: GND, A1: GND, A2: GND

| Pin    | Mainboard Pin | Pin    | Mainboard Pin  |
| ------ | ------------- | ------ | -------------- |
| IO0\_0 | DIR X         | IO1\_0 | Auswahl Z      |
| IO0\_1 | DIR Y         | IO1\_1 | Auswahl Y      |
| IO0\_2 | DIR Z         | IO1\_2 | Auswahl X      |
| IO0\_3 | DIR A         | IO1\_3 | OK             |
| IO0\_4 | DIR B         | IO1\_4 | Motor start    |
| IO0\_5 | DIR C         | IO1\_5 | Programm start |
| IO0\_6 | Speed 1       | IO1\_6 | Alarm all      |
| IO0\_7 | Speed 2       | IO1\_7 | Autosquare     |

#### Port Expander 2

Adresse: A0: GND, A1: GND, A2: 5V

| Pin    | Mainboard Pin | Pin    | Mainboard Pin  |
| ------ | ------------- | ------ | -------------- |
| IO0\_0 | Eingang 1     | IO1\_0 | Eingang 9      |
| IO0\_1 | Eingang 2     | IO1\_1 | Eingang 10     |
| IO0\_2 | Eingang 3     | IO1\_2 | ENA            |
| IO0\_3 | Eingang 4     | IO1\_3 | Spindel on/off |
| IO0\_4 | Eingang 5     | IO1\_4 | Ausgang 1      |
| IO0\_5 | Eingang 6     | IO1\_5 | Ausgang 2      |
| IO0\_6 | Eingang 7     | IO1\_6 | Ausgang 3      |
| IO0\_7 | Eingang 8     | IO1\_7 | Ausgang 4      |

### DAC Expander pin map:

{% hint style="info" %}
Der DAC IC ist per SPI mit dem ESP32 verbunden.
{% endhint %}

Der DAC IC BU2506FV bietet 8 analoge 10-Bit Ausgänge. Für Details bitte in das Datenblatt des ICs schauen.

| Pin    | Mainboard Pin  | Beschreibung             |
| ------ | -------------- | ------------------------ |
| A01    | Feedrate       | Bedienelement            |
| A02    | Rotation speed | Bedienelement            |
| A03    | Joystick X     | Bedienelement            |
| A04    | Joystick Y     | Bedienelement            |
| A05    | Joystick Z     | Bedienelement            |
| A06    | DAC A06        | Freier Pin am ESP Pinout |
| IO0\_6 | DAC A07        | Freier Pin am ESP Pinout |
| A08    | DAC A08        | Freier Pin am ESP Pinout |
