# Autosquaring

Was autosquaring ist, habe ich bereits hier beschrieben: [autosquaring.md](../../cnc-themen/autosquaring.md "mention"). In diesem Guide soll es darum gehen, wie man es am besten mit dem OCS2 einsetzt und Fehler vermeidet.

### Wann ist der richtige Zeitpunkt, um Autosquaring zu starten/durchzuführen?

Der Autosquaring-Prozess sollte stets direkt nach dem Einschalten der Steuerung durchgeführt werden, und zwar bevor jegliche Software, wie beispielsweise Estlcam, gestartet wird. Dies ist notwendig, da die Software die Motoren kontrolliert und den Autosquaring-Prozess stören kann, wenn sie bereits im Betrieb ist.

**Gilt für PCB Version > 2.12:** Ein möglicher Fehler, der auftreten kann, wenn die Software bereits läuft und verbunden ist, besteht darin, dass die Achsen während des Autosquaring-Prozesses nicht in die gewünschte Richtung bewegt werden. Sollte Estlcam die Motorrichtung aktiv gesetzt haben, ist es für den ESP32 nicht mehr möglich, diese während des Autosquaring-Vorgangs zu ändern. Infolgedessen kann es passieren, dass die Motoren gegen die Endanschläge stoßen, wenn der ESP32 versucht, sie von den Endanschlägen wegzufahren, da die Richtung nicht mehr geändert werden kann.

{% hint style="info" %}
Ab PCB Version 2.12 werden die DIR-Signale von ControllerModule beim Autosquaring unterbrochen. Demnach kann der oben beschriebene Fehler nicht mehr auftreten.
{% endhint %}

