# NIC-Chinook — reference kvality ovzduší

**Chinook** (severoamerický teplý vítr, „požírač sněhu") je vzdušné jméno pro vzduch, který
stanice dýchá. **Není to deska.** Každé čidlo ovzduší, které stojí za osazení, je kupovaná
**RS-485 Modbus jednotka**, takže tady není co vyrábět — tohle je sdílená reference, které
si své místo zaslouží a proč. Visí všude, kde má loadout ModeBus: na listu Palatiny, na
pomalé sběrnici hlavy nebo na kterémkoli nodu. Co není nativně Modbus, jde za **Babel**.

**Základní je jeden kanál — oxid uhelnatý přes NDIR.** Jako jediný projde oběma laťkami. Je
**trvanlivý**: uzavřená optická dráha, žádný elektrochemický článek a žádné pohyblivé části,
takže se opravdu osadí a zapomene — na rozdíl od VOC/NOx článků, které do roka umřou, a na
rozdíl od PM čidla s ventilátorem a zanášenou optikou. A je **smysluplný**: CO je ostrý
ukazatel nedokonalého hoření, takže jeho vzestup znamená, že *něco hoří* — ne pozadí, které
tu je pořád. A **spolu-časuje se**: požár zapálený bleskem se objeví jako vzestup CO
označkovaný stejnými hodinami jako úder, který ho založil, na každé stanici, která nese i
**Teslu**. CO je pomalé, takže nebere vyhrazený bajt na rámec — jede v muxu jako **1 bajt**.

**CO₂, PM2.5 a VOC zůstávají volitelné.** Chemické články žijí ~½–1 rok, což je opakovaný
náklad, který jde proti zalitému nodu ponechanému v terénu roky; a venku ta čtení většinou
nejsou událost — prach je tam pořád, CO₂ je dobře promíchané. CO₂ požár potvrzuje, PM2.5 je
rychlý signál kouře, ale je to servisní díl, ne osaď-a-zapomeň. Přesná chemie okolního
vzduchu je práce specializovaných agentur na pevných stanicích: schopnost je nabídnutá, jen
není osazená v základu.

**Žádný typový kód nodu, není co zapisovat do sítě.** Jednotky jsou Modbus slavy, adresuje
je node, který je čte, a objevují se v jeho muxu — ne na NodeBusu samy za sebe. Do jádra
protokolu se nepřidává nic.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
