---
# ★ N.I.C. ★
---

## NIC — Arduino Family

[The Arduino family software](https://github.com/Project-NIC/NIC-Arduino) — the storage / transport / viewer stack for small devices, **closed at v1.2 — the final version**. The Heimdall station keeps its own archive (NIC-HMC, below).

### NIC-MLA
Matroshka Logging Archive — the base log format (single-file, crash-safe container).
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/mla)*

### NIC-DMD
Delta Markov Duda — optional compression.
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/dmd)*

### NIC-KSF
Kolmogorov Shannon Feistel — optional encryption.
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/ksf)*

### NIC-GLUE-IN
Write data into an MLA log.
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-in)*

### NIC-GLUE-OUT
Read / export an MLA log (CSV, SQLite, …).
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/glue-out)*

### NIC-MSEED
Seismo export — an MLA log → miniSEED (ObsPy / SeisComP / FDSN).
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/mseed)*

### NIC-IAGA
Geomag export — an MLA log → IAGA-2002 (INTERMAGNET format / SuperMAG).
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/iaga)*

### NIC-VDE
Volkov Data Ecosystem — browse & export MLA logs.
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/vde)*

---

## NIC — Heimdall

[The station — its hardware and its software](https://github.com/Project-NIC/NIC-Heimdall) — one self-contained, multi-phenomenon measuring station: one enclosure with the head, the clock and the cards, and whatever units a site needs. Swap the units and it is a different instrument on the same bus and the same code. Time comes from one place, and anything that leaves the enclosure crosses a Galvani board. Listed as the repository's folders are, each with its bus and type; the software last.

---

**The enclosure — the head, the clock, the power, the cards and the transport**

### NIC-Mayak
The station head — datalogger and uplink (Wi-Fi, a modem on the backup cell, BLE to the phone), writing each unit's archive to two microSD cards. Every card hangs off it.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak)* · NodBus 1

### NIC-Kronos
The station timekeeper — a TCXO disciplined to GNSS: the 2²³ Hz network timebase (2²² Hz on every wire), PPS and the named second to every card on one ribbon.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos)*

> #### NIC-Polaris
> Kronos's GNSS front, bought — a time-only receiver and an active antenna on a carrier; no processor. Fitted when the station has no Sputnik.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos/polaris)*

### NIC-Hermes
The BMS/MPPT converter — polls the bought pack and charger on whatever bus they speak and hands the head one register block. It measures nothing.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/hermes)*

### NIC-Bifrost
The NodBus master — one link up to the head, four point-to-point spurs down to the units (copper to 500 m, glass beyond), each spur its own timing domain, the absolute second put on every frame. There is no station without one.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost)* · NodBus 2 · the NodBus master

> #### NIC-Argus
> The NodBus mini master — the Bifrost card with its other role: four mini segments for the small clocked units, itself a unit on a Bifrost port.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost/argus)* · NodBus 3 · the mini master

### NIC-Galvani
The transport layer — **eleven boards**, named by what they do: a **communication board** carries the link (485 on copper, glass to 10 km, glass to 100 km), a **power board** feeds the run at the source end (48 V, or 300 V where 48 does not carry the load that far; 12 or 24 V to a bought device) or takes it off the cable as 12 V at the unit end. Isolation, surge protection and the feed: **anything that leaves the enclosure crosses one**.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/galvani)*

---

**The station on one PCB**

### NIC-Mimir
Mini-Heimdall — Mayak, Kronos, a Bifrost, an Argus, Palatine and Hermes on one PCB, with a full station's power: the box of a station that measures the weather, a few spurs and a few sondes.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mimir)*

### NIC-Proteus
The smallest whole station head — Mayak, Kronos, a Bifrost and Hermes on one small PCB with one copper run, an isolated input brick and an LTE-M modem, Polaris plugged in, in a 1-DIN slot: a vehicle's head, or a field station that hosts one unit.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/proteus)*

---

**The units**

### NIC-Quake
Seismograph — ground motion and local events plus tilt, a sealed tube in rock or soil (ADXL355 + ICM-42688-P, SCL3300, optionally an RM3100).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quake)* · NodBus 5

### NIC-Tesla
Lightning — VLF sferics and the fast B-field, every impulse timed on the network clock (three ferrite rods + ADS127L14 at 2²⁰ SPS, its own DSP).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla)* · NodBus 7

> #### NIC-Pip
> The longwave carriers — the D-region (SID) channel, and longwave time for a station without GNSS. Tesla's board, its own firmware. **Held back by transmitter coverage** — finished as a description.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/pip)* · NodBus 12
>
> #### NIC-Steinmetz
> Line faults on power lines — arc, corona, partial discharge — from a vehicle at 80–100 km/h or a site. Tesla's board, its own firmware.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla/steinmetz)* · NodBus 13

### NIC-Marconi
The HF ionosphere — the F-region: HF transmitter levels 0.5–16 MHz and a passive ionogram (foF2, MUF), one air-core loop into direct sampling.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/marconi)* · NodBus 4

### NIC-Sputnik
GNSS / ionosphere — Total Electron Content and precipitable water vapour (Unicore UM980); the same receiver is the station's time source when fitted.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sputnik)* · NodBus 8

### NIC-Palatine
The meteo base and the ModBus master — four isolated arms for the bought weather set (T/RH, pressure, wind, solar, UV, snow depth) and the house modules below, no sensor of its own; itself a unit on NodBus.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine)* · NodBus 6 · the ModBus master

