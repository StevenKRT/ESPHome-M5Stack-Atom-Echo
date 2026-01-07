# M5Stack Atom Echo mit ESPHome und Home Assistant

Dieses Repository enthält eine ESPHome-Konfiguration für den **M5Stack Atom Echo** als Sprach-Frontend für Home Assistant.  
Das Gerät nutzt ein integriertes Mikrofon, einen kleinen Lautsprecher sowie Wake-Word-Erkennung (on-device oder über Home Assistant).

---

## Wichtige Einschränkungen

- **Spracherkennungs-Reichweite:** maximal ca. **1–2 Meter**
- **Mikrofon:** stark richtungsabhängig, empfindlich gegenüber Umgebungsgeräuschen
- **Soundqualität:** für Sprachausgabe funktional, **nicht hochwertig**, blechern und leise
- **Nicht geeignet** für größere Räume oder Musik-/TTS-Ausgabe mit Anspruch

Diese Einschränkungen sind hardwarebedingt.

---

## Einsatzbereiche

- Sprachsteuerung in unmittelbarer Nähe
- Starten einfacher Home-Assistant-Aktionen
- Timer und kurze akustische Rückmeldungen
- Test- und Entwicklungsumgebungen für Voice Assist

---

## Funktionen

- Wake-Word-Erkennung (on device oder über Home Assistant)
- Mikrofon- und Lautsprecher-Anbindung über I2S
- Sprachassistent (STT/TTS) über Home Assistant
- LED-Statusanzeige (SK6812 RGB)
- Timer-Funktion mit akustischem Signal
- OTA-Updates
- WLAN-Anbindung mit Fallback-AP
- Factory-Reset per Hardware-Taste

---

## Hardware

- M5Stack Atom Echo
- Integriertes Mikrofon (PDM)
- Integrierter Mini-Lautsprecher
- RGB-Status-LED

AliExpress:  
[M5Stack Offizielles ATOM Echo ESP32 Smart Speaker Development Kit](https://s.click.aliexpress.com/e/_EHiV3vI)

3D-Druck:
[M5Stack Atom Serie - Displayhalterung](https://makerworld.com/de/models/560405-m5stack-atom-series-display-mount?from=search#profileId-479672)

---

## Technische Parameter

| Komponente | Wert |
|----------|------|
| MCU | ESP32 |
| Audio | I2S (Mic + Speaker) |
| Wake Word | On device / Home Assistant |
| LED | SK6812, 1 Pixel |
| Reichweite Sprache | ca. 1–2 m |
| Soundqualität | niedrig |
| Netzwerk | WLAN |

---

## Audio-Hardware (GPIO)

| Funktion | GPIO |
|--------|------|
| I2S LRCLK | GPIO33 |
| I2S BCLK | GPIO19 |
| Mikrofon DIN | GPIO23 |
| Speaker DOUT | GPIO22 |
| LED | GPIO27 |
| Button | GPIO39 |

---

## Home-Assistant-Entitäten

- Voice Assistant
- Media Player (intern)
- Wake-Word-Engine-Auswahl
- LED-Status
- Factory-Reset-Button
- Timer-Status

---

## Wake-Word-Betrieb

Zwei Betriebsarten:

- **On device**  
  Wake-Word-Erkennung direkt auf dem Atom Echo (geringe Reichweite)

- **In Home Assistant**  
  Wake-Word-Erkennung serverseitig, Gerät fungiert als Audio-Endpunkt

Umschaltbar über eine Select-Entity.

---

## Dateien

- `m5stack-atom-echo.yaml` – ESPHome-Konfiguration

---

## Hinweise

- Das Gerät ist für **Nahfeld-Sprachsteuerung** ausgelegt
- Für hochwertige Sprachausgabe oder größere Distanzen ungeeignet
- LED dient ausschließlich als Statusanzeige

---

## Lizenz

Freie Nutzung. Keine Gewährleistung.
