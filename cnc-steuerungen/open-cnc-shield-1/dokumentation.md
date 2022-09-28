# Dokumentation

### **Jumper / Terminals / Anschlüsse**

****

| Beschriftung                             | Funktion                                 | Beschreibung                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JP6, JP7, JP2, JP1, JP10, JP11           | Mikroschritte der Aufstecktreiber        | <p>Hier werden die Mikroschritte der Aufstecktreiber eingestellt. Falls externe Treiber verwendet werden können diese Jumper frei gelassen werden.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#microstepping">Mikroschritte</a></p>                                                       |
| JP5, JP8, JP4, JP3, JP9, JP12            | Fault Jumper der Aufstecktreiber         | <p>Muss bei A4988 Treiber gesetzt sein. Bei DRV8825 bleiben die Jumper frei.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#fault-jumper">Fault Jumper</a></p>                                                                                                                               |
| J4, J7, J1, J2, J10, J11                 | Motoranschluss bei Aufstecktreibern      | <p>Hier werden die Motoren angeschlossen, wenn die Aufstecktreiber verwendet werden.<br>Schema: 1A 1B 2A 2B. Drehen die Motoren falsch herum einfach den Stecker einmal drehen.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#anschlie%C3%9Fen-der-motoren">Anschließen der Motoren</a></p> |
| JP19                                     | Konfiguration der Achsen                 | <p>Hier können die verschiedenen Achsen miteinander verbunden werden. Wird Estlcam als Software eingesetzt sollten hier alle Jumper gesetzt sein.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#konfiguration-der-achsen">Konfiguration der Achsen</a></p>                                  |
| JP20                                     | Autosquaring Konfiguration               | <p>Hier kann der Autosquaring Modus aktiviert werden und die Drehrichtung der Motoren während Autosquaring festgelegt werden.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#autosquare-konfiguration">Autosquare Konfiguration</a></p>                                                      |
| JP17                                     | Verbindet „Vin“ mit dem 12V Netz         | <p>Wenn das Shield mit 12V betrieben wird, sollte dieser Jumper gesetzt werden.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#stromversorgung">Stromversorgung</a></p>                                                                                                                      |
| JP15 und JP16                            | Jumper für die Spannung der Ausgänge     | <p>Hier kann die Spannung für die Ausgänge 1-8 festgelegt werden. Jeder Jumper stellt die Spannung für 4 Ausgänge ein.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#ausg%C3%A4nge">Ausgänge</a></p>                                                                                        |
| <p>JP13 und JP14<br>(ab version 1.5)</p> | Jumper für die Spannung an den Eingängen | Hier kann die Spannung, welche an der Terminals der Eingänge anliegt festgelegt werden. Jeder Jumper zählt dabei für 8 Eingänge. Mehr dazu im Kapitel Eingänge.                                                                                                                                                                       |
| JP18                                     | Spannung der Drehzahlsteuerung           | <p>Ist dieser Jumper gesetzt, liegt die Spannung des analogen Ausgangs für die Drehzahl zwischen 0 und 5V. Ansonsten liegt sie zwischen 0 und 10V.<br>Mehr dazu unter <a href="https://blog.altholtmann.com/open-cnc-shield/dokumentation/#spindel-steuerung">Spindelsteuerung</a></p>                                                |
| JP21(ab version 1.6)                     | ENA Einstellung                          | Hier können die ENA Treiber standardmäßig eingestellt werden. Mit einem 1K Widerstand kann ENA hier entweder mit GND oder mit 5V verbunden werden. Wird dies nicht benötigt kann der Jumper auch weggelassen werden.                                                                                                                  |

### **Stromversorgung**

Das OPEN-CNC-Shield kann mit 12-24V betrieben werden. Ich empfehle 24V.\
Wenn das Shield mit 12V versorgt wird kann es sein, dass im 12V Netz keine 12V ankommen, da durch den Spannungswandler ein geringer Spannungsverlust entsteht. Für diesen Fall ist der Jumper JP17 vorgesehen. Wenn dieser gesetzt ist, wird die Eingangsspannung direkt in das 12V Netz weitergeleitet.

Achtung, der Jumper JP17 darf auf keinen Fall gesetzt werden, wenn mehr als 12V am Terminal T2 (12-24V in) anliegen. Das kann diverse Bauteile auf dem Board zerstören!

#### **Benötigte Stromstärke**

Wenn **keine** Aufstecktreiber verwendet werden wird ein **24V 5A** Netzteil völlig ausreichen und bietet auch noch Reserven. Der zweite 12-24V Vin ist in diesem Fall unnötig. Hier ist ein Beispiel Netzteil: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/3dax7uF)

