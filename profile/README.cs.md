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

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Heimdall.jpg" width="300" alt="Heimdall"/></p>

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

# NIC-Strelka

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Strelka.jpg" width="300" alt="Strelka"/></p>

**Pohyb zvířete pro veterinární vyšetření** — malé jednotky na nohou, trupu a hlavě psa, koně
nebo krávy zaznamenávají, jak se zvíře hýbe, všechny na jednom společném čase. Nohy, trup a hlavu
tak jde položit vedle sebe krok po kroku. Živě v telefonu nebo v počítači, celý záznam potom. Má
nahradit levné sady senzorů, které se dnes prodávají: za jejich cenu nebo levněji, a v každém
případě lépe. Měří jen pohyb, ne kudy zvíře chodí; všechno je na zvířeti, žádná kamera ani
chodník.

**Živý náhled** rychlostí 50 nebo 100 Hz, jako kvaterniony, které Belka spočítá z hodnot
akcelerometru a gyroskopu, nebo surové kroky; **na kartu** se ukládají surová data v plné rychlosti snímání.
**Vibrace, pokusně:** když to hardware umožňuje, chceme zkusit i vyšší vzorkování, až do maxima
snímače, pro pokusná měření vibrací na strojích a podobně.

→ **[Project-NIC/NIC-Strelka](https://github.com/Project-NIC/NIC-Strelka)** — beta 0.7: celý návrh na papíře, firmware sestavený, aplikace začatá, nic zatím neběželo

<details>
<summary><b>Části</b> — jednotka, velitel, krabička, stanice, aplikace</summary>

| část | co to je |
|---|---|
| **Belka** | jednotka na zvířeti, se snímačem a kartou, v sadě jich je 1 až 32 |
| **Povodok** | velitel sady: stejná deska jako Belka, bez snímače a karty, jen místo BM20F nese kombo Fanstel WM02C20C — nRF54LM20A a k němu Wi-Fi 6 Nordic nRF7002, používané jen na 5 GHz; dává sadě společný čas a první z nich sbírá celou sadu a předává ji telefonu nebo počítači přes USB nebo Wi-Fi |
| **Budka** | krabička, ve které Belka bydlí: utěsněné pouzdro Hammond 1551, okénko pro světlo, uchycení |
| **nabíjecí stanice** | nabíjecí stanice pro celou sadu s rozbočovačem USB: každá Belka v ní je disk a počítač je zkopíruje všechny najednou |
| **Pušinka** | aplikace v telefonu nebo počítači, začatá ve Flutteru: jeden kód pro Android, iPhone, Windows, macOS a Linux, její základ je v repozitáři; časem případně celé aplikace |

</details>

<details>
<summary><b>Co je v Belce</b> — moduly a součástky</summary>

- modul Fanstel BM20F: procesor a rádio Nordic nRF54LM20A, vlastní rádio sady na 2,4 GHz, anténa na plošném spoji
- snímač pohybu TDK ICM-42686-P: akcelerometr ±32 g a gyroskop ±4 000 °/s; na stejné plošce i ICM-42688-P, ±16 g
- vlastní karta microSD uživatele ve slotu se zámkem, na celý záznam
- článek LiFePO4 LTOPOW LFP103042, 3,2 V, 720 mAh
- nabíječka TI BQ25170 a palivoměr ADI MAX17055
- dva stabilizátory TI TPS7A2030 na 3,0 V
- pětipinový magnetický kontakt pro nabíjení a USB, zapojený souměrně, takže jde nasadit oběma směry, s ochranou vstupu
- dva Hallovy spínače TI DRV5032: jednotka se ovládá přiloženým magnetem místo tlačítek, aby krabička zůstala vodotěsná
- dvoubarevná LED

</details>

<br>

---

# NIC-CrazyIvan

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-CrazyIvan.jpg" width="300" alt="Crazy Ivan"/></p>

**Neurální oblek** — až 582 elektrod a 98 pohybových senzorů, 56 z nich v rukavicích a ponožkách,
na obleku složeném z dílů: rukáv, nohavice, trup, čelenka. Vlastní signály svalů a pohyb těla jdou do počítače v batohu,
Radxa ROCK 5T s vlastním NPU nebo až se dvěma AI akcelerátory Hailo-10H, a celé tělo se
stává ovladačem počítače nebo hry. Vedle toho pomůcka pro rehabilitaci: lékař vidí, který sval
pracuje a jak silně. **Coming soon™.** No, zas *tak* brzy ne.

→ **[Project-NIC/NIC-Crazy_Ivan](https://github.com/Project-NIC/NIC-Crazy_Ivan)** — beta 0.5: cesta od kůže k modulu, dva ADS1298 na modul a hlava na dvou ADS1299, 280 kanálů při 1 920 SPS, rukavice a ponožka na jedné desce každá, malý procesor na prst, materiály a zdroje elektrod; stále na papíře, nic ještě není postaveno;
README česky, ostatní stránky anglicky

<details>
<summary><b>Části</b> — oblek, hlava, rodina v batohu, asistenti</summary>

| část | co to je |
|---|---|
| [**Rubaška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/rubaska) | košile: oblek sám, díly se snímacími moduly, Rebjata, rukavice Vešč a ponožka Nosok, elektrody |
| [**Bogatyr**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/bogatyr) | bohatýr: kde na těle sedí každá elektroda a každý pohybový senzor, sval po svalu, a proč |
| [**Nataša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/natasa) | jednotka v čelence: sluchátka, dva mikrofony, vibrace a tlačítka |
| [**Mamka**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/mamka) | máma, základní deska: hodiny celého obleku, zvukový most, budiče linek a napájení obleku |
| [**Baťa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/bata) | táta, počítač v batohu: Radxa ROCK 5T, s Umnicí, Hailo-10H, nebo jen s vlastním NPU |
| [**Terem**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/terem) | komnata dcer: deska v obou slotech M.2 ROCKu 5T, jeho dvě Hailo-10H, každé s vlastním zdrojem |
| [**Babuška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/babuska) | babička: baterie a její BMS, batoh s pevnou skořepinou |
| [**Porjadok**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/porjadok) | pořádek: co platí pro každý modul, procesor, firmware a spoje |
| [**Soňa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/sona) | asistentka pro neslyšící: pořád poslouchá a vibrací říká, co se kolem děje |
| [**Míša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/misa) | asistent, hlídač: radar a ultrazvuk hlídají překážky a varují sluchátky a čelenkou |
| [**Taťána**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/tatana) | asistentka: píše, co diktuješ, a předčítá text, knihy včetně |
| [**Nikita**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/nikita) | asistent: doba hudby jako vibrace |
| [**Pomoščnik**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/pomoscnik) | asistent, pomocník: podívá se na součástku, přečte její označení a najde ji, s brýlemi a kamerami |

</details>

<br>

---

# NIC-Sluchalo

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Sluchalo.jpg" width="300" alt="Sluchalo"/></p>

**Co je ve zdi, poznané podle stínu, který skrz ni vrhá Wi-Fi** — ruční hlava s jedenácti
přijímači Wi-Fi se posouvá po jedné straně zdi a malá krabička za druhou stranou vysílá; kabel,
trubka nebo ocelový profil mezi nimi pole zeslabí a hlava zmapuje kde. U zděných stěn do zdi
navíc ťuká a poslouchá. Hlava má průměr 167 mm: kruh devíti antén 30 × 29 mm na kružnici
o poloměru 65,8 mm kolem zkřížené dvojice, ke zdi 15 mm pěny s tvrdou kluznou fólií, asi 0,36 kg
bez krabice, asi tři hodiny na dvou článcích 18650. Každé nastavení i všechna surová data
zůstávají otevřená.

→ **[Project-NIC/NIC-Sluchalo](https://github.com/Project-NIC/NIC-Sluchalo)** — 0.1, koncept: fyzika spočítaná, hlava a její elektronika na papíře; nic ještě není postavené ani změřené; README česky, koncept anglicky

<details>
<summary><b>Části</b> — lucerna, kruh, datel a ostatní</summary>

| část | co to je |
|---|---|
| **Fonar** | lucerna: vysílač za zdí, dvě desky ESP32-C5 se zkříženými anténami, které se střídají |
| **Kolchoz** | kolchoz: kruh devíti přijímačů, které pracují jako jeden, a zkřížená dvojice uprostřed — jedenáct ESP32-C5 na jedněch hodinách |
| **Datel** | datel: ťukání plastovou tyčinkou uprostřed, osm mikrofonů kolem ní |
| **Razvedčik** | zvěd: dva optické snímače pohybu, které sledují hlavu po zdi |
| **Gensek** | generální tajemník: jeden STM32H7A3 nade vším |
| **Pajok** | příděl: dva články 18650 |
| **Gradusnik** | teploměr: tepelný snímač, odložený |

</details>

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
