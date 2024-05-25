---
description: Hier wird die Inbetriebnahme in Kürze beschrieben.
---

# Inbetriebnahme

### Sicherheitshinweise

{% hint style="danger" %}
Das Platine mitsamt seiner Erweiterungen darf nur von qualifiziertem Fachpersonal installiert und in Betrieb genommen werden. Lesen Sie bitte die Dokumentation sorgfältig durch und beachten Sie alle Anweisungen genau. Eine unsachgemäße Installation oder Bedienung des Geräts kann zu Beschädigungen der Elektronik oder der Maschine führen und Gefahren für die Gesundheit des Bedienungspersonals zur Folge haben. Abhängig vom Gefahrenpotential der Maschine sind eventuell zusätzliche Sicherheitsmaßnahmen erforderlich, wie z.B. Türverriegelung und Stillstandsüberwachung. In der Regel müssen solche Sicherheitsfunktionen mit externen Schaltungen rein elektromechanisch realisiert werden und dürfen nicht allein von Software und PC-Hardware abhängig sein. Der Anlagenhersteller, der die Platine und andere Komponenten zur Gesamtanlage zusammenbaut, und der Anlagenbetreiber sind für die Einhaltung der gesetzlichen Vorschriften verantwortlich.
{% endhint %}

## Quick Start

#### Integrierter ESP32

Der ESP32 auf dem Board wird bei Auslieferung bereits mit der neuesten Firmware bespielt. Diese kann selbstverständlich auch selbst aktualisiert oder angepasst werden. Weitere Informationen zum ESP32 finden sich hier: [ESP32](https://chatgpt.com/g/g-n7r1op9pe-timos-werkstatt-docs-bot/c/23e6a86c-1ce2-43db-b848-2218e53c0226).

Nach dem Aufspielen der Firmware bzw. im Auslieferungszustand befindet sich der ESP32 im "Ruhemodus" und hat keinen Einfluss auf die Steuerung. Erst nach der Einrichtung über das Webinterface werden die verschiedenen Funktionen je nach Konfiguration aktiviert.

Sobald die Platine mit Strom versorgt wird, erstellt der ESP32 einen WiFi-Hotspot mit dem Namen "OCS2-XXXXX". Zu diesem kann man sich mit einem Rechner oder Handy verbinden.

{% hint style="info" %}
Es sollten andere Netzwerkverbindungen deaktiviert werden, und bei einem Handy sollten mobile Daten vorübergehend ausgeschaltet werden. Dies ist notwendig, da das Handy oder der PC Schwierigkeiten haben kann, wenn das Internet über WiFi nicht erreichbar ist. Daher ist es am besten, alle anderen Verbindungen zu deaktivieren.
{% endhint %}

Ist man mit dem WLAN verbunden, kann der Browser geöffnet werden und über die Adresse 192.168.4.1 können alle Einstellungen vorgenommen werden. Die Einstellungen werden direkt gespeichert, aber erst nach einem Neustart des ESP32 aktiv.

{% hint style="info" %}
Nachdem alle Einstellungen vorgenommen und die Steuerung eingerichtet sind, wird empfohlen, den WLAN-Hotspot des ESP32 abzuschalten (dies ist in der Webkonfiguration möglich). Der Hotspot kann jederzeit wieder eingeschaltet werden, wenn Änderungen an den Einstellungen vorgenommen werden müssen. Beim OCS2 mini kann dies über den "Function"-Taster auf der Platine erfolgen.
{% endhint %}

### Motortreiber

Siehe [#motortreiber](anschluesse-jumper.md#motortreiber "mention")

### Eingänge / Ausgänge

Siehe [#eingaenge](anschluesse-jumper.md#eingaenge "mention"), [#ausgaenge](anschluesse-jumper.md#ausgaenge "mention") oder direkt [ein-und-ausgaenge-nutzen.md](../guides-zubehoer/ein-und-ausgaenge-nutzen.md "mention") für Beispiele.

### Controller

Für den Anschluss und die Funktion der ControllerModules finden sich hier Informationen: [controllermodules](../controllermodules/ "mention") oder auf der Seite/Dokumentation des jeweiligen Herstellers.
