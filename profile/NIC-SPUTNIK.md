# NIC-Sputnik — GNSS / Ionosphere front

The ionosphere is a mirror you can read with a good clock and a good antenna. NIC-Sputnik
turns a single multi-constellation, multi-frequency **Unicore UM980** receiver into a
node that measures **Total Electron Content (TEC)** — the column of free electrons
overhead.

It is the universal NIC node core plus one sensor: the glue reads the UM980 over UART
and curates its output onto the bus — raw backbone, corrections, augmentation — keeping
only what carries the science, not the firehose.

It grew out of the seismograph work: a big quake pushes acoustic-gravity waves up into
the ionosphere minutes later, so a seismo and a Sputnik node at one site catch both ends
of that chain — civilian space weather from commodity parts.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
