# NIC-KSF — Kolmogorov Shannon Feistel

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Většina kryptoknihoven přichází se správou klíčů, stavem relace, čítači a konfigurákem.
NIC-KSF tohle všechno odmítá.

Dělá přesně jednu věc: zašifruje nebo dešifruje blok 128bitovým klíčem — SPECK-128
v CTR módu, in-place, bez malloc, bez závislostí kromě `stdint.h` a `string.h`.
Šifrování a dešifrování jsou tatáž operace. Zajištění, že se každý klíč použije
jen jednou, vědomě předává vyšší vrstvě: primitivum, které zná své místo a do toho
tvého neleze.

Dvě C varianty pro starší i novější avr-gcc, Python reference shodná bajt po bajtu.
Na ATmega328 prostě běží. Ostré nástroje zůstávají malé.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