Sollten Aufstecktreiber verwendet werden sollte ein stärkeres Netzteil verwendet werden. Generell kann pro Treiber mit etwa 2A gerechnet werden. Hier ist zum Beispiel eins mit **24V und 15A**, damit können ohne Probleme alle 6 Aufstecktreiber verwendet werden und es bleibt auch noch genug Reserve: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/30T7FYc)\
Die Netzteile mit hohen Strömen bieten meist mehrere Anschlüsse. Hierfür kann der zweite 12-24V Vin genutzt werden. Dieser dient der Sicherheit und soll der Wärmeentwicklung bei hohen Strömen entgegenwirken.

### **Eingänge**

Es gibt 16 Eingänge auf dem OPEN-CNC-Shield. Diese können entweder mit positiver Spannung von 5-24V geschaltet werden oder mit GND. Wählbar ist dies über einen Jumper an dem jeweiligen Eingang. Jeder Eingang besitzt seinen eigenen Jumper.

Falls Autosquaring genutzt werden soll, braucht jeder Motor seinen eigenen Endstopp. Mehr dazu unter [Autosquaring](broken-reference).

#### **Spannung an den Eingängen**

Ab Platinenversion 1.5: Die Spannung, welche an den Terminals für die Eingänge anliegt, kann mit den Jumper JP13 und JP14 festgelegt werden. Man hat die Wahl zwischen 5V und 12V. Es ist ebenfalls möglich selbst eine Spannung anzulegen. Dafür müssen die Jumper frei gelassen werden und die Spannung kann dann an den jeweiligen COM-Anschluss gelegt werden.

#### **Endstopps**

**Normally closed / normally open**

Es können entweder normally closed (im Normalzustand geschlossen / ausgelöst) oder normally open (im Normalzustand geöffnet / nicht ausgelöst) Endstopps angeschlossen werden. Diese können entweder mit mehreren an einem Eingang angeschlossen werden oder es kann jeder Endstopp an seinen eigenen Eingang angeschlossen werden.\
Ich würde eine normally closed Verkabelung bevorzugen, da hierbei auch Kabelbrüche direkt erkannt werden können. Eingänge, an denen normally closed Sensoren angebracht sind müssen in der Software vermutlich invertiertiert werden.

**Näherungssensoren PNP oder NPN**

Es können sowohl PNP Sensoren als auch NPN Sensoren angeschlossen werden. Hierzu muss lediglich die passende Jumper Einstellung an dem Eingang vorgenommen werden. Diese gibt es ebenfalls als NC(normally closed) oder NO(normally open) Variante. Siehe oben für die Verkabelung.

