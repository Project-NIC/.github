---
# ★ N.I.C. ★
---

## NIC - Arduino Family

### NIC-Arduino — [the Arduino family software](https://github.com/Project-NIC/NIC-Arduino)

- **`mla/`** — NIC-MatroshkaLoggingArchive — the base log format — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MLA_ru.md)*
- **`dmd/`** — NIC-DeltaMarkovDuda — optional compression — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-DMD_ru.md)*
- **`ksf/`** — NIC-KolmogorovShannonFeistel — optional encryption — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-KSF_ru.md)*
- **`glue-in/` · `glue-out/`** — NIC-Glue IN/OUT — write / read+export an MLA log — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-GLUE_ru.md)*
- **`mseed/`** — NIC-MSEED — seismo miniSEED export — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-MSEED_ru.md)*
- **`vde/`** — NIC-VDE — the Volkov Data viewer — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-VDE_ru.md)*

---

## NIC - Station

### NIC-Station — [Multi sensors system station](https://github.com/Project-NIC/NIC-Station)

Grouped by **node** — a board on the NodeBus that announces one of the four types
(`seismo` / `basic` / `iono` / `starDust`). The modules and detectors that ride a node
are listed **under** it.

- **`quake/`** — **NIC-Quake** *(node — `seismo`)* — the seismograph (MEMS ADXL355 / ICM-42688 / SCL-3300 + edge event detection) — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUAKE_ru.md)*
- **`palatina/`** — **NIC-Palatina** *(node — `basic`, also the hub)* — precision weighing weather station + Pluvius rain gauge — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA_ru.md)*
  - **Pluvius · Sakura · Ceres** — Modbus-slave sensor modules on Palatina's leaf bus (weighing rain gauge / leaf-wetness / soil-moisture, STM32U031) — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-PALATINA_ru.md)*
  - **`quark/` · `photon/` · `helion/` · `gadolin/`** — **NIC-Quark** — radiation detectors (neutron reference + Photon γ/X-ray, Helion He³, Gadolin Gd boards); counts ride Palatina's BASIC payload K1–K4 — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-QUARK_ru.md)*
- **`sputnik/`** — **NIC-Sputnik** *(node — `iono`)* — Ionosphere / GNSS — TEC from a Unicore UM980 receiver — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-SPUTNIK_ru.md)*
- **`chinook/`** — **NIC-Chinook** *(node — `starDust`)* — air quality — CO₂ / PM / VOC / UV (parked) — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-CHINOOK_ru.md)*
  - **`tesla/`** — **NIC-Tesla** — lightning / TGF sferic receiver (own board, carried by Chinook) — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/NIC-TESLA_ru.md)*

---

## NIC - Bumble Bee (Russian Power)

### NIC-BumbleBee — the power side — *[Čeština](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee_cs.md) · [English](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee.md) · [Русский](https://github.com/Project-NIC/.github/blob/main/profile/BumbleBee_ru.md)*

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
