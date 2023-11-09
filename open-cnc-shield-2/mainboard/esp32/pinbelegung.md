# Pinbelegung

Der ESP32 Mikroprozessor kann zur individuellen Programmierung von Funktionen genutzt werden. Dabei spielt es meist keine Rolle, welcher Controller / Software genutzt wird. Zum Beispiel die Autosquaring Funktion wird von dem ESP32 ausgeführt und ist damit Controller unabhängig.

## Pin Belegung

<figure><img src="../../../.gitbook/assets/esp32 pin map.jpg" alt=""><figcaption></figcaption></figure>

### **ESP32 pin map:**

<table><thead><tr><th width="124">ESP Pin</th><th width="144">Mainboard Pin</th><th width="399">Funktion</th></tr></thead><tbody><tr><td>EN</td><td><strong>-</strong></td><td></td></tr><tr><td>GPIO36</td><td>IO INT 1</td><td>Interrupt Eingang von PortExpander 1</td></tr><tr><td>GPIO39</td><td>IO INT 2</td><td>Interrupt Eingang von PortExpander 1</td></tr><tr><td>GPIO34</td><td>ESP D34</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO35</td><td>ESP D35</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO32</td><td>ESP D32</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO33</td><td>DAC LD</td><td>LD vom DAC Expander</td></tr><tr><td>GPIO25</td><td>DS18B20</td><td>Temperatur Sensor</td></tr><tr><td>GPIO26</td><td>STEP Z</td><td>Schrittsignal Z</td></tr><tr><td>GPIO27</td><td>ESP D27</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO14</td><td>STEP Y</td><td>Schrittsignal Y</td></tr><tr><td>GPIO12</td><td>STEP X</td><td>Schrittsignal X</td></tr><tr><td>GPIO13</td><td>STEP A</td><td>Schrittsignal A</td></tr><tr><td>GND</td><td>GND</td><td>Stromversorgung</td></tr><tr><td>VIN</td><td>5V</td><td>Stromversorgung</td></tr><tr><td>GPIO23</td><td>MOSI</td><td>SPI Verbindung zum DAC Expander</td></tr><tr><td>GPIO22</td><td>SCL</td><td>I2C Pin. Steuert die PortExpander 1 und 2. Außerdem verfügbar am PanelModule, ControllerModule und ESP Pinout.</td></tr><tr><td>GPIO1</td><td>TX</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO3</td><td>RX</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO21</td><td>SDA</td><td>I2C Pin. Steuert die PortExpander 1 und 2. Zudem verfügbar am PanelModule, ControllerModule und ESP Pinout.</td></tr><tr><td>GPIO19</td><td>ESP D19</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO18</td><td>CLK</td><td>SPI Verbindung zum DAC Expander</td></tr><tr><td>GPIO5</td><td>ESP Panel LED</td><td>Pin zur Steuerung einer LED auf dem PanelModule</td></tr><tr><td>GPIO17</td><td>TX 2</td><td>Serielle Schnittstelle für das PanelModule</td></tr><tr><td>GPIO16</td><td>RX 2</td><td>Serielle Schnittstelle für das PanelModule</td></tr><tr><td>GPIO4</td><td>STEP C</td><td>Schrittsignal C</td></tr><tr><td>GPIO2</td><td>ESP D2</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>GPIO15</td><td>STEP B</td><td>Schrittsignal B</td></tr><tr><td>GND</td><td>GND</td><td>Stromversorgung</td></tr><tr><td>3V3</td><td>3,3V</td><td>3,3V Ausgang</td></tr></tbody></table>

### Port Expander:

{% hint style="info" %}
Die Port Expander sind per I2C mit dem ESP32 verbunden.
{% endhint %}

Die beiden Port Expander haben jeweils 16 digitale Ein- bzw. Ausgänge. Details zu den beiden ICs sind in deren Datenblättern zu finden. Es handel sich um PCA9555PW.

#### Port Expander 1

Adresse: A0: GND, A1: GND, A2: GND

<table><thead><tr><th width="98">Pin</th><th width="188">Mainboard Pin</th><th width="82">Pin</th><th>Mainboard Pin</th></tr></thead><tbody><tr><td>IO0_0</td><td>DIR X</td><td>IO1_0</td><td>Auswahl Z</td></tr><tr><td>IO0_1</td><td>DIR Y</td><td>IO1_1</td><td>Auswahl Y</td></tr><tr><td>IO0_2</td><td>DIR Z</td><td>IO1_2</td><td>Auswahl X</td></tr><tr><td>IO0_3</td><td>DIR A</td><td>IO1_3</td><td>OK</td></tr><tr><td>IO0_4</td><td>DIR B</td><td>IO1_4</td><td>Motor start</td></tr><tr><td>IO0_5</td><td>DIR C</td><td>IO1_5</td><td>Programm start</td></tr><tr><td>IO0_6</td><td>Speed 1</td><td>IO1_6</td><td>Alarm all</td></tr><tr><td>IO0_7</td><td>Speed 2</td><td>IO1_7</td><td>Autosquare</td></tr></tbody></table>

#### Port Expander 2

Adresse: A0: GND, A1: GND, A2: 5V

<table><thead><tr><th width="98">Pin</th><th width="184">Mainboard Pin</th><th width="75">Pin</th><th>Mainboard Pin</th></tr></thead><tbody><tr><td>IO0_0</td><td>Eingang 1</td><td>IO1_0</td><td>Eingang 9</td></tr><tr><td>IO0_1</td><td>Eingang 2</td><td>IO1_1</td><td>Eingang 10</td></tr><tr><td>IO0_2</td><td>Eingang 3</td><td>IO1_2</td><td>ENA</td></tr><tr><td>IO0_3</td><td>Eingang 4</td><td>IO1_3</td><td>Spindel on/off</td></tr><tr><td>IO0_4</td><td>Eingang 5</td><td>IO1_4</td><td>Ausgang 1</td></tr><tr><td>IO0_5</td><td>Eingang 6</td><td>IO1_5</td><td>Ausgang 2</td></tr><tr><td>IO0_6</td><td>Eingang 7</td><td>IO1_6</td><td>Ausgang 3</td></tr><tr><td>IO0_7</td><td>Eingang 8</td><td>IO1_7</td><td>Ausgang 4</td></tr></tbody></table>

### DAC Expander pin map:

{% hint style="info" %}
Der DAC IC ist per SPI mit dem ESP32 verbunden.
{% endhint %}

Der DAC IC BU2506FV bietet 8 analoge 10-Bit Ausgänge. Für Details bitte in das Datenblatt des ICs schauen.

<table><thead><tr><th width="98">Pin</th><th width="184">Mainboard Pin</th><th width="366">Beschreibung</th></tr></thead><tbody><tr><td>A01</td><td>Feedrate</td><td>Bedienelement</td></tr><tr><td>A02</td><td>Rotation speed</td><td>Bedienelement</td></tr><tr><td>A03</td><td>Joystick X</td><td>Bedienelement</td></tr><tr><td>A04</td><td>Joystick Y</td><td>Bedienelement</td></tr><tr><td>A05</td><td>Joystick Z</td><td>Bedienelement</td></tr><tr><td>A06</td><td>DAC A06</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>IO0_6</td><td>DAC A07</td><td>Freier Pin am ESP Pinout</td></tr><tr><td>A08</td><td>DAC A08</td><td>Freier Pin am ESP Pinout</td></tr></tbody></table>
