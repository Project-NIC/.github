# NIC-Weather — precizní vážicí meteostanice

Není to jedna krabička: je to malý projekt sám o sobě — hlavní jednotka plus sada nodů
sdílejících NIC RS-485 sběrnici a jedny hardwarové hodiny. Vlajkový přístroj je **vážicí
srážkoměr** — tenzometr, který naakumulované srážky váží místo překlápění — doplněný
Modbus meteo senzory: teplota/vlhkost, vítr, tlak, osvit, UV, blesky a půda.

Je to univerzální jádro NIC node plus meteo front (knihovny `nw-*`) a glue, které mluví
RS-485 / Modbus. V platformě navíc dělá **hub**, na který se věší ostatní fronty.

Jednoduché součástky, poctivá měření, jedna sdílená sběrnice — stanice, kterou postavíš a
provozuješ doma.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
