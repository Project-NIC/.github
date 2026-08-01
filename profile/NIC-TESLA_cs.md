# NIC-Tesla — přijímač blesků / TGF (sferický)

Pojmenováno po **Nikolovi Teslovi** (vysoké napětí / Teslův transformátor). Doma
postavitelný **sferický přijímač** — **čtyři feritové pruty** na komolé pyramidě +
diferenční front-end **THS4551** + ADC **ADS127L14** — který detekuje blesky **na hraně**
(edge-AI klasifikace) a posílá drobný **fixní záznam události**, ne syrové průběhy.

Tesla je **jedna jednotka NodeBusu, typový kód 7, na jedné desce**: analogový front a
**STM32H523, který běží její DSP**, sdílejí jeden plošňák v jedné IP68 krabici na anténním
rámu. Jediný konektor je **socket Galvani**.

Protože každý node sdílí jedny síťové hodiny — **doručená jedna mikrosekunda** — každý úder
dostane časovou značku pro síťovou multilateraci (TOA přes vzdálené stanice), a záblesk
gama záření z bouřky
(**TGF**) lze korelovat s radiačními deskami (**Quark** / **Photon**).

Návrh na papíře: detekce je pevná část; lokalizace potřebuje širokou síť.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
