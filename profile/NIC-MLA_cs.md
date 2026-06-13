# NIC-MLA — Matroshka Logging Archive

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Běžné logování znamená zoo formátů, databázi, která chce server, a adresářový
strom, co se rozsype při prvním výpadku proudu. NIC-MLA jde jinou cestou: jeden
soubor, dva proudy rostoucí proti sobě — data shora dolů, log zdola nahoru.

Každý záznam je 16bajtový slot zapečetěný CRC. Smazat ho znamená vynulovat ho;
kontrolní součet pak nesedí a čtečka ho přeskočí. Žádný žurnál, žádný fsck, žádný
strom na disku, který by se rozbil. Kontejner je záměrně hloupý — jen ukládá
bajty. Význam jede v samopopisných tabulkách v prefixu, takže kartu vytaženou
z ATmega328 vyexportuješ na PC do CSV/SQL bez jakékoliv předchozí znalosti.

Inteligence žije v tabulkách, ne v kódu. Proto běží od 8bitového mikrokontroléru
po server — a proto tě roky nepřekvapí.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
