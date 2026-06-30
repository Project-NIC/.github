# NIC-Majak — the data station (clock master + datalogger + uplink)

Маяк — a **lighthouse**, and the name of the old radio beacon that broadcast the
**time signal**. That is exactly what the master is: the **head-end** of one RS-485
segment — the single heartbeat the whole network steers by.

One oscillator — a dedicated **8.388608 MHz TCXO**, wired straight onto the clock pair —
is the network's only clock, so every node phase-locks to it to sub-microsecond. Majak
hands each node a TDMA slot, says *go*, then only **listens, stores and uplinks**: a
microSD NIC-MLA log on one side, a lean 16-byte LoRa / Wi-Fi telemetry frame on the other.

It is **front-agnostic** (an ESP32 head): it carries no sensor knowledge at all — seismo,
weather, iono or starDust nodes hang off the same master with zero changes. Build one good
Majak and one good node, and you have a station.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
