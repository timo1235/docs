# Driver Module

{% hint style="info" %}
Diese Seite ist für die Entwicklung neuer Driver Module und die Fehlersuche relevant.  Für die unterschiedlichen Driver Module gibt es eigene Dokumentationsseiten. Dort werden die unterstützten Features und technische Details der einzelnen Module beschrieben. [drivermodules](../../drivermodules/ "mention")
{% endhint %}

Die Driver Module sind für die Verbindung der Steuerung mit den verschiedenen Motortreibern. Je nachdem, was für Treiber an der Maschine eingesetzt werden, eignen sich andere Driver Module.

## Pin Belegung

<figure><img src="../../../.gitbook/assets/driver pin map.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typ OUT: Das Signal geht vom Controller / Steuerungssoftware in Richtung DriverModule

Typ IN: Das Signal kommt vom DriverModule und geht zum Controller / der Steuerung
{% endhint %}

### **Anschluss:**

<table><thead><tr><th width="81">Pin</th><th width="219">Beschreibung</th><th width="111">Typ</th><th width="67">Pin</th><th width="198">Beschreibung</th><th width="69">Typ</th></tr></thead><tbody><tr><td>1</td><td><strong>GND</strong></td><td>OUT</td><td>2</td><td><strong>V-Mot</strong><br>Hier liegt die Spannung der Motor Stromversorgung an.</td><td>OUT</td></tr><tr><td>3</td><td><strong>ENA</strong><br>Enable </td><td>OUT</td><td>4</td><td><strong>5V</strong></td><td>OUT</td></tr><tr><td>5</td><td><strong>ALARM</strong><br>Alarmausgang</td><td>IN</td><td>6</td><td><strong>DIR</strong><br>Richtungssignal</td><td>OUT</td></tr><tr><td>7</td><td><strong>STEP</strong><br>Schrittsignal</td><td>OUT</td><td>8</td><td><strong>-</strong></td><td>-</td></tr></tbody></table>

## Technische Daten

<table><thead><tr><th width="218">Beschreibung</th><th>Details</th></tr></thead><tbody><tr><td>STEP</td><td>Gepufferte Schrittsignale. 5V mit max. 20mA</td></tr><tr><td>DIR</td><td>Gepufferte Richtungssignale. 5V mit max. 20mA</td></tr><tr><td>Maße der Module</td><td>22 mm x 35 mm</td></tr></tbody></table>

