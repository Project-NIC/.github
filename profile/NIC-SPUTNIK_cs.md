# NIC-Sputnik — front GNSS / ionosféra

Ionosféra je zrcadlo, které se dá číst dobrými hodinami a dobrou anténou. NIC-Sputnik dělá
z jediného multi-konstelačního, vícefrekvenčního přijímače **Unicore UM980C** node, který
měří **Total Electron Content (TEC)** — sloupec volných elektronů nad hlavou.

Je to univerzální jádro NIC node plus jeden senzor: glue čte UM980C přes UART a kurátoruje
jeho výstup na sběrnici — surový základ, korekce, augmentace — drží jen to, co nese vědu,
ne celý proud dat.

Vyrostlo to ze seismografu: velké zemětřesení vyšle akusticko-gravitační vlny do
ionosféry o pár minut později, takže seismo a Sputnik node na jednom místě zachytí oba konce
toho řetězce — civilní vesmírné počasí z běžných součástek.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