NPN NC Sensor: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/3bw2EJx) [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/ebay\_icon-1.png)](http://rover.ebay.com/rover/1/707-53477-19255-0/1?ff3=4\&pub=5575576561\&toolid=10001\&campid=5338665749\&customid=\&mpre=https%3A%2F%2Fwww.ebay.de%2Fitm%2F4-Stk-induktiver-Naherungsschalter-Endschalter-NPN-NC-TTL-kompatibel-LJ12A3%2F232619400054%3Fhash%3Ditem3629325b76%3Ag%3A1YAAAOSwHBlaThtW) [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/aliexpress\_icon-1.png)](https://s.click.aliexpress.com/e/\_dW13pXA)

#### **LED als Signal für Eingänge**

Möchte man eine LED verbauen, welche anzeigt, ob ein Eingang ausgelöst wurde, gibt es verschiedene Möglichkeiten dieses zu realisieren.

**1. Direktes Anlöten an die Arduinos**

**Vorteil**: Unabhängig von der Jumper-Einstellung und Stromspannung der Eingänge.\
**Nachteil**: Es müssen Kabel verlötet werden.

Die Kabel für die LEDs können entweder von unten an die Platine gelötet werden, oder von oben direkt an die Arduino Megas. Im unteren Bild ist ein Beispiel für Eingang 1. GND von der LED wird mit dem Arduino Pin des Eingangs verbunden und der Pluspol der LED wird über einen 220 Ohm Widerstand mit 5V(Diese kann man sich irgendwo am Board abgreifen, zum Beispiel an einigen Schraubterminals) verbunden. Welcher Arduino dabei genommen wird, spielt keine Rolle. Eine Pinbelegung ist dem Schema zu entnehmen ⇾ [Gitlab – Timos Werkstatt](https://gitlab.com/cnc-projects1/timos-werkstatt)

**2. LED ebenfalls am Eingang anschließen**

**Vorteil**: Einfach anzuschließen, kein Löten\
**Nachteil**: Abhängig von der Jumper-Einstellung und der Spannung des Eingangs

**Jumper steht auf GND:**\
In diesem Fall wird die LED mit dem Minuspol an „IN“ vom Eingang angeschlossen und mit dem Pluspol mit einem Widerstand in Reihe an z.B. COM, oder direkt mit einem 220 Ohm Widerstand an 5V. Je, nachdem wie viel Spannung an COM anliegt werden verschiedene Widerstände benötigt. Siehe dazu die untere Tabelle.

**Jumper steht auf VCC**\
Der Minuspol der LED wird an GND angeschlossen und der Pluspol in Reihe mit einem passenden Widerstand an IN. Welche Widerstand benötigt wird kann der unteren Tabelle entnommen werden:

**3. Arduino Mega Ausgang für LED programmieren**

**Vorteil**: Es muss weder gelötet werden, noch ist man abhängig von der Jumper-Einstellung oder Spannung\
**Nachteil**: Es muss ein wenig Arduino Code geschrieben werden.

Bei dieser Methode muss der Code von dem zweiten Arduino ein wenig erweitert werden. In der Setup Methode müssen die Pins für die Eingänge auf „INPUT\_PULLUP“ gestellt werden. Dazu einfach kurz googlen, wie man Eingänge bei Arduinos setzt. Die benötigten Pins findet man ebenfalls im Schema ⇾ [Gitlab – Timos Werkstatt](https://gitlab.com/cnc-projects1/timos-werkstatt)

Danach erstellt man in der Loop-Methode eine Prüfung, ob der als „INPUT“ deklarierte Pin ausgelöst wurde(Google ⇾ Arduino digitalRead). Und falls dem so ist, setzt man einen der freien Pins am Pinout **J8** entsprechend. Die LED wird dann mit dem Pluspol in Reihe mit einem 220 Ohm Widerstand an dem Pinout Pin angeschlossen und mit dem Minuspol irgendwo an GND.

Hier ein wenig Beispielcode(bisher ungetestet) für Eingang 1:

```
const byte input1 = 15; // Digital Pin for Input1
const byte output1 = A1; // Output Pin on Pinout J8 on the Shield

setup() {
   ...
   pinMode(input1, INPUT_PULLUP); // Set pinmode for input pin

   pinMode(output1, OUTPUT); // Set pinmode as output
   digitalWrite(output1, LOW); // Initial state for the output LED
   ...
}

loop() {
   ...
   bool input1State = digitalRead(input1); // Read input 1 pin
   // If input1State is LOW(which means it is triggered) write HIGH
   // to the output pin and vice versa
   digitalWrite(output1, !input1State);
   ...
}
```

### **Ausgänge**

Das OPEN-CNC-Shield bietet 8 Ausgänge, welche in Estlcam nach Belieben geschaltet werden können. Es sind zwei Relaistreiber verbaut. Für jeden Relaistreiber kann die Spannung über die Jumper JP15 und JP16 gesetzt werden. OUT1-4 sind an COM1 angeschlossen und werden somit mit dem Jumper JP15 mit einer Spannung verbunden. **Achtung: COM1 wird ebenfalls für das Spindel Relais genutzt**, mehr dazu unter [Spindel Steuerung](broken-reference). OUT5-8 sind an COM2 angeschlossen und werden mit dem Jumper JP16 konfiguriert.\
So ist es zum Beispiel möglich, dass die Ausgänge 1-4 mit 5V arbeiten und die Ausgänge 5-8 mit 12V. Möchte man an eine andere Spannung kann man die jeweiligen Jumper offen lassen und diese Spannung direkt an COM1 oder COM2 anlegen. Diese ist dann an allen gleichnamigen COM Anschlüssen verfügbar, darf aber 50V nicht überschreiten.

Pro Ausgang darf maximal 500mA Strom fließen. Daher immer mit Relais arbeiten, sobald die Grenze eventuell überschritten wird. Auch auf die maximalen Ströme der Netze achten. Im 5V und 12V Netz stehen jeweils max 3A zur Verfügung. Die Ausgänge sind hier nicht die einzigen Abnehmer – Lüfter, Arduinos usw. ziehen auch Strom!

Im nachfolgendem Bild ist Beispielhaft der Anschluss eines 5V Relais. COM2 wird hierbei auf 5V gesetzt. Dann wird VCC mit COM2 verbunden(Also 5V an VCC) und GND mit GND. Geschaltet wird dann mit OUT5 und OUT6. Sobald diese in Estlcam ausgelöst werden liegt dort GND an. Sollte das Relais nicht schalten muss der Jumper auf dem Relais einmal umgesetzt werden. Dieser ist auf diesem Bild Gelb und unter den Anschlüssen für GND,IN1,IN2,VCC.

### **Aufstecktreiber / Externe Motortreiber**

Das OPEN-CNC-Shield unterstützt sowohl Aufstecktreiber wie z.B. den A4988 oder DRV8825 als auch den Anschluss externer Motortreiber. Für was man sich entscheidet, bleibt einem selbst überlassen. Generell kann man sagen, dass externe Treiber einen deutlich höheren Kostenaufwand haben, aber dafür auch höhere Ströme unterstützen und nicht so eine gute Kühlung benötigen. Für Nema 17 Motoren mit etwa 2A Leistung sollten die Aufstecktreiber bei guter Kühlung vollkommen ausreichen. Möchte man größere/stärkere Motoren/Servos/“Closed-Loop Motoren“ sollte man sich eher mit externen Treibern beschäftigen. Man kann auch erstmal klein anfangen und später auf externe Treiber aufrüsten.

#### **ENA Einstellung**

Ab Platinenversion 1.6: Die Einstellung welchen Zustand der ENA(Enable) Anschluss im Standard hat kann über den Jumper JP21 getätigt werden. Dies gilt sowohl für die Aufstecktreiber als auch für externe Treiber. Besitzen die Treiber selbst schon entsprechende Pullup-/ oder Pulldown Widerstände kann der Jumper frei gelassen werden.

**Platinen Version v1.6 und v1.7:** Der Widerstand R20 ist leider falsch beschriftet. Dort muss anstatt eines 10K Widerstands ein 1K Widerstand eingesetzt werden. Ist dort der 10K Widerstand verbaut geht auch nichts kaputt, allerdings funktioniert dann der Jumper für den ENA State nicht(JP21).

#### **Aufstecktreiber**

Alle Änderungen sollten immer im Stromlosen zustand erfolgen. Bitte auch unbedingt darauf achten die Treiber richtig herum einzustecken! Hier gibt es Unterschiede zwischen A4988 und DRV8825 Treiber! Wurde ein Treiber einmal falsch herum eingesteckt und das Board unter Strom gesetzt ist der Treiber sehr wahrscheinlich defekt.

**Microstepping**

Das Microstepping der Aufstecktreiber wird mit Jumpern eingestellt. Diese befinden sich auf der Platine genau unter den jeweiligen Treibern. Diese Einstellung kann demnach nur erfolgen, wenn die Treiber nicht eingesteckt sind.

Mit Microstepping kann man die Schritte des Motors weiter verkleinern. Ein typischer Schrittmotor hat z.B. 200 Schritte für eine volle Umdrehung. Stellt man das Mircostepping nun etwa auf 1/8 Schritt bedeutet dies: 200 × 8 = 1600 – Es werden nun 1600 Schritte für eine volle Drehung benötigt. Je höher die Microstepping Einstellung, desto geringer wird der Haltemoment der Motoren. Generell kann man mit diesen Werten experimentieren, um zu schauen, welche sich am besten für die eigene Maschine eignen. Oft geben Hersteller auch an, wie die Mikroschritte eingestellt werden sollten. Hat man hier eine Einstellung gewählt muss, man diese auch unbedingt der Software mitteilen.

Hier ist ein Beispiel für Estlcam. Die Mikroschritte sollten so für eine MPCNC-Fräse funktionieren. Die Jumper sind in diesem Beispiel für die x- und y-Achse auf 1/8 Schritt und für die z-Achse auf 1/4 Schritt eingestellt.

**Einsetzen der Treiber**

Bitte nur im Stromlosen zustand!

Hier ist es wichtig auf die richtige Orientierung zu achten, welche sich durchaus zwischen den verschiedenen Treiber Typen unterscheiden kann.

Ich mache es immer so, dass ich unter die Treiber schaue und die Position der Motoranschlüsse suche(1B, 1A, 2A, 2B) und darauf achte, diese dann in Richtung des 4Pin Headers für den Motor auszurichten.

So sieht das ganze dann von oben aus. Die Motoranschlüsse gehen in Richtung des Pin Headers. _**Achtung, das Bild eines DRV8825 Treibers unterscheidet sich! Nur auf die Motoranschlüsse achten!**_

**Fault Jumper**

Dieser Jumper ist neben jedem Treiber zu finden. Bezeichnungen JP5, JP8, JP4, JP3, JP9, JP12.\
Falls man die DRV8825 Treiber nutzt, bleibt dieser Jumper offen bzw. wird nicht gesetzt. Die Treiber geben hierüber ein Signal wenn diese überlastet sind, welches man abgreifen und nutzen könnte. **Bei den A4988 Treibern muss dieser Jumper gesetzt werden!** Hiermit wird der Treiber mit 5V versorgt.

**Treiberstrom einstellen**

Die Treiber besitzen ein Potentiometer, mit welchem der Strom bzw. die Spannung eingestellt werden kann. Dies wird folgendermaßen berechnet: Maximalstrom der Motoren geteilt durch 2. Also für Standard Nema 17 Schrittmotoren mit 2A ergibt sich eine Referenzspannung von 1V( 2A / 2 = 1). Bei dieser Spannung brauchen die Treiber allerdings eine sehr gute Kühlung. Bei der MPCNC werden die Treiber meist auf 0,7V eingestellt. Kühlen muss man die Treiber aber trotzdem ;-).\
Das Einstellen der Spannung muss im bestromten Zustand erfolgen. Daher muss man hier sehr Vorsichtig sein, nicht abzurutschen und somit einen Kurzschluss zu verursachen. In dem folgenden Video habe ich kurz gezeigt, wie man die Motoren einstellen kann:

**Anschließen der Motoren**

Die Motoren werden an den Anschlüssen J4, J7, J1, J2, J10 und J11 angeschlossen. Hierfür kann man Dupont Stecker verwenden. Hier zum Beispiel ein Set mit Zange: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/2Y8Agqz)\
Folgendes Anschlussschema sollte helfen:

Um herauszufinden welche Kabel zusammengehören kann man einfach eine Durchgangsmessung machen. Die Anschlüsse 1A und 1B sollten einen Durchgang haben. Genauso wie 2A und 2B.

#### **Externe Motortreiber**

Es gibt eine Vielzahl unterschiedlicher externer Treiber. Nutzt man externe Treiber, wird die Microstepp Konfiguration direkt an dem Treiber vorgenommen und nicht mehr auf der Platine. Die Jumperstellung spielt also keine Rolle mehr auf der Platine. Ebenfalls braucht die Platine nun nur noch einen Bruchteil des Stroms, da die Treiber direkt mit dem Motorstrom betrieben werden. Hier ist ein Beispiel für TB6600 Treiber:

Auf dem OPEN-CNC-Shield sind für jeden Treiber 4 Ausgänge. Einmal Enable(ENA) zum stromlos Schalten der Motoren, dann DIR für die Drehrichtung und STEP für die Schritte. Als letztes wird GND an allen Minus Polen aufgelegt. Im „High Voltage“ Bereich wird der Schrittmotor und das Netzteil angeschlossen.

### **Konfiguration der Achsen**

Hier kann man die Achsen miteinander verbinden. Je nachdem wofür man das Shield verwendet können die Achsen konfiguriert werden. Setzt man beispielsweise einen Jumper bei „Step X2“ und „X1“ sind die Steps der beiden Achsen verbunden / gleich. Gleiches gilt für die anderen Jumper.

#### **Achsen in Estlcam**

Bei der Verwendung von Estlcam sollten alle Jumper gesetzt sein. Estlcam unterstützt nur drei Achsen(x, y und z). Durch Setzen der Jumper Verfahren die Motoren für x1 und x2 dieselben Schritte und drehen in dieselbe Richtung. Gleiches gilt für die anderen Achsen.

#### **Achsen in LinuxCNC**

**LinuxCNC Adapters v1.0**

Hier kann der Jumper für die z-Achse sowohl bei „Step“ als auch bei „Dir“ freigelassen werden. Hierdurch kann der Motor Z2 für eine weitere Achse verwendet werden. Demnach könnten man dadurch in LinuxCNC 4 Achsen verfahren.

**LinuxCNC Adapter 6Achs v1.0**

**Hier sollten keine Jumper gesetzt werden. Dadurch können in LinuxCNC 6 Achsen verfahren werden.**

### **Spindel Steuerung**

Das OPEN-CNC-Shield bietet vielfältige Möglichkeiten der Spindel Steuerung. Unter anderem ist es möglich diese ein- und auszuschalten oder die Drehzahl zu regulieren.

Achtung! Lebensgefahr! Lasse den Fräsmotor von einem Elektriker anschließen!

Auf dem unten stehenden Bild sind die Terminals zum Anschluss einer Spindel abgebildet.

#### **Analoges Signal kalibrieren**

Wie der analoge Ausgang auf 10V kalibriert wird, zeigt das folgende Video. Dieser Schritt ist übrigens nur notwendig, wenn auch eine Spindel mit externer Drehzahlsteuerung angeschlossen wird.

Hier nochmal kurz zusammengefasst:

1. Platine mit Strom versorgen.
2. Arduino an Computer mit Estlcam anschließen
3. Multimeter auf Gleichstrommessung stellen und an den Terminal _Inverter/PWM_ anschließen. Dabei kommt der Minus-Pol an GND und der Plus-Pol an VCC.
4. In der CNC Steuerung von Estlcam den Arduino Mega mit richtigen Port auswählen.
5. Unter dem Reiter _Fräsmotor_ die Einstellungen für die China Spindel laden.
6. Die Steuerung programmieren.
7. Den Button drücken, um die Spindel zu starten und den Befehl „pwm100“ in der Kommandozeile eintippen.
8. Sicherstellen, dass der Schieberegler für die Spindel Geschwindigkeit über 100 % steht und dann so lange an der Stellschraube auf dem Potentiometer drehen bis das Multimeter etwa 10V anzeigt.
9. Fertig.

#### **Anschuss einer Fräse(Ein/Aus)**

Normale luftgekühlte Fräse. Drehzahlregelung an der Fräse selbst. Achtung, laut.\
[![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/3bATAmq)

Der Fräsmotor wird über ein Relais mit der Steuerung verbunden. Es sollte ein Solid State mit Nulldurchgangsschaltung verwendet werden. Hier ist ein Beispiel: [Ebay – RM1A23D25](https://www.ebay.de/sch/i.html?\_from=R40&\_trksid=m570.l1313&\_nkw=rm1a23d25+&\_sacat=0\&mkcid=1\&mkrid=707-53477-19255-0\&siteid=77\&campid=5338665749\&customid=\&toolid=10001\&mkevt=1). Achtung, je nach Stromentnahme kann das Relais heiß werden und muss gekühlt werden. Hier ist zum Beispiel ein passender Kühlkörper: [Amazon – Kühlkörper](https://amzn.to/2OfLozT).\
Die typischen mechanischen 5V Relais für z.B. Arduinos sind nicht geeignet. Diese können Störungen verursachen und geben auch des Öfteren mal den Geist auf.

#### **Anschluss Fräse mit externer Drehzahlsteuerung**

<figure><img src="https://blog.altholtmann.com/wp-content/uploads/2020/07/amb-fr%C3%A4se.jpg" alt=""><figcaption></figcaption></figure>

Die Fräse kann hier ohne ein Relais direkt an dem OPEN-CNC-Shield angeschlossen werden. Das braune Kabel kann entweder an COM1 angeschlossen werden, oder direkt an das Netzteil zur Stromversorgung der Platine angeschlossen werden.

#### **Anschluss eines Frequenzumrichters(China Spindel)**

Verbindungstabelle:

Achtung, damit die **Drehzahlsteuerung** funktioniert muss der Jumper bei **VI/VR** wie im obigen Bild gesetzt sein. Ansonsten wird die Drehzahl weiterhin über den Poti am FU gesteuert.

Weitere Informationen zu Einstellen und Anschließen des Frequenzumrichters findet man auch auf der Estlcam Seite. Dort ist dies noch einmal sehr gut beschrieben: [Estlcam – Chinaspindel](https://www.estlcam.de/chinaspindel.php)

#### **Anschluss eines Lasers**

Hier einmal Beispielhaft der Anschluss eines Lasers. Ich habe folgenden Laser verwendet: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/ebay\_icon-1.png)](https://www.ebay.de/itm/384470342569?hash=item598437dba9:g:8qQAAOSwMtRhewWl\&mkcid=1\&mkrid=707-53477-19255-0\&siteid=77\&campid=5338665749\&customid=\&toolid=10001\&mkevt=1)

Der Laser, den ich verwende braucht 12V, diese hole ich von einem externen Netzteil. Da der Laser nur läuft, wenn über PWM ein Signal heraus gegeben wird, spare ich es mir, den Laser über ein Relais mit Strom zu versorgen. Das wäre aber auch möglich. Das Relais würde dann genauso wie die Spindeln an den Anschluss „Spindel Relais“ auf der Platine angeschlossen werden.\
Damit TTL des Lasers funktioniert braucht dieser ein sauberes PWM Signal von 0 oder 5V. Dieses findet man auf der Platine an dem Anschluss „PWM“. Der Anschluss „VCC“ funktioniert auch dann nicht, wenn der Jumper für 5V gesetzt ist. VCC gibt lediglich eine Analoge Spannung heraus.

Wichtig, bei meinem Laser lagen an dem roten Kabel von TTL 12V an. Diese keinesfalls mit der Platine verbinden. Dabei können Bauteile zerstört werden. Es reicht das gelbe Signal Kabel und das schwarze GND Kabel anzuschließen.

Wie das ganze dann angesteuert wird und Softwareseitig funktioniert zeige ich in diesem Blog Beitrag: [LaserGRBL mit dem OPEN-CNC-Shield](https://blog.altholtmann.com/lasergrbl-mit-dem-open-cnc-shield/)

Link zur angepassten GRBL Firmware: [Gitlab – grbl](https://gitlab.com/cnc-projects1/grbl)

### **SUB-D 37 Anschluss**

Dieser Anschluss führt viele der Arduino Pins nach außen und dient als Schnittstelle für externe Bedienelemente wie zum Beispiel Handräder, Joystick, Buttons etc.

#### **Externes Funk panel**

Dieses Bedienpanel ist Kabellos. Weitere Informationen gibt es auf dieser Seite: [Wireless Control](https://blog.altholtmann.com/uebersicht-status/wireless-control/).

#### **Extension Panel(Anschluss per Kabel)**

Das Extension-Panel wird per Kabel angeschlossen und bietet eine Menge Möglichkeiten für externe Bedienelemente. Hierzu habe ich eine Seite mit weiteren Informationen erstellt:

#### **Handrad**

Dieses Handrad ist schön klein und bietet die wichtigsten Bedienelemente. Es wird per Kabel angeschlossen. Hierzu gibt es einen Beitrag mit einer Zusammenbau-Anleitung: [DIY Handrad unter 70€](https://blog.altholtmann.com/diy-cnc-handrad-mit-joystick/)

#### **Breakout Board / Eigene Entwicklung**

Es soll lieber etwas Eigenes sein? Das ist auch kein Problem. Dafür kann man sich so einen Adapter bestellen und anschließen:

Dort lassen sich dann alle Bedienelemente anschließen und man kann z.B. der Anleitung auf der Estlcam Homepage folgen: [Estlcam Handrad](https://www.estlcam.de/handrad.php) – Dazu einfach nach dem unten Abgebildetem Pin out anschließen.

#### **SUB-D 37 Pinout**

### **Lüfteranschluss**

Es ist möglich an dem 4Pin Lüfter Anschluss auf dem Board auch einen 2Pin Lüfter oder einen 3Pin Lüfter mit 12V anzuschließen. Dabei bitte auf die richtige Verpolung von GND und +12V achten. Diese sind auf der Platine gekennzeichnet.

Die Steuerung eines 4Pin Lüfters mit Drehzahlsteuerung funktioniert nur mit dem zweiten Arduino Mega! Ohne den zweiten Arduino dreht ein PWM-Lüfter vermutlich gar nicht, oder nur sehr langsam.

### **Zweiter Arduino Mega**

Der zweite Arduino Mega mini pro ist optional und kann eingesetzt werden, um weitere Funktionalitäten hinzuzufügen. Dazu gehört Autosquaring, temperaturabhängige Lüfter Steuerung, Ansteuerung eines Displays usw.

#### **Software aufspielen / konfigurieren**

Die Software für den Arduino liegt im [Gitlab – Timos Werkstatt](https://gitlab.com/cnc-projects1/timos-werkstatt) – Repository: [open-cnc-shieldSketch](https://gitlab.com/cnc-projects1/timos-werkstatt/-/tree/master/OPEN-CNC-Shield/software/open-cnc-shieldSketch)

Mögliche Display Layouts(hier unbedingt darauf achten, dass der Displaytyp übereinstimmt):

```
    Layout_128X32_Fan_and_Temp,
    Layout_128X32_Temp_and_Autosquare,
    Layout_128X32_Autosquare,
    Layout_128X64_1
```

#### **Erklärvideo**

#### **Autosquaring**

Autosquaring der Achsen ist vor allem bei DIY Fräse nützlich und soll für die Rechtwinkligkeit der Achsen zueinander sorgen. Gerade bei der MPCNC oder Artisan, welche größtenteils aus dem 3D-Drucker kommen kann es Probleme bei der Rechtwinkligkeit geben, welche hierdurch hoffentlich behoben werden. Beim Autosquaring werden alle Motoren, für welche Autosquaring aktiviert ist gegen ihre jeweiligen Endstops gefahren. Damit die Achsen dann im rechten Winkel sind, müssen die Endstops entsprechend ausgerichtet werden.

Achtung, um Autosquaring zu nutzen, muss ein Taster / Schalter an den passenden Pin des SUB-D 37 Anschlusses angeschlossen werden. Nutzt man das Extension-Panel oder Funk Panel sind hierfür bereits Anschlüsse vorgesehen und herausgeführt.

In diesem Video zeige ich wie man Autosquaring nachrüstet bzw. nutzt und was das ist:

**Autosquare Konfiguration**

Das Autosquaring wird über Jumper konfiguriert und aktiviert.

Hier kann für jede Achse einzeln festgelegt werden, ob diese aktiv ist oder nicht. Ebenso kann die Richtung geändert werden. Sollten die Motoren also in die falsche Richtung nach dem Start des Autosquaring laufen sorgt ein Jumper bei z.B. „Rev X“ dafür, dass die Motoren der x-Achse in die andere Richtung laufen. **Diese Einstellung gilt nur für den Autosquaring Modus!**\
Wenn der Jumper bei „use IN9“ gesetzt ist, wird beim Starten von Autosquaring der Eingang 9 ausgelöst und kann in Estlcam zum Beispiel als Endstopp konfiguriert werden. Damit denkt Estlcam, dass ein Endstopp ausgelöst wurde und versucht nicht selbst die Fräse zu verfahren.

Autosquaring für eine Achse ergibt nur Sinn, wenn es auch zwei Motoren für diese Achse gibt.

**Endstopps anschließen**

Die Endstopps müssen an den richtigen Eingängen angeschlossen sein, damit Autosquaring funktioniert. Hier ist eine Anschlusstabelle:

Es wird im Standard von Programm von NO ( = normally open) Endstopps ausgegangen. Falls die Endstopps als NC angeschlossen werden, muss dies im Arduino Code geändert werden. Siehe dazu folgende Zeile am Anfang des Arduino Codes:

```
// State of endstops - Use LOW for normally open endstops and HIGH for normally closed endstops
// Possible values: LOW // HIGH
// Default: LOW
#define AS_ENDSTOP_STATE_TRIGGERED LOW
```

#### **Lüfter Steuerung mit PWM**

Auf der Platine ist ein 4Pin Lüfter Anschluss. Hier können alle möglichen Arten von 12V Lüfter angeschlossen werden. Darunter ein 2Pin Lüfter(nur mit GND und +12V) ein 3Pin Lüfter oder ein 4Pin Lüfter mit Drehzahlsteuerung.\
Auf dem zweiten Arduino wird standardmäßig alle 10 Sekunden die Temperatur des Onboard Temperaturfühlers ausgelesen und die Drehzahl des Lüfters entsprechend bei Temperaturanstieg erhöht. Dies funktioniert nur mit einem 4Pin PWM Lüfter, und auch dort gibt es Unterschiede in der Frequenz. Ich habe die Platine mit folgendem Lüfter getestet:

<figure><img src="https://blog.altholtmann.com/wp-content/uploads/2020/06/luefter.jpg" alt=""><figcaption></figcaption></figure>

12V PWM Lüfter: [![](https://blog.altholtmann.com/wp-content/uploads/2020/04/amazon\_icon-1.png)](https://amzn.to/2MEU26n)\
Dieser Lüfter ist angenehm leise und funktioniert super mit der Drehzahlsteuerung.\
Wobei sicherlich auch andere Funktionieren. Ich habe halt nur diesen einen getestet.

#### **Externe Temperatur Sensoren**

Es ist möglich weitere externe Temperatur Sensoren anzuschließen. Dafür gibt es auf der Platine einen Terminal mit der Beschriftung „Temp DS18B20“. Hier kann ein oder auch mehrere Sensoren vom Typ DS18B20 angeschlossen werden. Ich weiß gerade nicht genau wie viele, aber sicherlich mehr als man braucht. Diese gibt es unter anderem auch in einer wasserdichten Variante. Da bietet es sich doch an, auch z.B. die Kühlwassertemperatur im Auge zu behalten :-).

<figure><img src="https://blog.altholtmann.com/wp-content/uploads/2020/04/ds18b20_waterproof.jpg" alt=""><figcaption></figcaption></figure>

Standardmäßig wird nur ein Sensor dort ausgelesen und auf dem Display des Bedienpanels ausgegeben. Möchte man mehrere Sensoren auslesen und verarbeiten oder auf irgendeine Art auf die Temperatur reagieren, muss man selbst Hand anlegen und die Funktion selbst auf dem Arduino programmieren. Beizeiten mache ich hierzu mal einen Beitrag.

### **Estlcam**

Folgt…

### **LinuxCNC**

folgt…

#### **Anschluss des Adapters**

Den Estlcam Arduino abziehen und dafür einen der LinuxCNC Adapter aufstecken.

#### **LPT / Parallel Port verbinden**

Hier einmal die Pinbelegung der LPT Anschlüsse:

**LinuxCNC Adapter v1.0**

**LinuxCNC Adapter 6Achs v1.0**

#### K**onfiguration der CNC**

Folgt

### **LaserGRBL**

Hierzu habe ich einen Beitrag erstellt: [LaserGRBL mit dem OPEN-CNC-Shield](https://blog.altholtmann.com/lasergrbl-mit-dem-open-cnc-shield/)

### **FAQ – Häufig gestellte Fragen**

#### **Wieso zeigt Eingang 8 in Estlcam immer ausgelöst an?**

Das liegt daran, dass Estlcam den Arduino Pin D13 für den Eingang 8 nutzt und dieser leider bei den Arduinos meist mit der internen LED verbunden ist. Zum Glück ist diese überflüssig und kann einfach entfernt werden. Ich mache das immer mit einem Cuttermesser und hebel die aus.\
Man kann selbstverständlich auch vorsichtiger Vorgehen und diese auslöten. Dann hat man die Möglichkeit diese später wieder anzulöten. In diesem kurzen Video zeige ich, wie ich das immer mache:

This website uses cookies to improve your experience. We'll assume you're ok with this, but you can opt-out if you wish. Cookie settingsACCEPT
