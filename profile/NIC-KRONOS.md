# NIC-Kronos — the station timekeeper

**Kronos, the Titan of time** — conflated with Chronos since antiquity, and the
conflation fits: the station's whole sense of time is born on this one small board.

A dedicated STM32H523 that does exactly one job: a GNSS-disciplined TCXO/GPSDO
synthesises the **2²³ Hz network clock** — and hands the whole station its heartbeat:
the clock fans out through the Bifrost bridges to every wire and fibre, a PPS edge
marks the second, and a coarse Unix second arrives once a minute (which doubles as
Kronos's own liveness heartbeat — a missed minute raises the alarm). To the Mayak it
simply **emulates a GPS**, so the head's time path never changes.

Every board in the network **counts THIS distributed clock, not its own crystal** —
one precise oscillator per station, everything else is wire and arithmetic. The whole
project delivers **one microsecond**; the 119 ns tick underneath is plumbing.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
