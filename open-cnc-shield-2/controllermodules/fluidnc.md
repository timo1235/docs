---
cover: ../../.gitbook/assets/controllermodule_banner.png
coverY: 0
---

# FluidNC

<div>

<figure><img src="../../.gitbook/assets/controller module fluidnc-2-500px.jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/controller module fluidnc-3-500px (1).jpg" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/controller module fluidnc-500px.jpg" alt=""><figcaption></figcaption></figure>

</div>

Dieser Controller ist für den Einsatz von [FluidNC ](http://wiki.fluidnc.com/)gedacht.&#x20;

> FluidNC ist eine CNC-Firmware, die für den ESP32-Controller optimiert ist. Sie ist die nächste Generation der Firmware von den Schöpfern von Grbl\_ESP32. Sie beinhaltet eine webbasierte Benutzeroberfläche und die Flexibilität, eine Vielzahl von Maschinentypen zu bedienen. Dies beinhaltet die Fähigkeit, Maschinen mit mehreren Werkzeugtypen zu steuern, wie beispielsweise Laser+Spindel.

{% embed url="https://youtu.be/efXxKAYP5gM" %}

### Überblick

* Alle 6 Achsen können einzeln verfahren werden. Damit ist Autosquaring direkt mit FluidNC möglich
* 8 Eingänge
* 8 Ausgänge
* Verbindung mit dem PC über USB oder Steuerung per Webinterface
* Micro SD Karten Slot
* Offline Controller fähig (Jobs können direkt von der SD-Karte gestartet werden)
* Kompatibel mit gängigen GRBL Softwares
* Anschluss für OLED Display

### Unterstützung des OCS2 Funktionen

<table><thead><tr><th width="313">Möglichkeiten OCS2</th><th width="432">Unterstützung des FluidNC Adapters</th></tr></thead><tbody><tr><td>6 Achsen</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> Alle 6 Achsen können angesteuert werden</td></tr><tr><td>16 Eingänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span> 8 - Es können die Eingänge 1-8 genutzt werden</td></tr><tr><td>8 Ausgänge</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> 8</td></tr><tr><td>Spindelgeschwindigkeitssteuerung 0-5V, 0-10V oder 5V PWM</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Spindel An/Aus Anschluss zum Schalten eines Relais / Frequenzumrichters</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Externe Bedienelemente</strong></td><td></td></tr><tr><td>Handrad / Encoder</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Motor Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> Ist angeschlossen und kann auf eine Funktion gemapped werden</td></tr><tr><td>Programm Start Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> Ist angeschlossen und kann auf eine Funktion gemapped werden</td></tr><tr><td>OK Taster</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span> Ist angeschlossen und kann auf eine Funktion gemapped werden</td></tr><tr><td>Feedrate (Vorschubgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Rotation Speed (Spindelgeschwindigkeit)</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>3-Achsen Joystick </td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Auwahl X, Y, Z zur Wahl der Achsen für den Encoder</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Speed 1 und Speed 2 zur Einstellung der Encoder Geschwindigkeit</td><td><span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr></tbody></table>

### Pin Mapping

| ESP32 / Shift Register Pin                 | Funktion                   |
| ------------------------------------------ | -------------------------- |
| gpio.1                                     | Frei - Nur am Pinout       |
| gpio.2                                     | Frei - Nur am Pinout       |
| gpio.3                                     | Frei - Nur am Pinout       |
| gpio.16                                    | Frei - Nur am Pinout       |
| gpio.12:low:pu                             | OCS2 OK Button             |
| gpio.13                                    | I2C SCK Pin (OLED Display) |
| gpio.14                                    | I2C SDA Pin (OLED Display) |
| gpio.5                                     |  CS pin für SD-Karte       |
| gpio.18                                    | SPI SCK Pin                |
| gpio.19                                    | SPI MISO Pin               |
| gpio.23                                    | SPI MOSI Pin               |
| gpio.22                                    | I2SO MISO - Shift Register |
| gpio.21                                    | I2SO Data - Shift Register |
| gpio.17                                    | I2SO WS - Shift Register   |
| gpio.25:high                               | OCS2 Spindle PWM           |
| gpio.26:low:pu                             | OCS2 Motor Start Button    |
| gpio.27:low:pu                             | OCS2 Programm Start Button |
| gpio.36 (hat Hardware Pullup)              | OCS2 Eingang 1             |
| gpio.39 (hat Hardware Pullup)              | OCS2 Eingang 2             |
| gpio.34 (hat Hardware Pullup)              | OCS2 Eingang 3             |
| gpio.35 (hat Hardware Pullup)              | OCS2 Eingang 4             |
| gpio.32 (setze ":pu" für Pullup in Config) | OCS2 Eingang 5             |
| gpio.33 (setze ":pu" für Pullup in Config) | OCS2 Eingang 6             |
| gpio.4 (setze ":pu" für Pullup in Config)  | OCS2 Eingang 7             |
| gpio.15 (setze ":pu" für Pullup in Config) | OCS2 Eingang 8             |
| **Shift Register (Outputs)**               |                            |
| i2so.0                                     | OCS2 STEP X                |
| i2so.1                                     | OCS2 DIR X                 |
| i2so.2                                     | OCS2 STEP Y                |
| i2so.3                                     | OCS2 DIR Y                 |
| i2so.4                                     | OCS2 STEP Z                |
| i2so.5                                     | OCS2 DIR Z                 |
| i2so.6                                     | OCS2 STEP A                |
| i2so.7                                     | OCS2 DIR A                 |
| i2so.8                                     | OCS2 STEP B                |
| i2so.9                                     | OCS2 DIR B                 |
| i2so.10                                    | OCS2 STEP C                |
| i2so.11                                    | OCS2 DIR C                 |
| i2so.12                                    | OCS2 ENA                   |
| i2so.13                                    | OCS2 Spindle on/off        |
| i2so.14                                    | Frei - Nur am Pinout       |
| i2so.15                                    | Frei - Nur am Pinout       |
| i2so.16                                    | OCS2 Ausgang 1             |
| i2so.17                                    | OCS2 Ausgang 2             |
| i2so.18                                    | OCS2 Ausgang 3             |
| i2so.19                                    | OCS2 Ausgang 4             |
| i2so.20                                    | OCS2 Ausgang 5             |
| i2so.21                                    | OCS2 Ausgang 6             |
| i2so.22                                    | OCS2 Ausgang 7             |
| i2so.23                                    | OCS2 Ausgang 8             |
| i2so.24 - i2so.31                          | Frei - Nur am Pinout       |

### Pinout&#x20;

Folgendes Pinout steht auf dem ControllerModule zur Verfügung und kann zusätzlich bei Bedarf genutzt werden:

![](../../.gitbook/assets/FluidNC\_Pinout.png)

### Beispielkonfiguration für meine MPCNC

```yaml
name: "OCS2 FluidNC"
board: "OCS2 FluidNC Controller"

stepping:
  engine: I2S_STREAM
  idle_ms: 250
  dir_delay_us: 1
  pulse_us: 4
  disable_delay_us: 0

axes:
  shared_stepper_disable_pin: i2so.12

  x:
    steps_per_mm: 50
    max_rate_mm_per_min: 7000
    acceleration_mm_per_sec2: 500
    max_travel_mm: 1000
    soft_limits: true

    homing:
      cycle: 2
      positive_direction: false
      mpos_mm: 0.000
      feed_mm_per_min: 500.000
      seek_mm_per_min: 1000.000
      seek_scaler: 1.1
      feed_scaler: 1.1

    motor0:
      limit_neg_pin: gpio.36:high
      hard_limits: true
      pulloff_mm: 5
      stepstick:
        direction_pin: i2so.1
        step_pin: i2so.0
    motor1:
      limit_neg_pin: gpio.39:high
      hard_limits: true
      pulloff_mm: 5
      stepstick:
        direction_pin: i2so.7
        step_pin: i2so.6

  y:
    steps_per_mm: 50
    max_rate_mm_per_min: 7000
    acceleration_mm_per_sec2: 500
    max_travel_mm: 1000
    soft_limits: true

    homing:
      cycle: 2
      positive_direction: false
      mpos_mm: 0.000
      feed_mm_per_min: 500.000
      seek_mm_per_min: 1000.000
      seek_scaler: 1.1
      feed_scaler: 1.1

    motor0:
      limit_neg_pin: gpio.34:high
      hard_limits: true
      pulloff_mm: 5
      stepstick:
        direction_pin: i2so.3
        step_pin: i2so.2
    motor1:
      limit_neg_pin: gpio.35:high
      hard_limits: true
      pulloff_mm: 5
      stepstick:
        direction_pin: i2so.9
        step_pin: i2so.8

  z:
    steps_per_mm: 50
    max_rate_mm_per_min: 2000
    acceleration_mm_per_sec2: 100
    max_travel_mm: 1000
    homing:
      cycle: -1

    motor0:
      limit_all_pin: NO_PIN
      stepstick:
        direction_pin: i2so.5
        step_pin: i2so.4
    motor1:
      null_motor:

# I2SO for shift registers
i2so:
  bck_pin: gpio.22
  data_pin: gpio.21
  ws_pin: gpio.17

# SPI for SD Card
spi:
  miso_pin: gpio.19
  mosi_pin: gpio.23
  sck_pin: gpio.18

sdcard:
  cs_pin: gpio.5
  card_detect_pin: NO_PIN

# I2C for OLED Display
i2c0:
  sda_pin: gpio.14
  scl_pin: gpio.13

oled:
  i2c_num: 0
  i2c_address: 60
  width: 128
  height: 64
  radio_delay_ms: 1000

coolant:
  # Ausgang 1
  flood_pin: i2so.16:high
  # Ausgang 2
  mist_pin: i2so.17:high
# probe:
#   pin: gpio.32:low:pu

Laser:
  pwm_hz: 5000
  output_pin: gpio.25:high
  enable_pin: NO_PIN
  disable_with_s0: false
  s0_with_disable: true
  tool_num: 0
  speed_map: 0=0.000% 1000=100.000%
  off_on_alarm: true

control:
  safety_door_pin: NO_PIN
  reset_pin: gpio.12:low:pu
  feed_hold_pin: gpio.26:low:pu
  cycle_start_pin: gpio.27:low:pu
  macro0_pin: NO_PIN
  macro1_pin: NO_PIN
  macro2_pin: NO_PIN
  macro3_pin: NO_PIN
```
