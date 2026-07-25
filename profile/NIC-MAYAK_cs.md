# NIC-Mayak — hlava stanice (datalogger + uplink + sestava)

Маяк — **maják**, a zároveň jméno staré rádiové stanice vysílající časový signál.
Mayak je **hlava** NIC stanice: sbírá, ukládá a uplinkuje — microSD log NIC-MLA na
jedné straně, úsporný 16bajtový LoRa / Wi-Fi telemetrický rámec na druhé — a drží
**sestavu**: jednu malou tabulku, která JE složením stanice (přidání jednotky nikdy
neznamená sahat na firmware uzlů).

Od éry Bifrostů se hlava nedotýká žádné sběrnice přímo: každý z jejích dvou trunk
UARTů je point-to-point **MasterNOD linka** na mostovou kartu Bifrost a NodeBus jako
takový začíná až za nimi. Ani hodiny nejsou jeho — vyrábí je **Kronos** a hlavě podává
PPS, tikový signál a hrubou sekundu, jako soukromá GPS.

Je **front-agnostický** (hlava ESP32-S31): nenese žádnou znalost čidel — seismo,
meteo, iono i mag jednotky se věší na stejnou hlavu beze změny. Postav jednu dobrou
hlavu a jeden dobrý uzel, a máš stanici.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
