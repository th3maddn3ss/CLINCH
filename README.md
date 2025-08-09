# CLINCH — Laminar-Shear Biogel Closure System

> Open research project for rapid, low-trauma wound closure using **controlled superficial laminar shear** (epidermal, 50–150 µm) and a **biodegradable hydrogel** to create a **lap-joint seal** — no needles, no staples.

**License:** Research / Non‑Commercial only — code under **PolyForm‑Noncommercial‑1.0.0**; docs/design/data under **CC BY‑NC 4.0**. For commercial licensing, contact **devklav@gmail.com**.

---

## Why CLINCH?

- **Less trauma:** Operates within the **epidermis** to avoid microvasculature; aims for hemostasis without sutures/staples.  
- **Fast & clean:** Shear + gel deposition within **≤ 3 s** to beat elastic recoil and lock a lap‑joint.  
- **Cosmetic-aware:** Micro‑lattice sealing pattern distributes load, reduces edge gapping, and targets better cosmetic outcomes.  
- **Open research:** White page, references, and a full validation plan (S1–S12) included for replication.

---

## How it works (high‑level)

1. **Anchor & prep** — Micro‑ridge silicone pads (Shore 00 40–70) apply **20–60 kPa** normal pressure on IPA‑prepped skin.  
2. **Laminar shear** — A voice‑coil (±0.15 mm) plus piezo impulse delivers **0.02–0.05 N·s** tangential “taps,” creating a **50–150 µm** superficial shear plane (epidermal‑only).  
3. **Lap‑joint formation** — The actuator traverses with a **0.25–0.40 mm** stitch pitch; cross‑links every **0.8–1.2 mm** at **±30–45°** create a micro‑lattice.  
4. **Biogel seal** — Within **≤ 3 s**, a biodegradable gel (e.g., **chitosan** or **PEG–alginate**) is deposited to form a continuous **50–150 µm film** plus a **0.3–0.6 mm** edge bead.  
5. **Set & hold** — Gel modulus is matched to site tension (**1–10 kPa** low‑tension; up to **~50 kPa** high‑tension) to resist gapping and flexion.

---

## Key specs (current targets)

| Parameter | Target |
|---|---|
| Shear depth | **50–150 µm** (epidermal; blood‑sparing) |
| Normal pressure | **20–60 kPa** |
| Tangential impulse | **0.02–0.05 N·s** per tap |
| Stroke | **0.3 mm** total (±0.15 mm) |
| Stitch pitch | **0.25–0.40 mm** |
| Lattice cross‑links | Every **0.8–1.2 mm** at **±30–45°** |
| Gel modulus | **1–10 kPa** (low tension), up to **~50 kPa** (high tension) |
| Film + bead | **50–150 µm** film + **0.3–0.6 mm** bead |
| Timing | Gel deposition **≤ 3 s** after shear |
| Orientation | Traverse along local **Langer lines** |

---

## What’s in this repo

- `docs/CLINCH_whitepage.tex` — White page (core concept, design, background)  
- `docs/CLINCH_references.bib` — References for the white page  
- `docs/CLINCH_supplementary_tests.tex` — Supplement (S1–S12 validation studies when done)  
- `docs/figures/` — Figures for the white page (images here)  
- `cad/` — Pad molds, fixtures, and chassis (STEP/STL/FreeCAD)  
- `firmware/` — Controller stubs for voice‑coil + piezo actuation  
- `materials/gels/` — Formulations and notes (chitosan, PEG–alginate, etc.)  
- `tests/` — Study folders (S1 impulse‑depth, S2 adhesion/flex, …)  
- `scripts/analysis/` — OCT depth parsing, lap‑shear plots

---

## Build the docs

```bash
# From /docs
pdflatex CLINCH_whitepage.tex
bibtex   CLINCH_whitepage
pdflatex CLINCH_whitepage.tex
pdflatex CLINCH_whitepage.tex

# Supplementary
pdflatex CLINCH_supplementary_tests.tex
```

---

## Validation plan (summary)

See `docs/CLINCH_supplementary_tests.tex` for full protocols (S1–S12).

- **S1** Impulse–Depth calibration (OCT/Confocal)  
- **S2** Adhesion & flex durability (lap‑shear ≥ 20 kPa; 1000 cycles, ±10% strain; gap < 0.3 mm)  
- **S3** Timing sensitivity (0.5–5 s delay)  
- **S4** Orientation vs. Langer lines  
- **S5** Hair & surface condition (clip vs. unclipped; IPA vs. none; moisturized vs. clean)  
- **S6** Thermal/hydration envelope (18–30 °C; RH 20–70%)  
- **S7** Microvascular safety (epidermal‑only shear)  
- **S8** Biogel biocompatibility (ISO‑relevant screens)  
- **S9** High‑tension sites (modulus + lattice tuning)  
- **S10** Sterility/bioburden  
- **S11** Usability/timing (≤ 3 s workflow)  
- **S12** Failure modes & margins (overshoot, delay, misalignment)

---

## Status

- ✅ Biological logic validated (shear concept)  
- ✅ Actuation concept (voice‑coil + piezo hybrid)  
- ✅ Materials short‑list (pads + gels)  
- ✅ Lattice sealing concept  
- 🚧 CAD for pad molds  
- 🚧 Control loop (traverse ↔ tap frequency)  
- 🚧 Bench testing (analogs, porcine)  
- 🚧 Burst pressure & cyclic flexion validation  
- 🚧 Zenodo white page + GitHub publication

---

## Safety & scope

- **Research prototype. Not a medical device.**  
- No clinical or human use without IRB approval and regulatory compliance.  
- Follow the surface‑prep SOP (IPA wipe; 30–60 s dry).  
- Avoid extreme sites in early tests (very thin periorbital; very thick heel).  
- Keloid‑prone or metabolically compromised skin may need special caution.

---

## Contributing

PRs welcome! Please include:
- Exact parameters (impulse, pressure, stitch pitch, gel modulus)  
- Environment (temp, RH), surface prep, site orientation  
- Data + plots (OCT depth distributions, lap‑shear curves, gap metrics)  
- Any failure signatures and safety notes

---

## Licensing (research / non‑commercial)

- **Code:** PolyForm‑Noncommercial‑1.0.0  
- **Docs/Design/Data:** CC BY‑NC 4.0  
- Commercial use requires a separate license — contact **devklav@gmail.com**.  
- Trademarks: “CLINCH” name/logo are not licensed.


---

## Citing CLINCH

When referencing this work:

```
CLINCH — Laminar‑Shear Biogel Closure System (White Page).
devin lavrisha, 2025. https://github.com/th3maddn3ss/CLINCH
```

(Will replace with DOI once the Zenodo record is live.)

---

## FAQ (quick hits)

- **Does it bleed?** Target depth is **epidermal‑only** (50–150 µm) to avoid the papillary plexus.  
- **Why the ≤3 s timing?** To beat elastic recoil so the lap‑joint holds before edges spring back.  
- **Which gel?** Start with **chitosan** or **PEG–alginate**; pick modulus by site tension.  
- **Hair?** Clip to **< 0.3 mm** along the closure line; hair affects pad contact.  
- **Orientation?** Align with **Langer lines** to reduce opening stress.

---

## Contact

- Maintainer: **Devin Lavrisha** — **devklav@gmai.com**  
- Issues: GitHub Issues tab  
- Commercial licensing: **devklav@gmail.com**
