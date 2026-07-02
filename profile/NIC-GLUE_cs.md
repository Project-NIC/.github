# NIC-GLUE (IN / OUT) — švy

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Knihovny NIC o sobě záměrně nevědí: MLA ukládá neprůhledné bajty, DMD balí pakety
pevné šířky, KSF transformuje bajty — žádná netuší, že ty ostatní existují.
*Lepidlo* je jakýkoliv kód, který ty švy srovná, a srovnat je správně je celá ta
práce.

**GLUE-IN** zapojuje zápisovou stranu: řádek senzoru, volitelně DMD komprese, do
MLA kontejneru — nastaví bit „compressed" a vzdálenost ke keyframu tak, aby každý
rotovaný soubor šel dekódovat sám. **GLUE-OUT** je tentýž nápad otočený: projde
hotový kontejner zpátky ven do CSV nebo SQLite a po cestě dekomprimuje.

Ani jedno není framework, který musíš převzít. Obojí je funkční příklad plus malý
katalog té hrstky švů, kde se knihovny musí shodnout — sepsaný jednou, ať to nikdo
nemusí objevovat znovu.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
