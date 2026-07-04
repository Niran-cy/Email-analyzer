# 🛡️ SOC Email Analysis Terminal

An advanced, enterprise-grade Security Operations Center (SOC) web application engineered to ingest, parse, and triage malicious email artifacts in real-time. This application features a decoupled full-stack architecture that extracts deep header metadata, parses multi-vector payload links, and leverages global threat intelligence feeds to deliver automated security verdicts.

Live: `https://niran-cy.github.io/Email-analyzer/`
Live Backend Core: `https://email-analyzer-yzh1.onrender.com`

---

## 🚀 Key Features

* **Multi-Vector Risk Scoring Grid:** Goes beyond binary categorization by parsing risk across three independent threat vectors: Cryptographic Sender Authenticity, Payload Link Reputation, and Heuristic/Intent Threat Analytics.
* **Deep Header Inspection:** Extracts and renders `Authentication-Results` formatting to immediately surface discrepancies in SPF alignment and DKIM cryptographic signatures.
* **Optimized SOC Dashboard UI:** Tabbed dark-mode terminal tailored for tier-2/3 security operations, optimizing cognitive load by categorizing dense forensic data into logical, readable data tables.
* **Live Threat Feed Integration:** Direct ingestion to the VirusTotal API to cross-reference extracted domains against 90+ global security vendor sets.

---

## 🛠️ Tech Stack

* **Frontend:** Vanilla JavaScript (ES6+ async/fetch), Semantic HTML5, CSS3 Custom Properties (SOC Dark Grid Theme). Hosted on GitHub Pages.
* **Backend:** Python 3, FastAPI (Asynchronous API framework), Uvicorn (ASGI web server). Hosted on Render.
* **Libraries & APIs:** Python Standard `email` parser, `requests` architecture, Live VirusTotal API.

---

## 📐 System Architecture

1. **Ingestion:** The analyst pastes raw RFC 822 email source code (inclusive of all transport headers and multipart body strings) into the ingestion terminal.
2. **Parsing Framework:** The asynchronous FastAPI backend leverages standard parsing libraries to isolate top-level headers, locate cryptographic verification tags, and run regular expressions to extract unique domains.
3. **Intel Cross-Referencing:** The isolated domain is routed to live external threat intelligence nodes using secure environment credential parsing.
4. **Telemetry Feedback:** Structured JSON response data maps dynamically onto the active layout elements without necessitating a browser state reload.

---

## 🔧 Production Installation & Setup

### Prerequisites
* Python 3.8+ installed locally.
* A valid VirusTotal API Key.

### 1. Cloud Backend Configuration (Render)
The backend is configured to build dynamically using a decoupled package tree via `requirements.txt`:
```text
fastapi
uvicorn
requests
