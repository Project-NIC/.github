<div align="center">

# ★ N.I.C. ★

**Native Intellect Community** — simple, proven principles, standard hardware, open designs.

**English** · [Čeština](https://github.com/Project-NIC/.github/blob/main/profile/README.cs.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/README.ru.md)

[What is NIC?](#what-is-nic)

</div>

---

# NIC-Arduino

**The storage, transport and viewer stack for small devices** — a crash-safe log format, optional
compression and encryption, the bridges in and out, exporters for the seismic and geomagnetic
networks, and a viewer. **Closed at v1.2 — the final version.**

→ **[Project-NIC/NIC-Arduino](https://github.com/Project-NIC/NIC-Arduino)**

<details>
<summary><b>The modules</b> — eight</summary>

| module | what it is |
|---|---|
| [**NIC-MLA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mla) | Matroshka Logging Archive — the base log format, one crash-safe file |
| [**NIC-DMD**](https://github.com/Project-NIC/NIC-Arduino/tree/main/dmd) | Delta Markov Duda — optional compression |
| [**NIC-KSF**](https://github.com/Project-NIC/NIC-Arduino/tree/main/ksf) | Kolmogorov Shannon Feistel — optional encryption |
| [**NIC-GLUE-IN**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-in) | write data into an MLA log |
| [**NIC-GLUE-OUT**](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-out) | read and export an MLA log — CSV, SQLite, … |
| [**NIC-MSEED**](https://github.com/Project-NIC/NIC-Arduino/tree/main/mseed) | an MLA log → miniSEED (ObsPy / SeisComP / FDSN) |
| [**NIC-IAGA**](https://github.com/Project-NIC/NIC-Arduino/tree/main/iaga) | an MLA log → IAGA-2002 (INTERMAGNET / SuperMAG) |
| [**NIC-VDE**](https://github.com/Project-NIC/NIC-Arduino/tree/main/vde) | Volkov Data Ecosystem — browse and export MLA logs |

</details>

<br>

---

# NIC-Heimdall

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Heimdall.jpg" width="300" alt="Heimdall"/></p>

**One self-contained measuring station for the solid Earth, the atmosphere and the ionosphere** —
an enclosure with the head, the clock and the cards, and whatever units a site needs, all on one
clocked bus. Swap the units and it is a different instrument on the same bus and the same code.
**Version 0.3 — a design-stage concept:** every board described to the part, the code above the
pins written and tested on a PC, nothing built yet.
Its READMEs read in English, Czech and Russian.

→ **[Project-NIC/NIC-Heimdall](https://github.com/Project-NIC/NIC-Heimdall)**

<details>
<summary><b>The enclosure</b> — the head, the clock, the power, the cards, the transport</summary>

| part | what it is | bus · type |
|---|---|---|
| [**Mayak**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak) | the head — datalogger and uplink (Wi-Fi, a modem, BLE), the archive on two microSD cards | NodBus 1 |
| [**Kronos**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos) | the timekeeper — a GNSS-disciplined TCXO, the network clock and the second to every card | — |
| ↳ [**Polaris**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos/polaris) | Kronos's GNSS front, bought — a time-only receiver and antenna on a carrier | — |
| [**Hermes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/hermes) | the BMS/MPPT converter — reads the bought pack and charger for the head | — |
| [**Bifrost**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost) | the NodBus master — four point-to-point spurs, copper to 500 m, glass beyond | NodBus 2 |
| ↳ [**Argus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost/argus) | the same card as the NodBus mini master — four segments for the small units | NodBus 3 |
| [**Galvani**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/galvani) | the transport layer — eleven boards; anything that leaves the enclosure crosses one | — |
| [**Mimir**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mimir) | mini-Heimdall — the head, the clock, two cards, Palatine and Hermes on one PCB | — |
| [**Proteus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/proteus) | the smallest whole station head, one PCB in a 1-DIN slot — for a vehicle or a one-unit site | — |

</details>

<details>
<summary><b>The units</b> — what the station measures</summary>

| unit | what it measures | bus · type |
|---|---|---|
| [**Quake**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quake) | ground motion, local events and tilt | NodBus 5 |
| [**Tesla**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla) | lightning — VLF sferics, every impulse timed on the network clock | NodBus 7 |
| ↳ [**Pip**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/pip) | longwave carriers — the D-region, and longwave time; Tesla's board | NodBus 12 |
| ↳ [**Steinmetz**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/steinmetz) | faults on power lines, from a vehicle or a site; Tesla's board | NodBus 13 |
| [**Marconi**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/marconi) | the HF ionosphere — transmitter levels 0,5–16 MHz, a passive ionogram | NodBus 4 |
| [**Sputnik**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sputnik) | GNSS — total electron content, and the station's time when fitted | NodBus 8 |
| [**Palatine**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine) | the meteo base — four ModBus arms for the bought weather set and the house modules | NodBus 6 |
| ↳ [**Chinook**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine/chinook) | air quality — bought units on Palatine's arms | — |
| [**Quark**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark) | radiation — two builds, by tubes and by scintillation | — |
| ↳ [**Quark-Tubes**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes) | every tube counted on one board — GM tubes, Helion and Gadolin for neutrons | mini 2 |
| ↳ [**Photon**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/photon) | γ / X-ray by scintillation, counts and energy | NodBus 9 |
| ↳ [**Positron**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/positron) | beta, both signs, with Neutron's channel on the same board | NodBus 11 |
| [**Gauss**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss) | the slow geomagnetic field — a sealed magnetometer sonde | mini 1 |
| [**Pascal**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pascal) | a tsunami gauge on the sea floor | mini 3 |
| [**Pluvius**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pluvius) | precipitation, weighed | ModBus 5 |
| [**Ceres**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres) | soil moisture and temperature, through glass | ModBus 6 |
| ↳ [**Sakura**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres/sakura) | leaf wetness — Ceres's board in the canopy | ModBus 7 |
| [**Babel**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel) | any sensor → Modbus RTU, converted at the sensor | ModBus 4 |

</details>

<details>
<summary><b>The station as a whole, and the software</b></summary>

| part | what it is |
|---|---|
| [**Atlantis**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/atlantis) | the water build — Pascal and Gauss off shore; the long deep run is shelved |
| [**Daedalus**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus) | building the station — mast, earthing, enclosure, vault, cables |
| [**Gaia**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gaia) | the siting atlas — where the stations go across the planet |
| [**HMC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md) | Heimdall Matryoshka Container — the station's archive, from the card to the server |
| [**HCC**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HCC.md) | Heimdall Compression Codec — lossless, column by column; a Python reference with its tests |
| [**Exporters**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/EXPORTERS.md) | the archive in the world's formats — miniSEED, IAGA-2002, RINEX, BUFR, CSV, SQL, … |
| [**Server**](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md#on-the-server) | the files as the archive of record, a catalogue over them, and the viewer |
| [**Handset**](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak/handset) | the commissioning app — the phone at the open enclosure, over BLE |

</details>

<br>

---

# NIC-BumbleBee <sub><i>Russian Power</i></sub>

**The power side — NIC-FPLG, a crankshaft-free two-stroke linear engine:** two pistons on one rod
with a tubular linear generator at its centre, running at mechanical resonance rather than at a
controlled speed. ~3 kW mechanical, 1–1,5 kW electrical; **twinned in anti-phase** it cancels ~88 %
of its own vibration.

→ **[Project-NIC/NIC-BumbleBee](https://github.com/Project-NIC/NIC-BumbleBee)**

<br>

---

# NIC-Strelka

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Strelka.jpg" width="300" alt="Strelka"/></p>

**The motion of an animal, for a veterinary examination** — small units on the legs, the trunk and
the head of a dog, a horse or a cow record how it moves, all on one common time: live on a phone or
a computer, the whole record afterwards. To replace the cheap sensor sets sold today, at their price
or below and better in any case; and, as an experiment, vibration on machines.

→ **[Project-NIC/NIC-Strelka](https://github.com/Project-NIC/NIC-Strelka)** — beta 0.86: the whole design on paper, the boards described for drawing, the firmware built, the application's base with its six menus, nothing run yet; 0.9 comes with the drawn boards

<details>
<summary><b>The parts</b> — the units, the commander, the boxes and the case, the docking, the application</summary>

| part | what it is |
|---|---|
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/belka.jpg" width="90"/><br/>**Belka** | the unit on the animal, with its sensor and its card, 1 to 32 in a set, on Materinka, the base board whose core every unit shares. Ugoljok, for large shocks on the hoof, is described but not made: whoever needs it builds it |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/zvjozdocka.jpg" width="90"/><br/>**Zvjozdočka** | the Belka for industry, with raw data up to 32 kHz: for machines in a hall, a set of its own with its own Povodok |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/kryska.jpg" width="90"/><br/>**Kryska** | the small Belka, for small animals and the ordinary examinations: Fanstel's BM20M, its memory on its board, built sturdy as standard |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/povodok.jpg" width="90"/><br/>**Povodok** | the set's commander, one to four in a set: its own Materinka with Fanstel's WM02C20C, Wi-Fi at 5 GHz, neither sensor nor card; it gives the set its time and passes what it measures to the phone or the computer, by USB or Wi-Fi |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/korabl.jpg" width="90"/><br/>**Korabl** | the box of a unit, each of its own size: the sealed case, its window for the light, its fastening |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/semjorka.jpg" width="90"/><br/>**Semjorka** | the case that carries a whole set |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/stykovka.jpg" width="90"/><br/>**Stykovka** | part of the hardware: the five-pin magnetic contact, on a lead or on a station for the whole set with a USB hub; it serves the charge and USB to a computer alone, a computer copying every unit at once |
| <img src="https://github.com/Project-NIC/NIC-Strelka/raw/main/pictures/pusinka.jpg" width="90"/><br/>**Pušinka** | the application on the phone or the computer, its base in Flutter with its six menus: one code for Android, iPhone, Windows, macOS and Linux |

</details>

<details>
<summary><b>Inside a Belka</b> — the modules and the parts</summary>

- Fanstel's BM20F module: Nordic's nRF54LM20A processor and radio, the set's own radio at 2,4 GHz, an antenna on the board
- the motion sensor, on one land: ST's LSM6DSV16X, ±16 g and ±4 000 °/s, in the Belka; ST's LSM6DSV320X, ±16 g and a second channel to ±320 g, in Ugoljok, for the hoof; TDK's ICM-42686-P, ±32 g and ±4 000 °/s, in Zvjozdočka, for raw data up to 32 kHz
- the user's own microSD card in a locking slot, for the whole record
- a LiFePO4 cell, LTOPOW's LFP103042, 3,2 V, 720 mAh
- Nordic's nPM1300 PMIC: the charge, ship mode as the off, the cell measured for Nordic's fuel gauge, the light's drivers
- two TI TPS7A2030 regulators at 3,0 V
- a five-pin magnetic contact for the charge and USB, wired symmetric so that it goes on either way round, its inlet guarded
- two TI DRV5032 Hall switches: the unit is worked by a magnet held to it instead of buttons, so that the box stays watertight
- a two-colour LED, lit by the PMIC as well

</details>

<br>

---

# NIC-CrazyIvan

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-CrazyIvan.jpg" width="300" alt="Crazy Ivan"/></p>

**A neural suit** — up to 580 electrodes and 108 motion sensors, 64 of them in the gloves and the
socks, on a suit put together from pieces: a sleeve, a trouser leg, the torso, a headband. The muscles' own signals and the body's
motion go to a computer in the backpack, a Radxa ROCK 5T with its own NPU or up to two Hailo-10H AI
accelerators, and the whole body becomes the controller for a computer or a game. Second, an
aid for rehabilitation: a doctor sees which muscle works and how hard.
**Coming soon™.** Well — not *that* soon.

→ **[Project-NIC/NIC-Crazy_Ivan](https://github.com/Project-NIC/NIC-Crazy_Ivan)** — beta 0.6: the ADS1298 on every module and the LSM6DSV16X held to the suit's clock, polyimide strips shielded on both faces, the units potted on the harness with connectors for assembly only, Mamka's converters at 1 MHz, Mrazík the cooling block; still on paper, nothing built yet

<details>
<summary><b>The parts and every name</b> — the suit, the head, the family in the backpack, the assistants</summary>

| part | what it is |
|---|---|
| [**Rubaška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/rubaska) | the shirt: the suit itself, the pieces with their sensing modules, the Rebjata, the glove Vešč and the sock Nosok, the electrodes |
| ↳ [**Kaščej**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/CONSTRUCTION.md#harness-and-washing) | Koschei the Deathless: the harness, a skin-tight overall with the bands and the modules on it, rinsed in clean water |
| ↳ [**Strejda Al**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/CONSTRUCTION.md#harness-and-washing) | Uncle Al, after Big Gay Al of *South Park*: the tight compression overall over Kaščej that presses the electrodes to the body |
| ↳ [**Rebjata**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/HARDWARE.md#sensing-module) | the kids: the sensing modules, Mamka's own children, each one a Rebjonok; two ADS1298, 16 EMG channels and the motion sensors |
| ↳ [**Staršaja**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/HARDWARE.md#sensing-module) | the elder: every sensing unit's main processor, an STM32H523 |
| ↳ [**Bratiški**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/HARDWARE.md#the-glove) | the little brothers: Staršaja's helpers on the glove's and the sock's board, today the switches that hand her each zone of motion sensors in turn |
| ↳ [**Vešč**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/HARDWARE.md#the-glove) | the Thing, the Addams' hand: the glove, one board on the back of the hand, 16 electrodes and up to 24 motion sensors |
| ↳ [**Nosok**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/rubaska/HARDWARE.md#the-sock) | the sock: the glove's board for the foot, worn above the ankle |
| [**Bogatyr**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/bogatyr) | the strongman: the rules, the counts and the motion sensors on the body; the electrodes' places wait for professionals' advice |
| [**Nataša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/natasa) | the unit in the headband: headphones, two microphones, vibration and buttons |
| [**Mamka**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/mamka) | mum, the base board: the clock for the whole suit, the sound bridge, the line drivers and the suit's power |
| ↳ [**Chodiki**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/mamka/HARDWARE.md#clock) | the wall clock with weights: the one clock the whole suit samples by |
| ↳ [**Pupovina**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/porjadok/HARDWARE.md#links-between-boards) | the umbilical cord: the eight lines from Mamka, one a piece of the suit, with power, the clock and data |
| ↳ [**Kormilica**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/mamka/HARDWARE.md#mamkas-own-supply) | the wet nurse: the suit's power on Mamka, the lines' converters that feed her children |
| [**Baťa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/bata) | dad, the computer in the backpack: a Radxa ROCK 5T, with Umnica, the Hailo-10H, or its own NPU alone |
| ↳ [**Umnica**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/bata/HARDWARE.md#umnica) | the clever one: a Hailo-10H, the educated daughter who thinks for dad |
| ↳ [**Borovičok**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/bata/HARDWARE.md#borovičok) | Staričok-Borovičok, the little old mushroom man, Babuška's husband: computer B, the applications and the glasses |
| ↳ [**Ďaďa Sem**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/bata/HARDWARE.md#ďaďa-sem) | Uncle Sam, who lives in the attic and watches everything: the cameras |
| ↳ [**Storož**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/bata/SOFTWARE.md#storož) | the night watchman, our Tron: when something fatal breaks he stops the household and says why |
| ↳ [**Budilnik**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/bata/SOFTWARE.md#budilnik) | the alarm clock: wakes a wearer who has left the suit alone with a line in the headphones, and if nobody answers puts the household to bed |
| ↳ **Nastěnka** | the good stepdaughter of *Mrazík*: the main software |
| ↳ **Macecha** | her stepmother: the strict correcting software that lets nothing through |
| ↳ [**Perevodčica**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/porjadok/SOFTWARE.md#output) | the interpreter: the output's converters for Unreal, Unity, VRChat, a lab or a robot |
| [**Terem**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/terem) | the daughters' chamber: the board in the ROCK 5T's two M.2 slots, its two Hailo-10H with a supply each |
| [**Porjadok**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/porjadok) | order: what holds for every module, the processor, the firmware and the links |
| ↳ [**Pitanije**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/porjadok/HARDWARE.md#power) | food, and a power supply: the suit's power from Babuška down to every module, with its fuses and protections |
| [**Babuška**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/babuska) | grandma: the battery and its BMS, the hard-shell backpack |
| ↳ [**Ključnica**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/babuska/HARDWARE.md#the-bms) | the housekeeper with the keys: the BMS, which decides what goes in and out of Babuška's pantry; her button switches the suit on and off |
| ↳ **Kommunalka** | a communal flat: the backpack, where the whole family lives and shares one kitchen |
| ↳ [**Mrazík**](https://github.com/Project-NIC/NIC-Crazy_Ivan/blob/main/babuska/CONSTRUCTION.md#mrazík) | Father Frost: the closed aluminium cooling block around the computer and Mamka |
| [**Soňa**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/sona) | assistant for the deaf: listens all the time and tells by vibration what is happening around |
| [**Míša**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/misa) | assistant, the watchdog: a radar and ultrasound watch for obstacles and warn through the headphones and the headband |
| [**Taťána**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/tatana) | assistant: types what you dictate and reads text aloud, books included |
| [**Nikita**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/nikita) | assistant: the beat of the music as vibration |
| [**Pomoščnik**](https://github.com/Project-NIC/NIC-Crazy_Ivan/tree/main/pomoscnik) | assistant, the helper: looks at a part, reads its marking and finds it, with the glasses and the cameras |

</details>

<br>

---

# NIC-Sluchalo

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-Sluchalo.jpg" width="300" alt="Sluchalo"/></p>

**What is in a wall, seen by the shadow Wi-Fi casts through it** — a hand-held head with eleven
Wi-Fi receivers slides along one face of a wall while a small box behind the other face sends; a
cable, a pipe or a steel stud between them dims the field, and the head maps where. For brick
walls it also taps the wall and listens. The head is 167 mm across: a ring of nine antennas
30 × 29 mm on a circle of 65,8 mm radius around a crossed pair, 15 mm of foam with a hard sliding
sheet against the wall, about 0,36 kg before the housing, about three hours on two 18650 cells.
Every setting and all the raw data stay open.

→ **[Project-NIC/NIC-Sluchalo](https://github.com/Project-NIC/NIC-Sluchalo)** — 0.1, a concept: the physics computed, the head and its electronics on paper; nothing built or measured yet

<details>
<summary><b>The parts</b> — the lantern, the ring, the woodpecker and the rest</summary>

| part | what it is |
|---|---|
| **Fonar** | the lantern: the sender behind the wall, two ESP32-C5 boards with crossed antennas taking turns |
| **Kolchoz** | the collective farm: the ring of nine receivers that work as one, and the crossed pair in the middle — eleven ESP32-C5 on one clock |
| **Datel** | the woodpecker: a knock through a plastic rod in the middle, eight microphones around it |
| **Razvedčik** | the scout: two optical-flow sensors that track the head over the wall |
| **Gensek** | the general secretary: one STM32H7A3 over everything |
| **Pajok** | the ration: two 18650 cells |
| **Gradusnik** | the thermometer: a thermal sensor, postponed |

</details>

<br>

---

# ★ N.I.C. ★
## NIC — Native Intellect Community
### Viva la résistance! ✊

---

## What is NIC?

NIC is for people who:

- Use simple and proven principles
- Are willing to test and create
- Work with standardized hardware and environments
- Don't need bloated solutions to prove they know what they're doing

NIC is a revolutionary movement of all comrades who are fed up with today's overpriced and unnecessarily complex world.

*"Strength lies in simplicity."*

★ **Viva la résistance!** ★

---
[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://opensource.org/licenses/MIT)
