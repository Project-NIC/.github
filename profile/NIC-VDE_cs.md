# NIC-VDE — Volkov Data Ecosystem

*Teaser · pro Show HN, r/embedded, Hackaday a podobné komunity.*

---

Logovací formát je užitečný jen tak, jak se do něj umíš podívat. NIC-VDE je
dvoupanelový souborový manažer v duchu Volkov Commanderu — ale nekončí u
souborového systému. Stiskneš Enter na `.mla` a vstoupíš dovnitř kontejneru, každý
zalogovaný záznam zobrazený jako soubor, který procházíš.

Dekóduje každý zabalený payload přes samopopisné schéma, přeloží 1bajtový index
stanice na reálné číslo stanice a celé to vyexportuje do CSV nebo SQL — to vše z
jádra bez GUI, které jde použít i samostatně. Dekomprese je automatická; mimo
rozsah zůstává jen šifrování.

Je postavený jako formát, který čte: hloupé knihovny, tenké lepidlo, chytrost v
tabulkách. Známé modré okno nad samopopisným archivem.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
