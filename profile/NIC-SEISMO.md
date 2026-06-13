# NIC-Seismo — MEMS seismograph front

Ground motion, measured by MEMS instead of a geophone: a precision **ADXL355** next to
an **ICM-42688** accelerometer and an **SCL-3300** inclinometer — fused and calibrated
on the node, with event detection running at the edge.

It is the universal NIC node core plus the seismo sensors and their glue; that glue is
the *only* thing that makes a node a seismograph. A geophone costs as much as a whole
node, with worse low-frequency response and no DC tilt — MEMS gives you both, and a
dense grid besides.

The complete standalone seismograph — the core and this front as one buildable product,
with the full hardware / firmware reference — is the **[NIC-Quake](https://github.com/Project-NIC/NIC-Quake)** trunk.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)** · ★ Viva La Resistánce ★
