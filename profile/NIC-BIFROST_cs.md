# NIC-Bifrost — most ze světla

**Bifrost — severský most mezi světy, střežený Heimdallem.** Jméno sedí přesně:
strážce (Heimdall, síť) otevírá své světelné mosty (Bifrost) ze stanice do okolních
světů.

Domácí mostová karta s STM32H523: **jeden trunk + čtyři spur porty**, každý spur
point-to-point linka — optická nebo měděná — k jedné vzdálené jednotce. Ke každému
spuru je karta jeho **masterem a časovou autoritou**: vysílá hodiny, řídí enrollment,
**měří zpoždění vedení** (ranging gate) a mapuje čas spuru na čas sítě. K hlavě
předstupuje za své jednotky a podává nahoru hotové, otimestampované rámce. Své patro
řídí autonomně — masterovi zbývá jediné sloveso: „nahoď svoje patro."

Každá vzdálená jednotka visí za Bifrostem, každá ve vlastní časové doméně — uzel za
20 km skla se nikdy nedozví, že je vzdálený, a blesk, který sežere most, sežere jednu
kartu, ne stanici.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
