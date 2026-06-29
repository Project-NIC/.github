# NIC-Quark — radiation detector front (design on paper)

Quark is the **radiation front** — just as Quake is the seismo front. Several
Geiger–Müller tubes behind graded lead / PE absorbers read **gamma in coarse energy
bands** (K1–K3), plus a **neutron channel** (K4) aimed at the gamma-ray flashes that
thunderstorms throw off (TGF). It is a *citizen-science relative monitor* — not
calibrated dosimetry — whose value is a **dense, cheap, clock-synced grid** that
correlates radiation bursts with specific lightning strikes across the network.

It is **design on paper**. Radiation is **not** a new node type: there are exactly four
(`seismo` / `basic` / `iono` / `starDust`), and Quark's counts ride in the Basic
payload's **K1–K4 block (offsets 27–30)**. A standalone detector reports as a Basic node;
combined with the lightning front it is a starDust node — either way the same four bytes,
the same decoder. The finalised detector physics live (in Czech) under the front's
`detektor-neutronu/` reference docs.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
