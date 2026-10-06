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
**Version 0.2 — a design-stage concept:** every board described to the part, nothing built yet.
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

# NIC-CrazyIvan

<p align="center"><img src="https://github.com/Project-NIC/.github/raw/main/profile/NIC-CrazyIvan.jpg" width="300" alt="Crazy Ivan"/></p>

**A neural suit** — 126 to 254 electrodes and 16 to 64 motion sensors on a suit put together from
pieces: a sleeve, a trouser leg, the torso, a headband. The muscles' own signals and the body's
motion go to a Raspberry Pi 5 with the Hailo-10H AI accelerator, and the whole body becomes the
controller for a computer or a game. **Coming soon™.** Well — not *that* soon.

→ **[Project-NIC/NIC-CrazyIvan](https://github.com/Project-NIC/NIC-CrazyIvan)** — private until it is finished

<details>
<summary><b>The parts</b> — the suit, the head, Mamka, the assistants</summary>

| part | what it is |
|---|---|
| [**Venom**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/venom) | the suit itself: the pieces with their sensing modules |
| [**Nataša**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/natasa) | the unit in the headband: headphones, two microphones, vibration and buttons |
| [**Power**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/power) | the power board, the battery and its BMS, in a hard-shell backpack with Mamka |
| [**Mamka**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/mamka) | the base board, with the Raspberry Pi 5 and the Hailo-10H: the clock for the whole suit, the sound bridge and the line drivers |
| [**Soňa**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/sona) | assistant for the deaf: listens all the time and tells by vibration what is happening around |
| [**Míša**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/misa) | assistant, the watchdog: ultrasound watches for obstacles and beeps a warning into the headphones |
| [**Taťána**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/tatana) | assistant: types what you dictate and reads text aloud, books included |
| [**Nikita**](https://github.com/Project-NIC/NIC-CrazyIvan/tree/main/nikita) | assistant: the beat of the music as vibration |

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
