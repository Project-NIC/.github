# NIC-Palatine — precision weighing weather station

Named after the *Societas Meteorologica Palatine* (Mannheim, 1780), the first
international standardized weather-station network. Not one box: a small project of its
own — a main unit plus a set of nodes sharing the NIC RS-485 bus and one hardware clock.
The headline instrument is **Pluvius**, a **weighing rain gauge** — a load cell that
weighs accumulated precipitation instead of tipping a bucket — joined by Modbus meteo
sensors: temperature/humidity, wind, pressure, solar, UV and soil. (Lightning is now its
own front, **Tesla**.)

It is the universal NIC node core plus the meteo front (the `nw-*` libraries) and the
glue that speaks RS-485 / Modbus. In the platform it doubles as the **hub** (node type
`basic`) the other fronts hang off.

Simple parts, honest measurements, one shared bus — a station you can build and run at
home.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
