<div align="center">

# ★ N.I.C. ★

**Native Intellect Community** — jednoduché osvědčené principy, standardní hardware, otevřené návrhy.

[English](https://github.com/Project-NIC) · **Čeština** · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/README.ru.md)

[Co je NIC?](#co-je-nic)

</div>

---

# NIC-Arduino

**Software pro ukládání, přenos a prohlížení dat z malých zařízení** — formát záznamu odolný proti
výpadku, volitelná komprese a šifrování, mosty dovnitř a ven, exportéry pro seismické
a geomagnetické sítě a prohlížeč. **Uzavřeno ve verzi 1.2 — finální verze.**

→ **[Project-NIC/NIC-Arduino](https://github.com/Project-NIC/NIC-Arduino)**

<details>
<summary><b>Moduly</b> — osm</summary>

| modul | co to je |
|---|---|
| [**NIC-MLA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mla) | Matroshka Logging Archive — základní formát záznamu, jeden soubor odolný proti výpadku |
| [**NIC-DMD**](https://github.com/Project-NIC/NIC-Arduino/tree/main/dmd) | Delta Markov Duda — volitelná komprese |
| [**NIC-KSF**](https://github.com/Project-NIC/NIC-Arduino/tree/main/ksf) | Kolmogorov Shannon Feistel — volitelné šifrování |
| [**NIC-GLUE-IN**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-in) | zápis dat do záznamu MLA |
| [**NIC-GLUE-OUT**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-out) | čtení a export záznamu MLA — CSV, SQLite, … |
| [**NIC-MSEED**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mseed) | záznam MLA → miniSEED (ObsPy / SeisComP / FDSN) |
| [**NIC-IAGA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/iaga) | záznam MLA → IAGA-2002 (INTERMAGNET / SuperMAG) |
| [**NIC-VDE**](https://github.com/Project-NIC/NIC-Arduino/tree/main/vde) | Volkov Data Ecosystem — procházení a export záznamů MLA |

</details>

<br>

---

# NIC-Heimdall

**Jedna soběstačná měřicí stanice pro pevnou Zemi, atmosféru a ionosféru** — skříň s centrálou,
hodinami a kartami a k tomu jednotky, které daná lokalita potřebuje, vše na jedné taktované
sběrnici. Vyměňte jednotky a je to jiný přístroj na stejné sběrnici a se stejným kódem.
**Verze 0.2 — koncept ve fázi návrhu:** každá deska popsaná do poslední součástky, zatím nic
postaveno. README jsou v angličtině, češtině a ruštině.

→ **[Project-NIC/NIC-Heimdall](https://github.com/Project-NIC/NIC-Heimdall)**

<details>
<summary><b>Skříň</b> — centrála, hodiny, napájení, karty, přenos</summary>

| část | co to je | sběrnice · typ |
|---|---|---|
| [**Mayak**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak) | centrála — datalogger a spojení ven (Wi-Fi, modem, BLE), archiv na dvou kartách microSD | NodBus 1 |
| [**Kronos**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos) | hodiny — TCXO řízený z GNSS, takt sítě a sekunda do každé karty | — |
| ↳ [**Polaris**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos/polaris) | GNSS frontend Kronosu, kupovaný — přijímač jen pro čas a anténa na nosné desce | — |
| [**Hermes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/hermes) | převodník BMS/MPPT — čte pro centrálu kupovanou baterii a nabíječ | — |
| [**Bifrost**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost) | master sběrnice NodBus — čtyři odbočky bod–bod, měď do 500 m, dál sklo | NodBus 2 |
| ↳ [**Argus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost/argus) | tatáž karta jako master NodBus mini — čtyři segmenty pro malé jednotky | NodBus 3 |
| [**Galvani**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/galvani) | přenosová vrstva — jedenáct desek; vše, co opouští skříň, projde jednou z nich | — |
| [**Mimir**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mimir) | mini-Heimdall — centrála, hodiny, dvě karty, Palatine a Hermes na jedné desce | — |
| [**Proteus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/proteus) | nejmenší úplná centrála stanice, jedna deska do slotu 1-DIN — pro vozidlo nebo lokalitu s jednou jednotkou | — |

</details>

<details>
<summary><b>Jednotky</b> — co stanice měří</summary>

| jednotka | co měří | sběrnice · typ |
|---|---|---|
| [**Quake**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quake) | pohyb půdy, místní události a náklon | NodBus 5 |
| [**Tesla**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla) | blesky — sferiky VLF, každý impulz časovaný podle hodin sítě | NodBus 7 |
| ↳ [**Pip**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/pip) | nosné dlouhých vln — oblast D a čas z dlouhých vln; deska Tesly | NodBus 12 |
| ↳ [**Steinmetz**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/steinmetz) | poruchy na elektrických vedeních, z vozidla nebo z lokality; deska Tesly | NodBus 13 |
| [**Marconi**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/marconi) | ionosféra v pásmu KV — úrovně vysílačů 0,5–16 MHz, pasivní ionogram | NodBus 4 |
| [**Sputnik**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sputnik) | GNSS — celkový obsah elektronů a čas stanice, je-li osazen | NodBus 8 |
| [**Palatine**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine) | meteorologický základ — čtyři větve ModBus pro kupovanou meteosadu a vlastní moduly | NodBus 6 |
| ↳ [**Chinook**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine/chinook) | kvalita ovzduší — kupované jednotky na větvích Palatine | — |
| [**Quark**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark) | radiace — dvě provedení, trubicemi a scintilací | — |
| ↳ [**Quark-Tubes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes) | každá trubice počítaná na jedné desce — trubice GM, Helion a Gadolin pro neutrony | mini 2 |
| ↳ [**Photon**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/photon) | gama a rentgenové záření scintilací, četnost i energie | NodBus 9 |
| ↳ [**Positron**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/positron) | beta obou znamének, na stejné desce s kanálem Neutron | NodBus 11 |
| [**Gauss**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss) | pomalé geomagnetické pole — uzavřená magnetometrická sonda | mini 1 |
| [**Pascal**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pascal) | tsunamimetr na mořském dně | mini 3 |
| [**Pluvius**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pluvius) | srážky, vážením | ModBus 5 |
| [**Ceres**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres) | vlhkost a teplota půdy, přes sklo | ModBus 6 |
| ↳ [**Sakura**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres/sakura) | ovlhčení listů — deska Ceres v korunách | ModBus 7 |
| [**Babel**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel) | jakýkoli senzor → Modbus RTU, převedeno u senzoru | ModBus 4 |

</details>

<details>
<summary><b>Stanice jako celek a software</b></summary>

| část | co to je |
|---|---|
| [**Atlantis**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/atlantis) | stavba do vody — Pascal a Gauss u pobřeží; dlouhá hluboká trasa je odložená |
| [**Daedalus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus) | stavba stanice — stožár, uzemnění, skříň, šachta, kabely |
| [**Gaia**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gaia) | atlas umístění — kam po planetě stanice patří |
| [**HMC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md) | Heimdall Matryoshka Container — archiv stanice, od karty po server |
| [**HCC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HCC.md) | Heimdall Compression Codec — bezeztrátový, sloupec po sloupci; referenční implementace v Pythonu s testy |
| [**Exporters**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/EXPORTERS.md) | archiv ve formátech, které svět přijímá — miniSEED, IAGA-2002, RINEX, BUFR, CSV, SQL, … |
| [**Server**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md#on-the-server) | soubory jako závazný archiv, katalog nad nimi a prohlížeč |
| [**Handset**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak/handset) | aplikace pro uvedení do provozu — telefon u otevřené skříně, přes BLE |

</details>

<br>

---

# NIC-BumbleBee <sub><i>Russian Power</i></sub>

**Energetická část — NIC-FPLG, dvoutaktní lineární motor bez klikového hřídele:** dva písty na
jedné ojnici s trubkovým lineárním generátorem uprostřed, běžící v mechanické rezonanci místo
v řízených otáčkách. ~3 kW mechanicky, 1–1,5 kW elektricky; **zdvojený v protifázi** potlačí ~88 %
vlastních vibrací.

→ **[Project-NIC/NIC-BumbleBee](https://github.com/Project-NIC/NIC-BumbleBee)**

<br>

---

# ★ N.I.C. ★
## NIC — Native Intellect Community
### Viva la résistance! ✊

---

## Co je NIC?

NIC je pro lidi, kteří:

- Využívají jednoduché a osvědčené principy
- Jsou ochotní testovat a tvořit
- Pracují se standardizovaným hardwarem a prostředím
- Nepotřebují nafouklá řešení, aby dokázali, že něco umí

NIC je revoluční hnutí všech soudruhů a soudružek, kterým nevyhovuje dnešní přeplácaný a zbytečně složitý svět.

*"V jednoduchosti je síla."*

★ **Viva la résistance!** ★

---
[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://opensource.org/licenses/MIT)
