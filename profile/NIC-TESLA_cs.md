# NIC-Tesla — přijímač blesků / TGF (sferický)

Pojmenováno po **Nikolovi Teslovi** (vysoké napětí / Teslův transformátor). Doma
postavitelný **sferický přijímač** — tři ortogonální feritové smyčky + front-end
OPA1637 + ADC ADS127L14 + **STM32H523** — který detekuje blesky **na hraně** (edge-AI
klasifikace) a posílá drobný **fixní záznam události**, ne syrové průběhy. **Vlastní
deska** → vlastní front (pravidlo: deska má jméno).

Protože každý node sdílí síťové hodiny s ~120 ns, každý úder dostane časovou značku pro
síťovou multilateraci (TOA přes vzdálené stanice), a záblesk gama záření z bouřky
(**TGF**) lze korelovat s radiačními deskami (**Quark** / **Photon**).

Návrh na papíře: detekce je pevná část; lokalizace potřebuje širokou síť.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
