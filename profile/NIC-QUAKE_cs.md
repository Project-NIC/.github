# NIC-Quake — Open-hardware distribuovaný MEMS seismograf

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Výzkumný seismograf po tobě chce buď geofony za majlant, které musíš ručně
vyrovnat do roviny, nebo boj s kapacitními čidly, co ujíždějí s každou změnou
teploty a vlhkosti. NIC-Quake jde jinou cestou.

Čidlo je MEMS akcelerometr — tři osy na jednom hermeticky uzavřeném křemíkovém
čipu, kalibrovaný z výroby, digitální výstup. Jeho seismická hmota rezonuje
nahoře v kHz, zatímco seismická energie zůstává pod 20 Hz, takže se nikdy
nepotkají. Uzel je zalitý v polyuretanu a přišroubovaný do skály nebo základu,
zapečetěný na celý život, bez jediného knoflíku k otáčení: firmware vezme klidový
stav čidla jako nulu a z vektoru zemské gravitace si sám určí absolutní orientaci.
Nainstaluj ho našikmo — on už ví, kde je dole.

Uzly se řetězí přes obyčejný Cat-6 v RS-485 lince, až osm na segment. Místo aby
věřily NTP nebo softwarovým časovým razítkům, master rozvádí hardwarový hodinový
signál po vlastním páru vodičů a fázově zamkne celý řetěz na nanosekundy. Data
padají do zbytku stacku: NIC-DMD je komprimuje, NIC-MLA je crash-safe uloží do
jednoho souboru, NIC-KSF zašifruje linku, NIC-MSEED je předá světu seismologie.

Architektura drží a datová cesta je postavená. PCB, firmware a polní testy jsou
ještě před námi — tohle repo je zadání, ne výsledek. Hledáme lidi, kteří dokážou
říct „nevím, ale zkusil bych to" — a pak to zkusí.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
