# NIC-Seismo — MEMS seismograf (front)

Pohyb země měřený MEMS místo geofonu: precizní **ADXL355** vedle akcelerometru
**ICM-42688** a sklonoměru **SCL-3300** — fúzované a kalibrované přímo na node, s detekcí
události běžící na hraně.

Je to univerzální jádro NIC node plus seismo senzory a jejich glue; právě to glue je
*jediná* věc, která dělá z node seismograf. Geofon stojí jako celý node, má horší
nízkofrekvenční odezvu a žádný DC náklon — MEMS dá obojí, a k tomu hustou síť.

Kompletní samostatný seismograf — jádro a tenhle front jako jeden buildovatelný produkt
s plnou hardware/firmware referencí — je kmen **[NIC-Quake](https://github.com/Project-NIC/NIC-Quake)**.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
