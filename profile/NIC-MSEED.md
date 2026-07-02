# NIC-MSEED — sensor logs → seismology

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

A sensor log is one thing; seismology speaks another language entirely. NIC-MSEED
is the bridge — it reads an `.mla`, decompresses the NIC-DMD blobs, pulls the raw
integer counts out per channel, and writes standard **miniSEED** (Steim-1 /
Steim-2) that drops straight into ObsPy, SeisComp, SWARM and the FDSN toolchain.

A container-agnostic core turns integers into Steim frames and back; a thin
`from_mla` layer wires NIC-MLA and NIC-DMD to it, mapping the STATION and SCHEMA
tables onto SEED network/station/channel codes. Pure Python, no external packages
— ObsPy only as an optional gold-standard check.

It is a worked converter, not a framework: the shortest honest path from an 8-bit
datalogger to a research-grade seismic archive.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
