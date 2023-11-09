# InOut Module

{% hint style="info" %}
Diese Seite ist für die Entwicklung neuer InOut Module und die Fehlersuche relevant.  Für die unterschiedlichen InOut Module gibt es eigene Dokumentationsseiten. Dort werden die unterstützten Features und technische Details der einzelnen Module beschrieben. [inoutmodules](../../inoutmodules/ "mention")
{% endhint %}

Das InOutModule ist für die Ein- und Ausgänge der Platine zuständig. Die verschiedenen InOut Module unterscheiden sich in der Anschlussart und Ausstattung. Einige haben steckbare Anschlüsse, andere nutzen Federklemmen-Anschlüsse. Auch gibt es Varianten mit bereits installierten Relais zum Anschluss von geschalteten Verbrauchern.

## Pin Belegung

<figure><img src="../../../.gitbook/assets/inout pin ma.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Typ OUT: Das Signal geht vom Controller / Steuerungssoftware in Richtung InOutModule

Typ IN: Das Signal kommt vom InOutModule und geht zum Controller / der Steuerung
{% endhint %}

### **InOut  1:**

<table><thead><tr><th width="81">Pin</th><th width="219">Beschreibung</th><th width="111">Typ</th><th width="67">Pin</th><th width="198">Beschreibung</th><th width="69">Typ</th></tr></thead><tbody><tr><td>1</td><td><strong>Ausgang 1</strong> </td><td>OUT</td><td>2</td><td><strong>Eingang 8</strong></td><td>IN</td></tr><tr><td>3</td><td><strong>Ausgang 2</strong></td><td>OUT</td><td>4</td><td><strong>Eingang 7</strong></td><td>IN</td></tr><tr><td>5</td><td><strong>Ausgang 3</strong></td><td>OUT</td><td>6</td><td><strong>Eingang 6</strong></td><td>IN</td></tr><tr><td>7</td><td><strong>Ausgang 4</strong></td><td>OUT</td><td>8</td><td><strong>Eingang 5</strong></td><td>IN</td></tr><tr><td>9</td><td><strong>5V</strong></td><td>OUT</td><td>10</td><td><strong>Eingang 4</strong></td><td>IN</td></tr><tr><td>11</td><td><strong>V-Board</strong><br>Gleiche Spannung wie die Stromversorgung der Hauptplatine</td><td>OUT</td><td>12</td><td><strong>Eingang 3</strong></td><td>IN</td></tr><tr><td>13</td><td><strong>GND</strong></td><td>OUT</td><td>14</td><td><strong>Eingang 2</strong></td><td>IN</td></tr><tr><td>15</td><td><strong>GND</strong></td><td>OUT</td><td>16</td><td><strong>Eingang 1</strong></td><td>IN</td></tr></tbody></table>

### **InOut 2:**

<table><thead><tr><th width="81">Pin</th><th width="219">Beschreibung</th><th width="111">Typ</th><th width="67">Pin</th><th width="198">Beschreibung</th><th width="69">Typ</th></tr></thead><tbody><tr><td>1</td><td><strong>Ausgang 5</strong></td><td>OUT</td><td>2</td><td><strong>Eingang 16</strong></td><td>IN</td></tr><tr><td>3</td><td><strong>Ausgang 6</strong></td><td>OUT</td><td>4</td><td><strong>Eingang 15</strong></td><td>IN</td></tr><tr><td>5</td><td><strong>Ausgang 7</strong></td><td>OUT</td><td>6</td><td><strong>Eingang 14</strong></td><td>IN</td></tr><tr><td>7</td><td><strong>Ausgang 8</strong></td><td>OUT</td><td>8</td><td><strong>Eingang 13</strong></td><td>IN</td></tr><tr><td>9</td><td><strong>5V</strong></td><td>OUT</td><td>10</td><td><strong>Eingang 12</strong></td><td>IN</td></tr><tr><td>11</td><td><strong>V-Board</strong><br>Gleiche Spannung wie die Stromversorgung der Hauptplatine</td><td>OUT</td><td>12</td><td><strong>Eingang 11</strong></td><td>IN</td></tr><tr><td>13</td><td><strong>GND</strong></td><td>OUT</td><td>14</td><td><strong>Eingang 10</strong></td><td>IN</td></tr><tr><td>15</td><td><strong>GND</strong></td><td>OUT</td><td>16</td><td><strong>Eingang 9</strong></td><td>IN</td></tr></tbody></table>

## Technische Daten

<table><thead><tr><th width="218">Beschreibung</th><th>Details</th></tr></thead><tbody><tr><td>Eingänge 1-16</td><td>Die Eingänge sind typischerweise mit Pullup Widerständen versehen. Dies ist allerdings auch vom ControllerModule abhängig.</td></tr><tr><td>Ausgänge 1-8</td><td>Die Ausgänge sind auf dem Mainboard mit 4,7K Ohm Pulldown Widerständen versehen.</td></tr><tr><td>Maße der Module</td><td>75 mm x 67,5 mm</td></tr></tbody></table>

