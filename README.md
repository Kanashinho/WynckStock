# 📦 WyncStock — WhatsApp Inventory Management

<div align="center">

*Full inventory control directly through WhatsApp — no new apps, no training, no complexity.*

![N8N](https://img.shields.io/badge/N8N-Automation-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![Airtable](https://img.shields.io/badge/Airtable-Database-18BFFF?style=flat-square&logo=airtable&logoColor=white)
![WhatsApp](https://img.shields.io/badge/WhatsApp-API-25D366?style=flat-square&logo=whatsapp&logoColor=white)
![Python](https://img.shields.io/badge/Python-Scripts-3776AB?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Stable%20MVP-brightgreen?style=flat-square)

🇧🇷 [Leia em Português](README.pt-BR.md)

</div>

---

## 🚀 About

**WyncStock** solves a real problem for small and medium businesses: managers wasting time on outdated spreadsheets, manual entry errors, and lack of real-time inventory visibility.

The solution is radically simple — **use WhatsApp, the app everyone already knows**, as the control interface. No new apps to install, no team training, no learning curve.

> *"If your team already uses WhatsApp, your inventory system should too."*

---

## ✨ Features

| Command | Description |
|---------|-------------|
| `📥 in [product] [qty]` | Register stock entry |
| `📤 out [product] [qty]` | Register stock exit |
| `🔍 check [product]` | Query current stock level |
| `📊 report` | Full inventory report |
| `⚠️ alerts` | List low-stock products |

---

## 🛠️ Tech Stack

```
Automation
├── N8N              → Workflow orchestration (exported .json included)
└── Python Scripts   → Custom processing logic

Database
└── Airtable         → Inventory storage and management

Communication
└── Z-API            → WhatsApp Business integration
```

---

## 💡 How It Works

```
Manager sends a WhatsApp message
        ↓
Z-API captures and forwards to N8N
        ↓
N8N interprets the command
        ↓
Python handles the business logic
        ↓
Airtable is updated in real time
        ↓
Confirmation sent back via WhatsApp
```

---

## 📦 Getting Started

### Prerequisites

- [N8N](https://n8n.io) account (self-hosted or cloud)
- [Airtable](https://airtable.com) account
- [Z-API](https://z-api.io) account with a connected WhatsApp number
- Python 3.10+

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Kanashinho/SynckStock.git
cd SynckStock

# 2. Set up environment variables
cp .env.example .env
# Edit .env with your credentials

# 3. Install Python dependencies
pip install -r requirements.txt

# 4. Import the workflow into N8N
# In N8N panel: Settings → Import workflow → select the .json file
```

### Configuration (.env)

```env
# Z-API (WhatsApp)
ZAPI_INSTANCE=your_instance
ZAPI_TOKEN=your_token

# Airtable
AIRTABLE_API_KEY=your_key
AIRTABLE_BASE_ID=your_base_id
AIRTABLE_TABLE_NAME=Stock

# N8N
N8N_WEBHOOK_URL=http://localhost:5678/webhook/wyncstock
```

---

## 🗂️ Project Structure

```
SynckStock/
├── workflows/
│   └── wyncstock_flow.json   # N8N workflow (import this)
├── scripts/
│   └── processor.py          # Python processing logic
├── requirements.txt
├── .env.example
└── .gitignore
```

---

## 🗺️ Roadmap

- [x] Functional MVP with Airtable
- [x] Stock in/out/check commands via WhatsApp
- [x] Low-stock alerts
- [ ] **Migration to SQL** (PostgreSQL) — better performance and control
- [ ] **Local server deployment** — eliminates cloud dependency, reduces maintenance cost
- [ ] Scheduled automatic reports
- [ ] Multi-warehouse support
- [ ] Complementary web dashboard

---

## 💰 Ideal Use Cases

- Small retail stores
- Restaurants and supply stock
- Industrial warehouses
- Any business where the team already uses WhatsApp daily

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

Free to use, copy and modify, **as long as you keep credit to the original author**.

---

## 👤 Author

**Kauã M. S. Winter Moraes**
- LinkedIn: [linkedin.com/in/kaua-winter](https://linkedin.com/in/kaua-winter)
- GitHub: [@Kanashinho](https://github.com/Kanashinho)
- Email: kaua.wintermoraes@gmail.com

---

<div align="center">
<i>If this project was useful to you, consider leaving a ⭐</i>
</div>
