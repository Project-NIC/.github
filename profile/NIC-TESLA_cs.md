# NIC-Tesla — přijímač blesků / TGF (sferický)

Pojmenováno po **Nikolovi Teslovi** (vysoké napětí / Teslův transformátor). Doma
postavitelný **sferický přijímač** — **čtyři feritové pruty** na komolé pyramidě +
diferenční front-end **THS4551** + ADC **ADS127L14** — který detekuje blesky **na hraně**
(edge-AI klasifikace) a posílá drobný **fixní záznam události**, ne syrové průběhy.

Tesla je **analogový front bez vlastního procesoru**: **SPI-em se připojuje na node
Chinook** ve stejné krabici a **DSP blesků běží na Chinookově STM32H523**. Podle pravidla
„deska má jméno" je pořád vlastní pojmenovaný front.

Protože každý node sdílí síťové hodiny s ~120 ns, každý úder dostane časovou značku pro
síťovou multilateraci (TOA přes vzdálené stanice), a záblesk gama záření z bouřky
(**TGF**) lze korelovat s radiačními deskami (**Quark** / **Photon**).

Návrh na papíře: detekce je pevná část; lokalizace potřebuje širokou síť.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
