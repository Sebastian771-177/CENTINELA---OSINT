◈ Centinela OSINT
Spanish-Language Threat Intelligence Monitor

Bridging the gap in English-centric SOC tooling by applying AI-powered analysis to Spanish-language cybercriminal ecosystems across Latin America and Spain.


🔍 What It Does
Centinela ingests raw Spanish-language posts from clandestine threat sources — dark web forums, Telegram channels, and underground marketplaces — and uses the Anthropic Claude API to extract structured threat intelligence automatically.
For each threat feed item, Centinela produces:

Severity rating — CRITICAL / HIGH / MEDIUM / LOW
Threat type — e.g. Initial Access Broker, Ransomware-as-a-Service
MITRE ATT&CK TTPs — mapped to the threat behavior described
Targeted sectors and countries
IOCs — handles, wallet addresses, contact info
Threat actor profile — motivation, sophistication, likely origin
Analyst recommendations — concrete next steps
TLP classification — RED / AMBER / GREEN
Intelligence gaps — what's still unknown and worth investigating

Results are rendered as a color-coded HTML dashboard directly in Google Colab.

🌎 Why This Matters
The majority of commercial threat intelligence platforms are built around English-language sources. Spanish-speaking threat actors — operating across Mexico, Argentina, Chile, Colombia, Venezuela, and Spain — represent a major and growing segment of the global cybercriminal ecosystem that is routinely undermonitored.
Analysts with Spanish fluency and regional expertise are uniquely positioned to close this gap. Centinela demonstrates how large language models can accelerate that work — turning raw, unstructured Spanish-language threat content into analyst-ready intelligence in seconds.

🛠 Technologies

Python 3.10+
Anthropic Claude API (claude-opus-4-5) — structured intelligence extraction via prompt engineering
Google Colab — interactive notebook environment with HTML rendering
IPython.display — dashboard rendering


🚀 Getting Started
Run in Google Colab (recommended)

Open the notebook in Google Colab
Click the 🔑 Secrets icon in the left sidebar
Add a secret named ANTHROPIC_API_KEY with your key from console.anthropic.com
Toggle Notebook access ON
Run all cells top to bottom

Run locally
bashpip install anthropic
export ANTHROPIC_API_KEY=sk-ant-...
python centinela_osint.py

Remove the from google.colab import userdata line and set your key via environment variable when running locally.


📊 Sample Output
Each analyzed threat produces an intelligence card like this:
┌─────────────────────────────────────────────────────┐
│ MX-2025-001 · Foro Clandestino MX           ⚠ CRITICAL │
│ Initial Access Broker                        TLP:RED   │
│ 📍 México                              Confidence: HIGH │
├─────────────────────────────────────────────────────┤
│ RAW POST: "Se vende acceso RDP a empresa financiera  │
│ CDMX. Panel admin, 500 equipos, sin AV..."           │
├─────────────────────────────────────────────────────┤
│ SUMMARY: A threat actor is selling RDP access to a  │
│ financial institution in Mexico City...              │
│                                                     │
│ TTPs: Remote Desktop Protocol · Valid Accounts      │
│ SECTORS: Finance · Banking                          │
│ COUNTRIES: 🇲🇽 Mexico                               │
│ IOCs: @sombra_red (Telegram)                        │
└─────────────────────────────────────────────────────┘

📁 Project Structure
centinela-osint/
├── centinela_osint.py   # Main script (also paste into Colab cells)
├── README.md            # This file
└── centinela_output.json  # Generated after running — structured intel reports

🔮 Roadmap

 Live Telegram channel monitoring via telethon
 STIX 2.1 export format for SIEM integration
 Automated IOC enrichment via VirusTotal API
 Regional actor tracking and attribution over time
 Spanish/English bilingual dashboard toggle


👤 Author
Sebastian [Last Name]
CompTIA Security+ | Google Cybersecurity Certificate
B.A. International Relations | Fluent in Spanish
Based in Miami, FL
Built as a portfolio project demonstrating the intersection of AI, threat intelligence, and Spanish-language domain expertise.

⚠️ Disclaimer
This tool uses entirely simulated threat feed data for demonstration purposes. No real dark web sources are accessed. This project is intended solely for educational and portfolio purposes.
