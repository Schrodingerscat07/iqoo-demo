# FreshGuard — Food Quality Screening Instrument

> **Flagship Multi-Modal Food Screening Application for iQOO 15**  
> A high-precision mobile instrument combining produce freshness inspection and physical acoustic resonance measurement.

---

## Overview

**FreshGuard** transforms the smartphone into a handheld food quality screening device. Engineered for high-confidence consumer and field diagnostics, FreshGuard screens produce freshness and milk purity without cumbersome manual input or third-party sensor peripherals.

### Core Inspection Modes

1. **Produce Freshness Screening**
   - **Automated Specimen Recognition**: Locks on to produce specimens directly in the viewfinder without manual category selection.
   - **Acoustic Impulse & Resonant Damping**: Analyzes mechanical cellular firmness and turgor pressure through tap impulse feedback.
   - **Optical Spectral Feature Mapping**: Evaluates chlorophyll breakdown, anthocyanin shifts, and cuticle degradation.
   - **Actionable Metrics**: Produces an integrated Freshness Index (0–100), estimated Remaining Useful Life (RUL in days), and daily degradation velocity.

2. **Milk Quality Check — Physical Acoustic Measurement Instrument**
   - **Multi-Vessel Acoustic Calibration**: Calibrated resonant profiles for standard tumblers, borosilicate beakers, thin stemware, and ceramic mugs.
   - **Chassis-to-Glass Mechanical Coupling**: Place phone directly against the glass wall with live acoustic contact pressure verification.
   - **Controlled Vibration Pulse**: Frequency-swept haptic excitation (80 Hz &ndash; 1,800 Hz) drives structural vibration into the liquid column.
   - **Ringdown Acoustic Listening**: High-sensitivity microphones capture boundary resonance decay envelope $A(t) = A_0 e^{-\zeta \omega_n t} \cos(\omega_d t)$.
   - **FFT Signal Analysis**: Computes resonant peak shift ($\Delta f$), viscous damping ratio ($\zeta$), speed of sound ($c$), and acoustic impedance ($Z$).
   - **ML Inference**: Machine learning classifier evaluates water dilution percentage and screens foreign adulterants (Urea, Starch, Detergents/Surfactants).

---

## Design System & Aesthetics

- **Technical Instrument Language**: Deep OLED black base (`#000000`) paired with crisp white typography, micro-borders, and silver telemetry accents.
- **Restrained Status Coding**: Green, amber, and red indicators reserved strictly for diagnostic classification states.
- **Seamless Asset Blending**: Transparent high-resolution icon artwork naturally dissolved into the interface background without enclosing frames or rounded boxes.
- **Fail-Safe Tactical Navigation**: Dedicated pill back-buttons, direct home exit shortcuts, persistent bottom docks, and history stack protection.

---

## Repository Structure

```
iqoo-demo/
├── index.html       # Complete single-file application with zero runtime dependencies
├── vercel.json      # Vercel deployment routing, security headers & asset caching
├── manifest.json    # PWA web app manifest for fullscreen home-screen mobile installation
├── package.json     # Project metadata and serve script
├── logo.png         # High-resolution transparent application logo
├── logo.jpg         # Original source asset
├── .gitignore       # Git ignore rules
└── README.md        # Technical documentation and deployment guide
```

---

## Deploy to Vercel

This repository is pre-configured and 100% production-ready for **Vercel** with automatic zero-config deployments:

### Deploy via Vercel Dashboard (Recommended)

1. Go to [vercel.com/new](https://vercel.com/new).
2. Select **Import Git Repository** and choose **`Schrodingerscat07/iqoo-demo`**.
3. Leave Framework Preset as **Other** (Root directory `./`).
4. Click **Deploy**.
5. Your app will be live with a global HTTPS `.vercel.app` URL in under 15 seconds!

### Automatic CI/CD

Every subsequent commit pushed to `main` on GitHub will automatically trigger a production deployment on Vercel.

---

## Quick Start / Local Execution

FreshGuard runs directly in any modern web browser or mobile WebView without requiring complex build steps or node modules:

```bash
# 1. Clone repository
git clone https://github.com/Schrodingerscat07/iqoo-demo.git
cd iqoo-demo

# 2. Launch with any HTTP server (e.g. Python or Node)
python -m http.server 8080
# or: npx serve .

# 3. Open in browser
http://localhost:8080
```

---

## Verification & Built-in Demo Scenarios

The application includes interactive simulated scenarios accessible via the **About & Diagnostics** tab -> **Demo & Verification Mode**:

- **Honeycrisp Apple**: Optimal freshness benchmark (Score: 88, RUL: 5–7 days).
- **Greenhouse Tomato**: Peak harvested freshness (Score: 94, RUL: 6–8 days).
- **Roma Tomato**: Advanced softening and overripe state (Score: 41, RUL: 0–1 day).
- **Pure Cow Milk**: Zero adulterants, nominal dilution baseline (~3.8% water profile, 1,248 Hz resonant peak, normal viscous damping).
- **Milk Sample (Water Dilution Anomaly)**: Flagged excess water dilution (+22.4%), resonant frequency shift to 1,180 Hz, reduced acoustic damping.

---

## License

MIT License. Designed and developed for demonstration on iQOO 15 flagships.
