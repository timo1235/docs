---
cover: broken-reference
coverY: 0
---

# D-SUB25

<div>

<figure><img src="../../.gitbook/assets/panel d-sub25-3-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/panel d-sub25-4-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/panel d-sub25-1200px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Mit diesem PanelModule kann ein externes Bedienelement / Handrad über ein D-SUB25 Kabel angeschlossen werden. Da das Kabel über 25 Adern verfügt, gibt es für jede Funktion eine separate Datenleitung.

### Überblick

* D-SUB25 Anschluss
* Eigene Datenleitung für jede Funktion

### LED

Es gibt eine LED auf dem Board, welche durch den ESP32 auf dem OPEN-CNC-Shield 2 gesteuert werden kann.

### Pinout

<table><thead><tr><th width="104">D-SUB25 Pin</th><th>Funktion</th><th width="86">D-SUB25 Pin</th><th>Funktion</th></tr></thead><tbody><tr><td>1</td><td>5V</td><td>14</td><td>GND</td></tr><tr><td>2</td><td>5V</td><td>15</td><td>GND</td></tr><tr><td>3</td><td>Encoder A</td><td>16</td><td>Encoder B</td></tr><tr><td>4</td><td>Joystick X</td><td>17</td><td>Joystick Y</td></tr><tr><td>5</td><td>Joystick Z</td><td>18</td><td>Feedrate - Vorschubgeschwindigkeit</td></tr><tr><td>6</td><td>Rotation Speed - Spindelgeschwindigkeit</td><td>19</td><td>Programm Start</td></tr><tr><td>7</td><td>Motor Start</td><td>20</td><td>OK </td></tr><tr><td>8</td><td>Auswahl X</td><td>21</td><td>Auswahl Y</td></tr><tr><td>9</td><td>Auswahl Z</td><td>22</td><td>Speed 1</td></tr><tr><td>10</td><td>Speed 2</td><td>23</td><td>ENA - Enable der Treiber</td></tr><tr><td>11</td><td>Autosquare</td><td>24</td><td>ESP TX - Serielle Verbindung</td></tr><tr><td>12</td><td>ESP RX - Serielle Verbindung</td><td>25</td><td>Frei - Kann am Pin Header selbst belegt werden</td></tr><tr><td>13</td><td>Frei - Kann am Pin Header selbst belegt werden</td><td></td><td></td></tr></tbody></table>

Die Pins D13 und D25 stehen zusätzlich auf der Platine als Pin Header zur Verfügung und können selbst belegt werden.

### Technische Details

Bis auf die serielle Verbindung(ESP TX und RX) arbeiten alle Ein- und Ausgänge am D-SUB25 mit einem 5V Pegel.

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/PanelModules/PanelModule%20D-SUB25" %}
