---
cover: ../../.gitbook/assets/inoutmodule_banner.jpg
coverY: 0
---

# Federklemmen

<div>

<figure><img src="../../.gitbook/assets/controller spring-2-1200px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/controller spring-1200px (1).jpg" alt=""><figcaption></figcaption></figure>

</div>

### Überblick

* 8 Eingänge
* Eingänge schalten entweder mit GND/Masse oder mit 5-24V (über einen Switch direkt auf der Platine umschaltbar)
* 4 Ausgänge
* Ausgänge sind mit Darlington Relays versehen - schalten also GND/Masse an den OUTs
* 500mA pro Ausgang
* COM-Spannung für Ausgänge wählbar zwischen 5V und Eingangsspannung des OPEN-CNC-Shields (normalerweise 24V)
* Anzeige der aktuellen Stati über LEDs

### Technische Daten

<table><thead><tr><th width="421">Eigenschaft</th><th>Wert</th></tr></thead><tbody><tr><td>maximaler Strom Ausgänge</td><td>jeweils 500mA</td></tr><tr><td>maximale Spanung Ausgänge</td><td>50V - die Spannung kann an COM2 angelegt werden. Der Jumper für COM2 darf in diesem Fall nicht gesetzt sein</td></tr><tr><td>maximale Spannung an Eingängen </td><td>24V</td></tr></tbody></table>

Die schematischen Zeichnungen und DXF files zu der Platine sind auf Github zu finden:

{% embed url="https://github.com/timo1235/cnc-werkstatt/tree/master/OPEN-CNC-Shield%202.x/OCS2%20modules/InOutModules/InOutModule%20Spring" %}

### Jumper

| Jumper                                                                                | Beschreibung                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img src="../../.gitbook/assets/spring_relay_jumper.png" alt="" data-size="original"> | <p>Hier kann die Spannung für COM1 und COM2 mit einem Jumper eingestellt werden.<br>- ist der Jumper in der linken Position, liegt die OCS2 Eingangsspannung an (normalerweise 24V)<br>- ist der Jumper in der rechten Position, liegen 5V an. <br></p>                                     |
| <img src="../../.gitbook/assets/spring_switch.png" alt="" data-size="original">       | <p>Schalter für die Eingänge am Beispiel von Eingang 1:<br>- <strong>Schalter in der oberen Position:</strong> An IN1 wird geschaltet, sobald dort GND anliegt<br>- <strong>Schalter in der unteren Position:</strong> IN1 wird geschaltet, sobald eine Spannung zwischen 5-24V anliegt</p> |

### Beispiele Ein- und Ausgänge nutzen

{% hint style="info" %}
Beispiele für die Nutzung gibts hier: [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention")
{% endhint %}
