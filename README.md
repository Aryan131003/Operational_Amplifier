# Two-Stage Operational Amplifier

![Technology](https://img.shields.io/badge/Technology-gpdk180%20180nm-green)
![Tool](https://img.shields.io/badge/Tool-Cadence%20Virtuoso-blue)
![Simulator](https://img.shields.io/badge/Simulator-ADE%20L%20Spectre-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Stability](https://img.shields.io/badge/Stability-Fully%20Stable-brightgreen)

A **Two-Stage Operational Amplifier** designed and simulated in Cadence Virtuoso using **gpdk180 (180nm)** technology. The design achieves high gain, excellent CMRR and PSRR, and is verified to be a fully stable system with all poles on the Left Half Plane (LHP).

---

## Specifications

| Parameter | Value |
|-----------|-------|
| Supply Voltage (VDD) | 1.8V |
| Technology Node | gpdk180 (180nm) |
| Topology | Two-Stage Amplifier |
| Open Loop Gain | **82 dB** |
| CMRR | **76 dB** |
| PSRR | **-70 dB** |
| Phase Margin | **146°** |
| Gain Bandwidth Product (GBW) | **30 MHz** |
| Stability | ✅ Fully Stable — All poles in LHP |
| Simulator | Spectre (ADE L) |

---

## Design Overview

A **Two-Stage Operational Amplifier** consists of:

```
Differential Input Stage (First Stage)
            │
            ▼
      Active Load
            │
            ▼
  Second Gain Stage (Common Source)
            │
            ▼
Miller Compensation Capacitor
```

- **First Stage** — Differential pair with active current mirror load providing high gain and good CMRR
- **Second Stage** — Common source amplifier providing additional voltage gain
- **Miller Compensation** — Ensures stability with a phase margin of 146°
- **Stability** — All poles verified on the Left Half Plane via PZ analysis

---

## Simulations Performed

| Analysis | Purpose |
|----------|---------|
| **AC Analysis** | Open loop gain, GBW, Phase Margin, CMRR, PSRR |
| **DC Analysis** | Bias point verification, transistor operating region check |
| **Pole-Zero (PZ)** | Full stability analysis — all poles confirmed in LHP |

---

## Simulation Results

### AC Response — Gain & Phase
![AC Response](simulations/Gain.png)

Open loop gain of **82 dB** with GBW of **30 MHz** and phase margin of **146°**.

### CMRR
![CMRR](simulations/CMRR.png)

Common Mode Rejection Ratio of **76 dB**.

### PSRR
![PSRR](simulations/PSRR.png)

Power Supply Rejection Ratio of **-70 dB**.

### Pole-Zero Analysis
![Pole Zero](simulations/PZ.png)

All poles confirmed on the **Left Half Plane** — fully stable system.

### DC Operating Point
![DC](simulations/DC.png)

All transistors verified in saturation region at correct bias point.

---

## Key Results Summary

| Parameter | Value | Status |
|-----------|-------|--------|
| Open Loop Gain | 82 dB | ✅ |
| CMRR | 76 dB | ✅ |
| PSRR | -70 dB | ✅ |
| Phase Margin | 146° | ✅ Excellent |
| GBW | 30 MHz | ✅ |
| Stability | All poles in LHP | ✅ Fully Stable |

---

## Design Notes

- **Two-stage topology** chosen for high gain with good output swing
- **Miller compensation** applied between first and second stage for stability
- Phase margin of **146°** indicates an extremely stable, well-compensated design
- All poles confirmed on **Left Half Plane** via PZ analysis
- Simulated using **Spectre** via **ADE L** in Cadence Virtuoso

---

## Future Improvements

- [ ] Transient step response simulation
- [ ] Process corner analysis (TT, FF, SS, SF, FS)
- [ ] Monte Carlo analysis for mismatch
- [ ] Output swing and slew rate measurement
