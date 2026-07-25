# NIC-Kronos — časoměřič stanice

**Kronos, Titán času** — s Chronem si ho lidstvo plete od antiky, a ta záměna sedí:
celý smysl stanice pro čas se rodí na téhle jedné malé desce.

Vyhrazený STM32H523 s jediným úkolem: GNSS-disciplinovaný TCXO/GPSDO syntetizuje
**síťové hodiny 2²³ Hz** — a podává celé stanici její tep: hodiny se přes mosty
Bifrost rozvádějí do každého drátu i vlákna, hrana PPS značí sekundu a hrubá unixová
sekunda chodí jednou za minutu (a slouží zároveň jako Kronosův vlastní heartbeat —
vynechaná minuta spouští poplach). Majáku prostě **emuluje GPS**, takže časová cesta
hlavy se nikdy nemění.

Každá deska v síti **počítá TYHLE rozvedené hodiny, ne vlastní krystal** — jeden
přesný oscilátor na stanici, všechno ostatní je drát a aritmetika. Celý projekt
doručuje **jednu mikrosekundu**; 119ns tik pod ní je instalatérství.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
