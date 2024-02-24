# Allgemein

###

<div>

<figure><img src="../.gitbook/assets/table router shield 2 (1).jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/table router shield 3 (1).jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/table router shield 4 (1).jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/table router shield (1).jpg" alt=""><figcaption></figcaption></figure>

</div>

### **Beschreibung**

Dieses „Table Router Shield“ ist für die vollautomatische Steuerung der Höhe einer Untertisch-Fräse entworfen worden. Für die Steuerung der Funktionen wird ein ESP32 genutzt. Tatsächlich ist das Einsatzgebiet nicht auf eine Untertisch-Fäse begrenzt. Es kann für alle Anwendungen genutzt werden, bei denen ein Stepper verfahren wird.

### **Funktionen**

* ESP32 mit DualCore Funktion um den Stepper-Motor und das Display unabhängig voneinander zu verwenden
* Steckplatz für einen Aufstecktreiber im Pololu-Design. Das heißt es können z.B. DRV8825, A4988 oder auch die sehr geräuscharmen TMC2209 verwendet werden
* Anschlüsse für die Nutzung externer Treiber, falls der Motor mehr Power benötigt
* Button-/Schalter-Anschlüsse für:
  * Werkzeugwechsel
  * Werkzeuglängenmessung
  * OK-Knopf zum Anfahren der Soll-Position
  * Modus-Knopf, um in den Direkt-Modus zu wechseln(Achse verfährt direkt beim Betätigen des Encoders)
  * Ein/Ausschalten einer Spindel
  * Poti zum Einstellen der Geschwindigkeit der Spindel
* Analoger 0-10V Ausgang für die Steuerung einer Spindel
* Anschluss eines I2C Displays
* Anschluss eines Encoders
* Anschlüsse für Enstops(Limit oben, Limit unten und einen für die Werkzeuglängenmessung)
* 12V Ausgang für z.B. einen externen Schrittmotor Treiber
* 5V Ausgang für z.B. LEDs in den Schaltern
* Alle Ein- und Ausgänge sind mit LEDs versehen, um den aktuellen Auslösezustand anzuzeigen
* Verpolungsschutz am 12V Eingang
* Selbst zurücksetzende Sicherungen, falls Kurzschlüsse verursacht werden
* Pin out um weitere Funktionen zu realisieren
* Fertige Software zum Aufspielen
