---
# ★ N.I.C. ★
---

## NIC — Arduino Family

[The Arduino family software](https://github.com/Project-NIC/NIC-Arduino) — the storage / transport / viewer stack.

### NIC-MLA
Matroshka Logging Archive — the base log format (single-file, crash-safe container).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA_ru.md)*

### NIC-DMD
Delta Markov Duda — optional compression.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD_ru.md)*

### NIC-KSF
Kolmogorov Shannon Feistel — optional encryption.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF_ru.md)*

### NIC-GLUE-IN
Write data into an MLA log.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_ru.md)*

### NIC-GLUE-OUT
Read / export an MLA log (CSV, SQLite, …).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_ru.md)*

### NIC-MSEED
Seismo export — an MLA log → miniSEED (ObsPy / SeisComP / FDSN).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED_ru.md)*

### NIC-IAGA
Geomag export — an MLA log → IAGA-2002 (INTERMAGNET format / SuperMAG).
*[repo](https://github.com/Project-NIC/NIC-Arduino/tree/main/iaga)*

### NIC-VDE
Volkov Data Ecosystem — browse & export MLA logs.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE_ru.md)*

---

## NIC — Heimdall

[The hardware fronts + the base station](https://github.com/Project-NIC/NIC-Heimdall) — one node core, one bus, one clock. Mix and match freely: a station is whatever fronts you bolt on, and light sensors can hang straight off the master's Modbus.

### NIC-Mayak
The station head — datalogger and uplink. Every node hangs off it.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MAYAK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MAYAK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MAYAK_ru.md)*

### NIC-Kronos
The station timekeeper — a dedicated clock board: GNSS-disciplined 2²³ Hz network clock (2²² Hz on the wire), PPS and coarse UTC for the whole station.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KRONOS_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KRONOS.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KRONOS_ru.md)*

### NIC-Pip
Longwave time — the 40–120 kHz time-code stations and eLoran → a second PPS and a date for Kronos where the sky is hidden. **Worked theory, shelved** — the band covers the already-instrumented world and misses everywhere this project exists to fill.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pip)*

### NIC-Bifrost
The bridge card — trunk ↔ point-to-point spurs to remote units, copper or light, each spur its own ranged timing domain; every remote unit hangs behind one.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-BIFROST_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-BIFROST.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-BIFROST_ru.md)*

### NIC-Palatine
The meteo base — temp / RH, pressure, wind, solar, UV, soil. Its field MODs sit under it:

- **NIC-Sakura** — leaf wetness: the dew / plant-disease channel, a Modbus MOD on Palatine's leaf bus — *[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/palatine/MODBUS_UNITS.md)*
- **NIC-Ceres** — soil moisture: the soil column read at fixed depths (the bench-packed *patrona*), a Modbus MOD — *[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/palatine/MODBUS_UNITS.md)*

*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE_ru.md)*

### NIC-Chinook
Air quality — not a board: the bought RS-485 Modbus units, with the CO fire channel as the base.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK_ru.md)*

### NIC-Quake
Seismograph — local ground motion + edge event detection (ADXL355 + ICM-42688, SCL-3300, RM3100).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE_ru.md)*

---

### NIC-Quark
The shared reference for the radiation detectors — the physics + counting the heads below build on (not a board). The three detector boards sit under it:

- **NIC-Helion** — neutron: He³ / BF₃ — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_ru.md)*
- **NIC-Gadolin** — neutron: Gd capture (with **Rhodion**, the Rh-activation variant) — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_ru.md)*
- **NIC-Photon** — γ / X-ray: GM tubes behind graded lead — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_ru.md)*

---

### NIC-Sputnik
GNSS / ionosphere — Total Electron Content, space weather (Unicore UM980C).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK_ru.md)*

### NIC-Tesla
Lightning — VLF sferics / fast B-field (four ferrite rods + THS4551 + ADS127L14).
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA_ru.md)*

### NIC-Gauss
Magnetometer — the slow geomagnetic field (Tesla is its fast-field sibling).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss)*

### NIC-Pluvius
Precipitation — a weighing rain gauge.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINE_ru.md)*

### NIC-Babel
The universal Modbus bridge — any sensor → Modbus at the source.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel)*

### NIC-Galvani
The universal port-module family — four boards (I/O × output/input): isolation + the ~48 V remote-spur feed (the one place the network makes a voltage), the sacrificial surge front, and the feed telemetry — the network's whole transport layer as plug-in modules; anything that leaves the enclosure crosses one. The sea variant sits under it:

- **NIC-Atlantis** — the sea link: the optical block re-rated for a submarine run — a 200–300 V feed down the hybrid cable, 120 km lasers, the oil-filled sonde at the far end. **Worked theory, shelved** — *[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/galvani/ATLANTIS.md)*

*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GALVANI_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GALVANI.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GALVANI_ru.md)*

### NIC-Daedalus
Station construction — the mast, the sensor seat, the vault, grounding and finish: how a station is physically built and seated (a build guide, not a board).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus)*

### NIC-Gaia
The siting atlas — where the stations go across the planet: coverage maps and the reasoning behind them (maps, not a board).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/blob/main/GAIA.md)*

### NIC-Handset
The commissioning app — the phone at the open enclosure: who enrolled, what is failing by name, GO / NO-GO over button-gated BLE (software, not a board).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak/handset)*

---

## NIC — Bumble Bee *(Russian Power)*

### NIC-BumbleBee
The power side.
*[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee_ru.md)*

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
