# NIC-MLA — Matroshka Logging Archive

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

Conventional logging means a zoo of formats, a database that wants a server, and
a directory tree that corrupts on the first power cut. NIC-MLA takes a different
road: one file, two streams growing toward each other — data down from the top,
the log up from the bottom.

Every record is a 16-byte slot sealed by a CRC. Deleting it means zeroing it; the
checksum no longer matches and the reader walks past. No journal, no fsck, no
on-disk tree to break. The container is deliberately dumb — it only stores bytes.
Meaning rides in self-describing tables in the prefix, so a card pulled from an
ATmega328 exports to CSV/SQL on a PC with no prior knowledge.

The intelligence lives in the tables, not the code. That is why it runs from an
8-bit micro to a server — and why it won't surprise you for years.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
