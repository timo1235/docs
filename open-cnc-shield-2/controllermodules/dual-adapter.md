---
cover: ../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# Dual Adapter

Dieser Adapter wird auf den Steckplatz für Controllermodule auf dem OCS2 aufgesetzt und bietet Platz für zwei zusätzliche Module. Dadurch ist es möglich, zwei unterschiedliche Controllermodule auf einem OCS2 zu betreiben. Über einen Schalter am Dual-Adapter lässt sich komfortabel zwischen den beiden Modulen wechseln. Es ist jedoch zu beachten, dass die Maschine zu jedem Zeitpunkt nur durch ein Modul gesteuert werden kann.

Ein praxisrelevantes Beispiel wäre der Einsatz des Controllermoduls FluidNC für Laseranwendungen, während das Controllermodul Estlcam für sämtliche Fräsoperationen genutzt wird.

Hier ein kurzes Video dazu:



### Überblick

* Nutzung zweier ControllerModule ohne umstecken
* Wechsel, welches Modul aktiv ist, mit einem Schalter
* Folgende Signale werden umgeschaltet/getrennt:
  * STEP und DIR für alle 6 Achsen
  * Spindel on/off
  * Spindel PWM
  * Alle 8 Ausgänge
* Folgende Signale liegen an beiden ControllerModules an(generell alle Eingangssignale):
  * Eingang 1-16
  * Encoder A/B
  * Motor Start (Bedienteil)
  * Programm Start (Bedienteil)
  * OK-Taste (Bedienteil)
  * Feedrate (Bedienteil)
  * Rotation Speed (Bedienteil)
  * Joystick X/Y/Z (Bedienteil)
  * Auswahl X/Y/Z (Bedienteil)
  * Speed 1/2 (Bedienteil)
  * ENA/Enable der Motortreiber
  * ALARM\_ALL der Motortreiber
  * I2C vom ESP32

### Schalter&#x20;

Der Schalter besteht aus 3 Pins. Der mittlerer Pin(COM) kann entweder mit "First" verbunden werden oder mit "Second". Passende Schalter hierfür findet man unter dem Namen "SPDT" oder auch "ON-OFF-ON".

Beide ControllerModules sind dauerhaft mit Strom und den oben beschriebenen Signalen verbunden. Es werden nur die erwähnten Signale umgeschaltet.

<figure><img src="../../.gitbook/assets/schalter_dual_adapter.png" alt=""><figcaption></figcaption></figure>

### Kompatibilität

Es sind nicht alle Kombinationen von Controller inkl. verschiedener Konfigurationen durchgetestet. Die folgende Liste/Hinweise wird stetig erweitert.

{% hint style="warning" %}
Es liegt in der eigenen Verantwortung dafür zu Sorgen, dass keine Abhängigkeiten zwischen den ControllerModulen entstehen. Falls die gemeinsam genutzen Leitungen von einem Controller durch Fehlkonfiguration zum Beispiel als Ausgang genutzt werden, kann die Steuerung Schaden nehmen
{% endhint %}

#### ENA/Enable der Treiber

In der derzeitigen Ausführung des Dual-Adapters sind die ENA-Anschlüsse beider Controllermodule dauerhaft miteinander verbunden. Es ist daher unerlässlich, darauf zu achten, dass die Controllermodule die ENA-Funktion nicht aktivieren oder schalten. Keinesfalls dürfen beide Controllermodule gleichzeitig den ENA-Anschluss verwenden - während der Betrieb mit einem aktiven Modul funktioniert, würde das Schalten beider Module - eines auf GND und das andere auf 5V - zu einem Kurzschluss führen, der potenziell die Steuerung beschädigen kann.

Die sicherste Maßnahme ist es, die ENA-Funktion an beiden Controllern nicht zu verwenden. Stattdessen sollten die Motoren mit dem ENA-Jumper direkt auf dem OCS2 Shield in den korrekten Zustand versetzt werden.

In zukünftigen Versionen des Dual-Adapters könnte das Verhalten der ENA-Anschlüsse einer Überarbeitung unterzogen werden, um eine verbesserte Funktionalität zu gewährleisten.

#### Estlcam und FluidNC

Diese Controller-Kombination funktioniert einwandfrei. Der ENA hinweis oben sollte beachten werden. Dazu in der FluidNC Konfiguration `shared_stepper_disable_pin: i2so.12` auskommentieren oder löschen.
