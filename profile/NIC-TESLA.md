# NIC-Tesla — lightning / TGF sferic receiver

Named for **Nikola Tesla** (high-voltage / the Tesla coil). A do-it-yourself **sferic
receiver** — **four ferrite rods** on a truncated-pyramid frame + a **THS4551**
differential front-end + an **ADS127L14** ADC — that detects lightning **at the edge**
(edge-AI classification) and ships a tiny **fixed event record**, not raw waveforms.

Tesla is **one NodeBus unit, type code 7, on a single board**: the analog front and the
**STM32H523 that runs its DSP** share one PCB in one IP68 box on the antenna frame. Its
only connector is the **Galvani socket**.

Because every node shares one network clock — **one microsecond delivered** — each strike
is time-stamped for network multilateration (TOA across widely-separated stations), and a
thunderstorm
gamma-ray flash (**TGF**) can be correlated with the radiation boards (**Quark** /
**Photon**).

Design on paper: detection is the solid part; localisation wants the wide network.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
