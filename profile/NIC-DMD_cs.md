# NIC-DMD — Delta Markov Duda

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Komprimovat drobné senzorové pakety obvyklým způsobem tě stojí stovky bajtů RAM
nebo Huffmanovu tabulku posílanou s každou zprávou. NIC-DMD jde jinou cestou.

Nese jednu pevnou Huffmanovu tabulku v 64 bajtech ROM a nula RAM navíc. Každý
paket se komprimuje samostatně — kodér vyzkouší pět jednoduchých metod a nechá si
tu nejmenší, v nejhorším případě přidá jediný bajt hlavičky. Náhodná, šifrovaná
nebo už komprimovaná data? Pošle je syrová a mávne rukou: žádná ztráta, žádné
reálné nafouknutí.

Pomalu se měnící telemetrie přes LoRa je jeho parketa — meteo, elektroměry, GPS,
průmyslové čítače. Plně funkční na ATmega328, byte-identický v C i Pythonu. Malá
data si zaslouží malý kód.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
