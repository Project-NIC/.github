# NIC-Chinook — the air-quality reference

**Chinook** (a North-American warm wind, the "snow eater") is an air name for the air the
station breathes. **It is not a board.** Every air sensor worth fitting is a bought
**RS-485 Modbus unit**, so there is nothing here to manufacture — this is the shared
reference for which ones earn their place and why. They hang wherever the loadout has a
ModeBus: Palatine's leaf, the head's slow bus, or any node's. Anything not natively Modbus
goes behind a **Babel**.

**One channel is base — carbon monoxide by NDIR.** It is the only air channel that clears
both bars. It is **durable**: a sealed optical path, no electrochemical cell and no moving
parts, so it is genuinely fit-and-forget — unlike the VOC/NOx cells that die in a year, and
unlike the fan-and-fouling PM sensor. And it is **meaningful**: CO is a sharp marker of
incomplete combustion, so a rise means *something is burning* — not a background that is
always there. It also **co-times**: a lightning-ignited fire appears as a CO rise stamped to
the same clock as the strike that started it, on any station that also carries **Tesla**. CO
is slow, so it takes no dedicated per-frame byte — it rides the mux as **1 byte**.

**CO₂, PM2.5 and VOC stay opt-in.** Chemical cells live ~½–1 year, a recurring cost that
fights a potted node left in the field for years; and outdoors the readings are mostly not
events — dust is always there, CO₂ is well mixed. CO₂ corroborates a fire; PM2.5 is the fast
smoke signal but is a serviceable part, not fit-and-forget. Precise ambient chemistry is the
job of dedicated agencies on fixed stations: the capability is offered, it is simply not
populated on the base.

**No node type code, nothing to enrol.** The units are Modbus slaves, addressed by the node
that reads them and appearing in that node's mux — not on the NodeBus in their own right.
Nothing is added to the core protocol.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
