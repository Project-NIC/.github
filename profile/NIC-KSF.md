# NIC-KSF — Kolmogorov Shannon Feistel

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

Most crypto libraries arrive with key management, session state, counters and a
config file. NIC-KSF refuses all of it.

It does exactly one thing: encrypt or decrypt a block with a 128-bit key —
SPECK-128 in CTR mode, in place, no malloc, no dependencies beyond `stdint.h` and
`string.h`. Encryption and decryption are the same operation. Ensuring each key is
used once is handed, deliberately, to the layer above: a primitive that knows its
place and stays out of yours.

Two C variants for old and new avr-gcc, a Python reference that matches
byte-for-byte. On an ATmega328 it just runs. Sharp tools stay small.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
