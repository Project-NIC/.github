# NIC-MSEED — senzorové logy → seismologie

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Senzorový log je jedna věc; seismologie mluví úplně jiným jazykem. NIC-MSEED je
ten most — přečte `.mla`, dekomprimuje NIC-DMD bloby, vytáhne syrové celočíselné
counts po kanálech a zapíše standardní **miniSEED** (Steim-1 / Steim-2), který
zapadne rovnou do ObsPy, SeisComp, SWARM a celého FDSN toolchainu.

Jádro nezávislé na kontejneru mění celá čísla na Steim rámce a zpět; tenká vrstva
`from_mla` na něj napojí NIC-MLA a NIC-DMD a mapuje tabulky STATION a SCHEMA na
SEED kódy network/station/channel. Čistý Python, žádné externí balíčky — ObsPy
jen jako volitelná kontrola se zlatým standardem.

Je to funkční konvertor, ne framework: nejkratší poctivá cesta od 8bitového
dataloggeru k seismickému archivu pro výzkum.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
