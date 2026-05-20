# 🛡️ NusaShield AI

Multi-Agent Indonesian Fintech Fraud Detection Platform powered by MiMo AI.

## Architecture

```
┌─────────────────────────────────────────────────┐
│                 NusaShield AI                    │
├─────────────────────────────────────────────────┤
│  ┌──────────┐ ┌──────────┐ ┌──────────────────┐ │
│  │ QRIS     │ │ Phishing │ │ Invoice Fraud    │ │
│  │ Scanner  │ │ Detector │ │ Analyzer         │ │
│  │ Agent    │ │ Agent    │ │ Agent            │ │
│  └────┬─────┘ └────┬─────┘ └───────┬──────────┘ │
│       │             │               │            │
│  ┌────┴─────────────┴───────────────┴──────────┐ │
│  │          Agent Orchestrator                  │ │
│  │          (Hermes Agent)                      │ │
│  └─────────────────┬───────────────────────────┘ │
│                    │                              │
│  ┌─────────────────┴───────────────────────────┐ │
│  │         MiMo-V2.5-Pro API                   │ │
│  │         (Long-chain Reasoning)              │ │
│  └─────────────────────────────────────────────┘ │
│                                                  │
│  ┌──────────┐ ┌──────────┐ ┌──────────────────┐ │
│  │ WhatsApp │ │ Threat   │ │ Indonesian Fraud │ │
│  │ Scam     │ │ Intel    │ │ Intel Layer      │ │
│  │ Agent    │ │ Agent    │ │ (BI, OJK, BSSN)  │ │
│  └──────────┘ └──────────┘ └──────────────────┘ │
└─────────────────────────────────────────────────┘
```

## Why Indonesia

Indonesia loses **~Rp 200 trillion (~USD 12.5B) per year** to digital fraud.
QRIS, OVO, GoPay, DANA, ShopeePay are now the daily payment surface for
200M+ users — and the same surface scammers target with QRIS swap, fake
merchant codes, social-engineered WhatsApp Business accounts, and forged
invoice PDFs.

NusaShield AI is the first MiMo-powered, Indonesian-language multi-agent
defense system tuned to that fraud surface. Every agent reasons in Bahasa
Indonesia and references local artifacts — BI regulations, OJK directives,
BSSN advisories, and Polri Cyber Crime patterns.

## Multi-Agent System

| Agent | Role | Model | Tokens/run |
|---|---|---|---|
| QRIS Scanner | Detect QRIS swap, fake merchant codes, MPM/CPM tampering | mimo-v2.5-pro | 600K |
| Phishing Detector | Analyze SMS/WA/email links targeting Indonesian banks & wallets | mimo-v2.5-pro | 400K |
| Invoice Fraud Analyzer | Parse invoice PDFs, cross-check NPWP, bank account, vendor DB | mimo-v2.5-pro | 700K |
| WhatsApp Scam Agent | Classify WA Business / personal scams (DANA freeze, kurir, undian) | mimo-v2.5 | 350K |
| Threat Intel Agent | Cross-reference fraud signals across BI / OJK / BSSN feeds | mimo-v2.5 | 200K |
| Report Generator | Bahasa-Indonesia executive summary + remediation steps | mimo-v2.5 | 250K |

## Token Consumption Model

| Agent | Tokens/Operation | Frequency | Daily/User |
|---|---|---|---|
| QRIS Scanner | 600K | 12/day | 7.2M |
| Phishing Detector | 400K | Continuous (48x/day) | 19.2M |
| Invoice Fraud Analyzer | 700K | 4/day | 2.8M |
| WhatsApp Scam Agent | 350K | 24/day | 8.4M |
| Threat Intel Agent | 200K | 24/day | 4.8M |
| Report Generator | 250K | 6/day | 1.5M |
| **Total** | | | **~43.9M/day** |

At 100 active users (banks, fintech compliance teams, BPR): ~4.4B tokens/day → ~132B/month.

## Tech Stack

- **AI Models:** MiMo-V2.5-Pro (reasoning), MiMo-V2.5 (analysis)
- **Agent Framework:** Hermes Agent
- **IDE:** Cursor + Claude Code
- **Data sources:** BI fraud advisories, OJK SLIK, BSSN CSIRT, Polri Cyber
- **Storage:** PostgreSQL + Redis
- **Deploy:** Docker + Kubernetes
- **Languages:** Bahasa Indonesia (primary), English (secondary)

## Target Users

- Indonesian digital banks (Jago, SeaBank, Allo, Blu, BTPN Jenius)
- E-wallet compliance teams (DANA, OVO, GoPay, ShopeePay, LinkAja)
- BPR / multifinance fraud ops
- KYC/AML platforms operating in Indonesia
- Government CSIRT and Cyber Crime units

## Status

🚧 Development in progress — seeking MiMo API credits for production scale.

## License

MIT
