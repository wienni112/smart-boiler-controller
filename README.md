# Smart Boiler Controller 🔥💧

## 📌 Projektidee
Der **Smart Boiler Controller** ist ein DIY-Projekt zur intelligenten Steuerung von Warmwasserboilern.  
Ziel ist es, vorhandene Elektroboiler so nachzurüsten, dass sie flexibel auf **dynamische Strompreise** (z. B. Tibber) oder **PV-Überschuss** reagieren.  
So wird der Boiler zu einem **thermischen Speicher** – ähnlich wie eine Batterie, nur günstiger und langlebiger.

---

## 🎯 Ziele
- Boiler **intelligent ein- und ausschalten** abhängig von Strompreisen.  
- Erweiterung um **variable Temperaturregelung** (z. B. nachts 45 °C, bei Niedrigpreis 60–70 °C).  
- Mechanische Nachrüstung mit **3D-gedrucktem Knopf/Zahnrad** und kleinem **Schrittmotor**.  
- Anbindung an **Home Assistant** / **MQTT**.  
- Dokumentation von Hardware, Firmware, CAD und Daten in diesem Repo.  

---

## 🛠️ Mögliche Ansätze
1. **Shelly / Relais-Steuerung**  
   - Nutzung der EVU-Kontakte (5/6) des Boilers → Sperre/Boost.  
   - Einfache Umsetzung, weniger Eingriff in Mechanik.  

2. **Motorisierte Temperaturregelung**  
   - 3D-gedruckter Ersatzknopf mit Zahnrad.  
   - Schrittmotor (z. B. NEMA 11 oder 28BYJ-48) verstellt die Temperatur automatisch.  
   - Steuerung per ESP32 + ESPHome über WLAN/MQTT.  

3. **Quadratisches Gehäuse**  
   - Motor + Mechanik unsichtbar integriert.  
   - Optional auch Elektronik (ESP32, Treiber, Netzteil).  
   - Versorgung über externe **DC-Buchse** (z. B. 5V vom Steckernetzteil).  

---

## 📂 Repository-Struktur
smart-boiler-controller/
├── README.md # Projektübersicht (dieses Dokument)
├── docs/ # Ideen, Konzepte, Dokumentation
│ └── ideen.md
├── hardware/ # Bauteile, Schaltpläne
│ └── teileliste.md
├── firmware/ # ESPHome/Arduino-Firmware
│ └── esphome_boiler.yaml
└── cad/ # 3D-Modelle (STL/SCAD)
└── knob_v1.scad


---

## 🚀 Nächste Schritte
- [ ] Ideen ausarbeiten und dokumentieren (`docs/ideen.md`)  
- [ ] Bauteile auswählen & Teileliste erstellen (`hardware/teileliste.md`)  
- [ ] Erste Firmware schreiben (`firmware/esphome_boiler.yaml`)  
- [ ] 3D-Design vom Knopf + Gehäuse starten (`cad/`)  
- [ ] Testaufbau am realen Boiler durchführen  

---

## 📊 Motivation
- Durchschnittlicher Tagesverbrauch: ca. 12 kWh  
- Boiler-Heizstab: 7,5 kW → großer Hebel für Lastverschiebung  
- Tibber-Dynamiktarif: Preis-Spreads von –10 ct/kWh bis 60+ ct/kWh  
- Durch smarte Steuerung sind **mehrere Hundert € Einsparung pro Jahr** möglich.

---

## 👥 Mitmachen
Dieses Projekt ist **open source** – gerne Pull Requests oder Ideen einbringen.  
Jede Hilfe beim CAD-Design, Firmware oder Integration in Home Assistant ist willkommen.  

---

## 📖 Lizenz
MIT License – freie Nutzung, bitte teilen & weiterentwickeln 🚀
