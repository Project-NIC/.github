# NIC-Mayak — the station head (datalogger + uplink + the roster)

Маяк — a **lighthouse**, and the name of the old radio beacon that broadcast the
time signal. The Mayak is the **head** of a NIC station: it captures, stores and
uplinks — a microSD NIC-MLA log on one side, a lean 16-byte LoRa / Wi-Fi telemetry
frame on the other — and holds the **roster**: one small table that IS the station's
composition (adding a unit never means touching node firmware).

Since the Bifrost era the head touches no bus directly: each of its two trunk UARTs
is a point-to-point **MasterNOD link** to a Bifrost bridge, and the NodeBus proper
starts behind them. The clock is not his either — **Kronos** makes it and hands the
Mayak a PPS, the tick stream and a coarse second, like a private GPS.

It is **front-agnostic** (an ESP32-S31 head): it carries no sensor knowledge at all —
seismo, weather, iono or mag units hang off the same head with zero changes. Build one
good head and one good node, and you have a station.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
