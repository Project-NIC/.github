---
# ★ N.I.C. ★
---

## NIC — Arduino Family

[The Arduino family software](https://github.com/Project-NIC/NIC-Arduino) — the storage / transport / viewer stack.

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

[The hardware fronts + the base station](https://github.com/Project-NIC/NIC-Heimdall) — one node core, one bus, one clock. Mix and match freely: a station is whatever fronts you bolt on, and light sensors can hang straight off the master's Modbus.

### NIC-Mayak
The station head — datalogger and uplink. Every node hangs off it.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/mayak)*

### NIC-Kronos
The station timekeeper — a dedicated clock board: GNSS-disciplined 2²³ Hz network clock (2²² Hz on the wire), PPS and coarse UTC for the whole station.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/kronos)*

### NIC-Pip
Longwave time — the 34–120 kHz time-code stations and eLoran → a second PPS and a date for Kronos where the sky is hidden. **Worked theory, shelved** — the band covers the already-instrumented world and misses everywhere this project exists to fill.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pip)*

### NIC-Bifrost
The bridge card — trunk ↔ point-to-point spurs to remote units, copper or light, one up and four down, each spur its own ranged timing domain; every remote unit hangs behind one. **Argus is the same board:**

- **NIC-Argus** — the carrier node: the identical card with different firmware in a different socket, carrying four NodBus **mini** segments so a small clocked unit gets network time without spending a spur on it — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/argus)*

*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/bifrost)*

### NIC-Palatine
The meteo base — temp / RH, pressure, wind, solar, UV, soil. Its field MODs sit under it:

- **NIC-Sakura** — leaf wetness: the dew / plant-disease channel, a Modbus MOD on Palatine's leaf bus — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sakura)*
- **NIC-Ceres** — soil moisture: the soil column read at fixed depths (the bench-packed *patrona*), a Modbus MOD — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/ceres)*

*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/palatine)*

### NIC-Chinook
Air quality — not a board: the bought RS-485 Modbus units, with the CO fire channel as the base.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/chinook)*

### NIC-Quake
Seismograph — local ground motion + edge event detection (ADXL355 + ICM-42688, SCL-3300, RM3100).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/quake)*

---

### NIC-Quark
The radiation unit — the physics and the counting the heads below build on, and its three boards: the HV-tube counting board and the two scintillation boards. The detector projects sit under it:

- **NIC-Helion** — neutron: He³ / BF₃ — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/helion)*
- **NIC-Gadolin** — neutron: Gd capture (with **Rhodion**, the Rh-activation variant) — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gadolin)*
- **NIC-Photon** — γ / X-ray: GM tubes behind graded lead, and the SiPM + PIN scintillation channel — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/photon)*
- **NIC-Positron** — beta: the plastic-tile scintillator and the unshielded tube over the deposition plate — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/positron)*

---

### NIC-Sputnik
GNSS / ionosphere — Total Electron Content, space weather (Unicore UM980C).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/sputnik)*

### NIC-Tesla
Lightning — VLF sferics / fast B-field (four ferrite rods + THS4551 + ADS127L14).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/tesla)*

### NIC-Gauss
Magnetometer — the slow geomagnetic field (Tesla is its fast-field sibling), an RM3100 in an oil-filled tube.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gauss)*

### NIC-Pascal
The pressure sonde — a tsunami gauge that reads the water column from underneath, in the same oil-filled tube as Gauss.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pascal)*

### NIC-Pluvius
Precipitation — a weighing rain gauge.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/pluvius)*

### NIC-Babel
The universal Modbus bridge — any sensor → Modbus at the source.
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/babel)*

### NIC-Galvani
The transport layer — **ten boards**, split by job: a **power board** makes the feed or takes it off the cable (48 V, or 300 V where 48 does not carry the load that far), a **communication board** carries the link (485 on copper, glass to 10 km, glass beyond). Isolation, the sacrificial surge front and the feed telemetry; **anything that leaves the enclosure crosses one**, and a normal station builds three. The sea variant sits under it:

- **NIC-Atlantis** — the sea link: the optical board re-rated for a submarine run — a 300 V feed down 100 km of armoured hybrid, ship-laid, to the oil-filled sonde at the far end. **Worked theory, shelved** — *[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/atlantis)*

*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/galvani)*

### NIC-Daedalus
Station construction — the mast, the sensor seat, the vault, grounding and finish: how a station is physically built and seated (a build guide, not a board).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/daedalus)*

### NIC-Gaia
The siting atlas — where the stations go across the planet: coverage maps and the reasoning behind them (maps, not a board).
*[repo](https://github.com/Project-NIC/NIC-Heimdall/tree/main/gaia)*

### NIC-Handset
The commissioning app — the phone at the open enclosure: who enrolled, what is failing by name, GO / NO-GO over button-gated BLE (software, not a board).
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
