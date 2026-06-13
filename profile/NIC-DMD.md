# NIC-DMD — Delta Markov Duda

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

Compressing tiny sensor packets the usual way costs you hundreds of bytes of RAM,
or a Huffman table shipped alongside every message. NIC-DMD takes a different road.

It carries one fixed Huffman table in 64 bytes of ROM and zero extra RAM. Each
packet is compressed on its own — the encoder tries five simple methods and keeps
the smallest, adding at most one header byte in the worst case. Random, encrypted
or already-compressed data? It ships it raw and shrugs: no loss, no real expansion.

Slowly-changing telemetry over LoRa is where it shines — weather, energy meters,
GPS, industrial counters. Fully working on an ATmega328, byte-identical in C and
Python. Small data deserves small code.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
