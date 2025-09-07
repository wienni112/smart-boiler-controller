# 💡 Ideen & Konzepte – Smart Boiler Controller

Hier werden alle Ideen, Skizzen, Fotos und Dokumentationen gesammelt.  
Ziel ist es, die verschiedenen Ansätze zur Nachrüstung des Boilers übersichtlich festzuhalten.

---

## 🔧 Steuerungsvarianten

### 1. Relais-/Shelly-Steuerung über Boiler-Kontakte (EVU 5/6)
- **Kontakt 5**: Boiler sperren (bei hohen Preisen)  
- **Kontakt 6**: Schnellheizen/Boost (bei Niedrigpreisen)  
- Umsetzung mit **Shelly Pro 2** oder vergleichbarem Modul.  
- Vorteil: Einfache Umsetzung, nutzt vorhandene Eingänge des Boilers.  
- Nachteil: Nur grobe Steuerung (Ein/Aus, Boost), keine variable Soll-Temperatur.

---

### 2. Motorisierte Temperaturregelung (Knopf drehen)
- Originalknopf ersetzen durch **3D-gedruckten Knopf mit Zahnradkranz**.  
- Kleiner Schrittmotor (z. B. **28BYJ-48** oder **NEMA 11**) dreht den Knopf.  
- Steuerung über **ESP32 + Motortreiber (ULN2003 / DRV8825)**.  
- Vorteil: Vollständige Flexibilität (jede Temperatur zwischen 35–80 °C einstellbar).  
- Nachteil: Mechanisch aufwändiger, mehr Platzbedarf.

---

### 3. Quadratisches Gehäuse („Smart-Knob“)
- Anstelle des Knopfes wird ein **kompaktes Gehäuse** montiert.  
- Enthält: Zahnradknopf, Schrittmotor, ggf. ESP32 + Treiber.  
- Externe Versorgung über **Steckernetzteil (5 V DC-Buchse)**.  
- Vorteil: Motor und Elektronik unsichtbar integriert, saubere Optik.  
- Nachteil: Gehäuse muss speziell konstruiert und angepasst werden.

---

## 📐 Mechanische Umsetzung

- **Knopfaufnahme:** D-Achse wie im Original, damit auf Thermostatstift passt.  
- **Zahnrad:** z. B. Modul 1, ~50 mm Durchmesser, für Übersetzung mit Motor.  
- **Motorposition:** seitlich im Gehäuse mit Halterung.  
- **Optional:** Anzeigeelemente (OLED-Display, LEDs) im Gehäuse.

---

## ⚡ Elektronik

- **Netzteil:** externes 230 V → 5 V Steckernetzteil, Verbindung über DC-Buchse (z. B. 5,5×2,1 mm).  
- **Controller:** ESP32 mit ESPHome → WLAN, MQTT, Home Assistant.  
- **Treiber:**  
  - ULN2003 (für 28BYJ-48)  
  - DRV8825 / TMC2209 (für NEMA 11/17)  
- **Motor:**  
  - Klein & günstig: 28BYJ-48 (~28 mm, 5 V)  
  - Kräftiger & präziser: NEMA 11 (28 mm, 12 V)

---

## 📊 Energiemanagement-Idee
- **Nachts:** nur Grundlast 45 °C  
- **Billigpreis (< 20 ct/kWh):** auf 60 °C hochheizen  
- **Negativpreise oder Wochenende:** auf 70 °C als Speicher  
- **Legionellenschutz:** 1× pro Woche automatisch auf 70 °C  

---

## 📸 Bilder

👉 Hier können Boiler-Fotos, Knopf-Bilder oder CAD-Screenshots eingefügt werden.  
Beispiel:



---

## 📑 Dokumente

👉 Bedienungsanleitungen oder technische Unterlagen kommen hier rein.  
Beispiel:
- [Stiebel Eltron SHZ 80 LCD Anleitung (PDF)](instructionandinstallationmanual_doc-00120268.pdf)  
- [Aktuelles Boiler-Handbuch (PDF)](instructionandinstallationmanual_doc-00060526.pdf)

---

## ✅ Nächste Schritte
- [ ] Fotos & PDFs ins `docs/` Verzeichnis legen  
- [ ] 3D-Design für Ersatzknopf/Gehäuse anlegen  
- [ ] Bauteile-Liste vervollständigen (`hardware/teileliste.md`)  
- [ ] Erste ESPHome-Firmware hochladen (`firmware/esphome_boiler.yaml`)  
