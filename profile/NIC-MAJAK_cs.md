# NIC-Majak — datová stanice (clock master + datalogger + uplink)

Маяк — **maják**, a zároveň jméno staré rádiové stanice, která vysílala **časový
signál**. Přesně to dělá master: je to **head-end** jednoho RS-485 segmentu — jediný
tep, podle kterého se řídí celá síť.

Jeden oscilátor — vyhrazený **8.388608 MHz TCXO** zapojený přímo na hodinový pár — je
jediné hodiny v síti, takže každý node se na něj fázově zamkne na sub-mikrosekundu.
Majak přidělí každému nodu TDMA slot, řekne *jeď*, a pak už jen **poslouchá, ukládá a
uplinkuje**: microSD log NIC-MLA na jedné straně, úsporný 16bajtový LoRa / Wi-Fi
telemetrický rámec na druhé.

Je **front-agnostický** (ESP32 hlava): nenese žádnou znalost čidel — seismo, meteo, iono
i starDust nody se věší na stejný master beze změny. Postav jeden dobrý Majak a jeden
dobrý node, a máš stanici.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