> #### NIC-Chinook
> Air quality — not a board: the bought RS-485 Modbus air units on Palatine's arms, fitted per site.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine/chinook)*

### NIC-Quark
The radiation part — what is measured and the two builds that measure it: **Quark-Tubes**, high voltage, and **Quark-Scintillation**, low voltage.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark)*

> #### NIC-Quark-Tubes
> Radiation by tubes, high voltage — every tube counted on one board, counts only: Photon's GM tubes behind graded lead, and Helion or Gadolin for the neutrons.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes)* · mini 2
>
> > ##### NIC-Helion
> > Neutron — the He³ / BF₃ tube on Quark-Tubes, and the kV source; no processor of its own.
> > *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes/helion)*
> >
> > ##### NIC-Gadolin
> > Neutron — Gd capture read by a ring of GM tubes on Quark-Tubes (with **Rhodion**, the Rh-activation variant); no processor of its own.
> > *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/tubes/gadolin)*
>
> #### NIC-Quark-Scintillation
> Radiation by scintillation, low voltage — scintillators read by electronics on two H7A3 boards, counts and energy: Photon, Positron and Neutron.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation)*
>
> > ##### NIC-Photon
> > γ / X-ray, by scintillation — a CsI(Tl) crystal read by a SiPM and a PIN diode, counts and energy (Quark-Scintillation). Its GM-tube build is counted on Quark-Tubes.
> > *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/photon)* · NodBus 9
> >
> > ##### NIC-Positron
> > Beta, both signs — a plastic scintillator block + SiPM, counts and energy (Quark-Scintillation).
> > *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/positron)* · NodBus 11
> >
> > ##### NIC-Neutron
> > Neutron, thermal and epithermal — ⁶LiF/ZnS(Ag) screens on a photomultiplier; a channel of Positron's board, riding its record (Quark-Scintillation).
> > *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quark/scintillation/neutron)* · type 10 reserved

### NIC-Gauss
Magnetometer — the slow geomagnetic field (Tesla is its fast-field sibling), an RM3100 in a sealed tube, oil-filled in the sea build; fitted when no Quake carries the chip.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss)* · mini 1

### NIC-Pascal
The pressure sonde — a tsunami gauge that reads the water column from the sea floor, in Gauss's tube.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pascal)* · mini 3

### NIC-Pluvius
Precipitation — a weighing rain gauge: a 200 cm² catch on a load cell, answered in grams.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pluvius)* · ModBus 5

### NIC-Ceres
Soil moisture — water content and soil temperature read through borosilicate glass, the units packed at fixed depths in a *patrona*.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres)* · ModBus 6

> #### NIC-Sakura
> Leaf wetness — Ceres's board in the same glass bowl, hung in the canopy at 45°.
> *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres/sakura)* · ModBus 7

### NIC-Babel
The universal Modbus bridge — any sensor (I²C, SPI, UART, 1-Wire) → Modbus RTU at the source.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel)* · ModBus 4 bare

---

**The station as a whole**

### NIC-Atlantis
The water build — the Galvani boards in their pressure build and a sea cable: Pascal and Gauss a few hundred metres off shore. The 50–100 km run to a magnetometer on 300 V is **shelved**.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/atlantis)*

### NIC-Daedalus
Station construction — the mast, the earthing, the enclosure, the vault and the cable routing: how a station is physically built (a build guide).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus)*

### NIC-Gaia
The siting atlas — where the stations go across the planet: coverage maps and the reasoning behind them.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gaia)*

---

**The software — one package, from the card to the server**

### NIC-HMC
Heimdall Matryoshka Container — the station's archive: a series of files per unit, its recording and send rules, every segment on its own, every card carrying its own description. What the head stores, the uplink carries and the server keeps; the station does not use NIC-MLA.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md)*

### NIC-HCC
Heimdall Compression Codec — lossless, column by column: a prediction, the miss Rice-coded, no table stored or trained. Python reference with its tests.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HCC.md)*

### NIC-Exporters
Readers of the archive for what the world takes — miniSEED + StationXML, IAGA-2002, RINEX, BUFR, CWOP, IOC sea level, air quality, CSV and SQL (SQLite / PostgreSQL), one template each.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/EXPORTERS.md)*

### NIC-Server
The server — the files as the archive of record, a catalogue over them in SQLite or PostgreSQL, and the viewer.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/core/archive/HMC.md#on-the-server)*

### NIC-Handset
The commissioning app — the phone at the open enclosure: who enrolled, what is failing by name, GO / NO-GO over button-gated BLE.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak/handset)*

---

## NIC — Bumble Bee *(Russian Power)*

### NIC-BumbleBee
The power side — **NIC-FPLG**, a crankshaft-free two-stroke linear engine: two pistons on one rod with a tubular linear generator at the rod's centre, running permanently at mechanical resonance rather than at a controlled RPM. ~3 kW mechanical, 1–1.5 kW electrical; **twinned in anti-phase** it cancels ~88 % of its own vibration.
*[repo](https://github.com/Project-NIC/NIC-BumbleBee)*

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

## Что такое NIC?

NIC — для людей, которые:

- Используют простые и проверенные принципы
- Готовы тестировать и создавать
- Работают со стандартизированным оборудованием и средой
- Не нуждаются в раздутых решениях чтобы доказать, что что-то умеют

NIC — это революционное движение всех товарищей, которых не устраивает сегодняшний переоценённый и излишне усложнённый мир.

*«Сила в простоте.»*

★ **Viva la résistance!** ★

---
[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://opensource.org/licenses/MIT)
