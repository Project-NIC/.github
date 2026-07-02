# NIC-Quake — Open hardware distributed MEMS seismograph

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

A research seismograph asks you to buy geophones that cost a fortune and level
them by hand, or to fight capacitive sensors that drift with every change in
temperature and humidity. NIC-Quake takes a different road.

The sensor is a MEMS accelerometer — three axes on one hermetically sealed
silicon die, factory-calibrated, digital out. Its proof mass resonates up in the
kHz while seismic energy stays below 20 Hz, so the two never meet. A node is
potted in polyurethane and bolted into rock or a foundation, sealed for life,
with no knob to turn: the firmware takes the sensor's resting state as zero and
reads Earth's own gravity vector to fix absolute orientation. Mount it crooked —
it already knows which way is down.

Nodes daisy-chain over ordinary Cat-6 on an RS-485 line, up to eight per segment.
Instead of trusting NTP or software timestamps, a master distributes a hardware
clock on its own wire pair, phase-locking the whole chain to nanoseconds. The
data drops into the rest of the stack: NIC-DMD compresses it, NIC-MLA stores it
crash-safe in one file, NIC-KSF encrypts the link, NIC-MSEED hands it to the
seismology world.

The architecture holds and the data path is built. The PCB, the firmware and the
field tests are still ahead — this repo is a brief, not a result. We are looking
for people who can say "I don't know, but I'd try this" — and then try it.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
