# NIC-GLUE (IN / OUT) — the seams

*Teaser · for Show HN, r/embedded, Hackaday and similar communities.*

---

The NIC libraries are deliberately ignorant of each other: MLA stores opaque
bytes, DMD packs fixed-width packets, KSF transforms bytes — none knows the others
exist. The *glue* is whatever code lines up the seams, and lining them up right is
the whole job.

**GLUE-IN** wires the write side: a sensor row, optional DMD compression, into an
MLA container — setting the compressed bit and keyframe distance so every rotated
file decodes on its own. **GLUE-OUT** is the same idea reversed: walk a finished
container back out to CSV or SQLite, decompressing as it goes.

Neither is a framework you must adopt. Each is a worked example plus a small
catalogue of the handful of seams where the libraries must agree — written down
once, so nobody has to rediscover them.

→ **[github.com/Project-NIC](https://github.com/Project-NIC)**
