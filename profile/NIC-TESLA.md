# NIC-Tesla — lightning / TGF sferic receiver

Named for **Nikola Tesla** (high-voltage / the Tesla coil). A do-it-yourself **sferic
receiver** — three orthogonal ferrite loops + an OPA1637 front-end + an ADS127L14 ADC +
an STM32H523 — that detects lightning **at the edge** (edge-AI classification) and ships
a tiny **fixed event record**, not raw waveforms. Its **own board** → its own front
(rule: a board gets a name).

Because every node shares the 120 ns network clock, each strike is time-stamped for
network multilateration (TOA across widely-separated stations), and a thunderstorm
gamma-ray flash (**TGF**) can be correlated with the radiation boards (**Quark** /
**Photon**).

Design on paper: detection is the solid part; localisation wants the wide network.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
