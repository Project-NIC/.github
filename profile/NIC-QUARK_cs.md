# NIC-Quark — front detekce záření (návrh na papíře)

Quark je **radiační front** — tak jako Quake je seismo front. Několik Geiger–Müllerových
trubic za odstupňovanými olověnými / PE absorbéry čte **gama v hrubých energetických
pásmech** (K1–K3) plus **neutronový kanál** (K4) mířený na záblesky gama záření, které
chrlí bouřky (TGF). Je to *občansko-vědecký relativní monitor* — ne kalibrovaná
dozimetrie — jehož cena je **hustá, levná, hodinami sítě synchronizovaná mřížka**, co
koreluje záblesky záření s konkrétními blesky napříč sítí.

Je to **návrh na papíře**. Záření **není** nový typ node: typy jsou přesně čtyři
(`seismo` / `basic` / `iono` / `starDust`) a Quarkovy counts jedou v **bloku K1–K4 v
Basic payloadu (offsety 27–30)**. Samostatný detektor reportuje jako Basic node; spojený
s bleskovým frontem je to starDust node — tak jako tak stejné čtyři bajty, stejný dekodér.
Finální fyzika detektoru žije (česky) v referenčních dokumentech frontu pod
`detektor-neutronu/`.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
