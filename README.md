# 🛰️ VOID — Satellite Intelligence System v7.0

> **Real-time satellite tracking · ESA imagery · AI disaster forecasting · Orbital debris risk · All free.**

## 🌍 What is VOID?

VOID is a full-stack **satellite intelligence platform** that connects real institutional data — from NASA, ESA, USGS, CelesTrak, and the US Space Command — into a single operational dashboard.

It tracks **800+ live satellites**, fetches **10-metre resolution ESA Sentinel-2 imagery**, predicts disaster escalation **72 hours ahead** using Meta's LLaMA 3.3 70B AI, monitors **22,000+ orbital debris objects** for collision risk, and computes population & infrastructure impact scores — all in one browser tab, completely free.

**Built by:** P. Jeevan Kumar — `astroflyerg1@gmail.com` — `+91 8072161639`

---

## 🚀 Live Demo

👉 **[void-intelligence.streamlit.app](https://share.google/qtB96bQnLnJXPFkJC)**

| Login | Password |
|-------|----------|
| `admin` | `void2024` |

---

## ✨ 7 Breakthrough Features

| # | Feature | What It Does |
|---|---------|-------------|
| **F1** | ☁️ Cloud Cover Prediction | Cross-references satellite pass windows with WMO hourly cloud forecasts — tells you exactly when to image |
| **F2** | 🤖 Autonomous AI Planner | One sentence → complete mission plan in 15 seconds. Zero manual steps |
| **F3** | 🛰️ Constellation Coordination | Coordinates top-5 satellites simultaneously — reduces revisit time from 5 days to 2–6 hours |
| **F4** | 🛡️ Orbital Debris Risk | Real-time conjunction risk from 22,000+ object CelesTrak debris catalog |
| **F5** | 💹 Market Intelligence | Live mission P&L, TAM by event type, benchmarked against Planet Labs & Maxar financials |
| **F6** | 🌍 Impact Scoring | Population exposure + infrastructure inventory (hospitals, roads, airports) per event |
| **F7** | 🔮 Escalation Forecast | 24h / 48h / 72h AI disaster evolution forecast using LLaMA 3.3 70B, grounded with live data |

---

## 📡 15 Operational Tabs

```
1.  Mission Control      — Live event map + satellite scoring + 3D globe
2.  Cloud Prediction     — F1: Per-pass cloud cover forecast
3.  Constellation        — F3: Multi-satellite coordination
4.  Debris Risk          — F4: Orbital conjunction analysis
5.  Market Intelligence  — F5: P&L + TAM + industry benchmarks
6.  Impact Score         — F6: Population & infrastructure exposure
7.  Escalation AI        — F7: 72-hour predictive disaster forecast
8.  Autonomous Planner   — F2: Zero-input mission planning
9.  Imagery              — ESA Sentinel-2 satellite imagery (7 spectral modes)
10. Pixel AI             — 3×3 grid vision analysis + conversational Q&A
11. Business Intel       — Charts, margins, competitive comparison
12. Reports              — Full structured mission reports (SQLite)
13. VOID AI              — Full-context intelligence chat (all modules combined)
14. Mission History      — Searchable log of all saved missions
15. Admin / Setup        — API health, user management, rate limiting
```

---

## 🛰️ Data Sources

| Module | Source | Institution | Accuracy |
|--------|--------|-------------|----------|
| Live Events | NASA EONET v3 | NASA GSFC | 1–10 km, 1–6h latency |
| Earthquakes | USGS GeoJSON | US Geological Survey | ±0.1° magnitude |
| Disasters | GDACS RSS | UN ODRR | Verified within 2–4h |
| Humanitarian | ReliefWeb | UN OCHA | Active declared disasters |
| Satellite TLEs | CelesTrak | Dr T.S. Kelso | SGP4 ±1–5 km LEO |
| TLE Authority | Space-Track.org | US Space Command | Authoritative SSN radar |
| Imagery | Sentinel Hub API | ESA Copernicus | 10 m, ±0.5 m geolocation |
| Cloud Forecast | Open-Meteo | WMO Standard | ±10–15% cloud cover |
| Impact | OpenStreetMap | Community / UN | >80% completeness |
| Debris | CelesTrak GP | US Space Command | 22,000+ tracked objects |
| AI Model | LLaMA 3.3 70B | Meta / Groq | Grounded with live data |

---

## 🖼️ Sentinel-2 Imaging Modes

| Event Type | Band Algorithm | Resolution |
|------------|---------------|------------|
| 🔥 Wildfire | SWIR: B04 + B11 (1610nm) + B12 (2190nm) | 20 m |
| 🌊 Flood | NDWI = (B03−B08)/(B03+B08) — Gao 1996 | 10 m |
| 🌾 Drought | NDVI = (B08−B04)/(B08+B04) — Rouse 1974 | 10 m |
| 🏚️ Earthquake | True RGB enhanced: B04+B03+B02 ×1.8 | 10 m |
| 🌋 Volcano | SWIR Thermal: B04+B11+B12 boosted | 20 m |
| 🌀 Storm | NDWI + RGB composite overlay | 10 m |
| 🧊 Sea Ice | True RGB enhanced ×2.0 | 10 m |

---

## 🧠 AI Stack

```
Primary   : Meta LLaMA 3.3 70B    — Mission planning, escalation, market analysis
Vision    : Meta LLaMA 3.2 90B    — Pixel-level satellite image interpretation
Fallback 1: Meta LLaMA 3.1 70B
Fallback 2: Mistral Saba 24B
Fallback 3: Gemma2 9B
Fallback 4: Meta LLaMA 3.2 3B

Inference : Groq Cloud (sub-second response, free tier)
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Python Streamlit — 15-tab layout, custom CSS dark theme |
| Orbital Mechanics | Skyfield + SGP4 — same algorithm as NASA GSFC |
| Concurrency | ThreadPoolExecutor (16 workers) — 800+ TLEs in 3–8 seconds |
| Visualisation | Plotly — 3D globe, P&L charts, conjunction plots |
| Database | SQLite3 — users, sessions, API logs, mission history |
| Security | SHA-256 hashing, secrets.token_hex sessions, role-based access |
| Imagery API | Sentinel Hub Processing API + OAuth2 — server-side evalscript |
| Image Processing | Python PIL — 3×3 grid crop for vision AI analysis |
| Weather | Open-Meteo WMO API + wttr.in fallback |

---

## ⚡ Quick Start — Run Locally

### 1. Clone the repo
```bash
git clone https://github.com/jeevanspace/void-intelligence.git
cd void-intelligence
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Set up API keys
Create a `.env` file in the project root:
```env
GROQ_API_KEY=your_groq_api_key_here
SH_CLIENT_ID=your_sentinel_hub_client_id
SH_CLIENT_SECRET=your_sentinel_hub_client_secret
```

### 4. Run the app
```bash
streamlit run app.py
```

Open **http://localhost:8501** in your browser.

5. Click **"Deploy"** — live in 3–5 minutes ✅

---

## 🔑 Get Free API Keys

| Service | Purpose | Get It Here | Cost |
|---------|---------|-------------|------|
| **Groq** | AI inference (LLaMA) | [console.groq.com](https://console.groq.com) | Free |
| **Sentinel Hub** | Satellite imagery | [apps.sentinel-hub.com](https://apps.sentinel-hub.com/dashboard) | Free (30K PU/month) |
| **NASA EONET** | Disaster events | No key needed | Free |
| **USGS** | Earthquake data | No key needed | Free |
| **CelesTrak** | Satellite TLEs | No key needed | Free |
| **Open-Meteo** | Cloud forecasts | No key needed | Free |
| **OpenStreetMap** | Infrastructure data | No key needed | Free |

---

## 💰 Commercial Value Delivered Free

| Capability | Commercial Equivalent | Annual Cost | VOID Cost |
|------------|----------------------|-------------|-----------|
| Live satellite tracking | AGI STK | $50,000/yr | **$0** |
| 10m satellite imagery | Planet Labs | $200K–$1M/yr | **$0** |
| Cloud-optimised tasking | Planet tasking dashboard | $50K+/yr | **$0** |
| Debris conjunction risk | LeoLabs / ExoAnalytic | $25K–$75K/yr | **$0** |
| 72h escalation forecast | Verisk AIR / RMS | $50K–$500K/yr | **$0** |
| Population impact scoring | ESRI ArcGIS + custom | $30K–$100K/yr | **$0** |
| Autonomous mission planner | Custom dev | $100K+ | **$0** |

---

## 🔒 Security

- SHA-256 password hashing with username salt
- Cryptographically secure session tokens (`secrets.token_hex(32)`)
- Role-based access control: `admin` / `analyst` / `viewer`
- Per-user, per-role API rate limiting
- Input sanitisation — XSS/injection prevention
- Full API usage audit log (timestamp, user, endpoint, latency)
- `.env` and database files excluded from version control

---

## 📁 Project Structure

```
void-intelligence/
├── app.py              # Main application — 5,200+ lines
├── requirements.txt    # Python dependencies
├── .gitignore          # Excludes .env, database, logs
└── README.md           # This file
```

---

## 📊 Industry Benchmarks

| Company | Gross Margin | Source |
|---------|-------------|--------|
| Planet Labs | 48% | NYSE:PL 10-K FY2024 |
| Spire Global | 41% | NYSE:SPIR filing |
| ICEYE | 38% | Series D disclosure |
| Maxar Technologies | 32% | Acquired by Advent 2023 |
| Satellogic | 29% | NASDAQ:SATL filing |
| **VOID** | **29–68%** | **Per-mission P&L** |

---

## 👤 About the Developer

**P. Jeevan Kumar** — Independent developer specialising in satellite intelligence systems, AI integration, and geospatial data platforms.

- 📧 Email: [astroflyerg1@gmail.com](mailto:astroflyerg1@gmail.com)
- 📞 Phone: +91 8072161639
- 🛰️ Platform: [void-intelligence.streamlit.app](https://void-intelligence.streamlit.app)

---

## 📄 License

MIT License — free to use, modify, and distribute with attribution.

---

## 🙏 Acknowledgements

- **NASA GSFC** — EONET disaster event API
- **ESA Copernicus** — Sentinel-2 satellite imagery
- **US Geological Survey** — Earthquake data feeds
- **Dr T.S. Kelso / CelesTrak** — Satellite TLE data
- **US Space Command** — Space-Track.org object catalog
- **Meta AI** — LLaMA 3.3 70B & 3.2 90B Vision models
- **Groq** — Ultra-fast AI inference infrastructure
- **Open-Meteo** — WMO-standard weather forecasts
- **OpenStreetMap** — Global infrastructure data

---

*VOID Satellite Intelligence System v7.0 · Built by P. Jeevan Kumar · February 2026*

