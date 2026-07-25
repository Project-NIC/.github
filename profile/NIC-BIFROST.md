# NIC-Bifrost — the bridge of light

**Bifrost — the Norse bridge between worlds, guarded by Heimdall.** The name is
exact: the watchman (Heimdall, the network) opens his light-bridges (Bifrost) from
the station to the worlds around it.

A house STM32H523 bridge card: **one trunk + four spur ports**, each spur a
point-to-point link — optical or copper — to one remote unit. Toward each spur the
card is that spur's **master and time authority**: it transmits the clock, runs
enrollment, **measures the line's propagation delay** (the ranging gate) and maps
spur time to network time. Toward the head it presents its units and hands up
finished, timestamped frames. Its floor runs autonomously — the master keeps one
verb: "bring your floor up."

Every remote unit hangs behind a Bifrost, each in its own timing domain — so a node
behind 20 km of fibre never learns it is remote, and lightning that eats one bridge
eats one card, not the station.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
