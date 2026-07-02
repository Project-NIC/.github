# NIC-Tesla — lightning / TGF sferic receiver

Named for **Nikola Tesla** (high-voltage / the Tesla coil). A do-it-yourself **sferic
receiver** — **four ferrite rods** on a truncated-pyramid frame + a **THS4551**
differential front-end + an **ADS127L14** ADC — that detects lightning **at the edge**
(edge-AI classification) and ships a tiny **fixed event record**, not raw waveforms.

Tesla is an **analog front with no processor of its own**: it **SPI-couples to the
Chinook node** in the same enclosure, and **Chinook's STM32H523 runs the lightning DSP**.
By the "a board gets a name" rule it is still its own named front.

Because every node shares the 120 ns network clock, each strike is time-stamped for
network multilateration (TOA across widely-separated stations), and a thunderstorm
gamma-ray flash (**TGF**) can be correlated with the radiation boards (**Quark** /
**Photon**).

Design on paper: detection is the solid part; localisation wants the wide network.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
