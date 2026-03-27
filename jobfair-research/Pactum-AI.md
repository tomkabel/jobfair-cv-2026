# Pactum AI — Job Fair Research Report

**Prepared for:** kood/JobFair 2026 attendee (Tom Kristian Abel)  
**Date:** March 27, 2026  
**Relevance:** Security researcher / CTO — AI security, offensive security, system architecture

---

## Company Overview

**Pactum AI** builds autonomous AI agents that negotiate supplier contracts at scale for Fortune 500 / Global 2000 companies.

| Metric | Value |
|--------|-------|
| **Founded** | 2019 |
| **HQ** | Mountain View, CA (engineering in Tallinn) |
| **Employees** | 130+ from 10+ countries |
| **Funding** | >$100M total (Series C: $54M, Jun 2025, Insight Partners) |
| **Key clients** | Walmart, Honeywell, Novartis, Rolls-Royce, BMW, J&J |
| **Fastest deal** | 87 seconds (fully autonomous) |
| **Largest deal** | $140.5M |

### Founders
- **Kaspar Korjus** (CEO) — Former MD of Estonia's e-Residency program
- **Kristjan Korjus** (Chief Scientist)
- **Martin Rand** (President)

---

## How the AI Works

1. **Opportunity Identification** — agents scan supplier bases for negotiation opportunities
2. **Policy Compliance** — agents operate within company rules and approval chains
3. **Autonomous Negotiation** — AI engages suppliers via conversational interfaces
4. **Execution** — agreements signed and fed into ERP systems (SAP Ariba, Coupa)

**Key metrics:** 489% increase in spend handled, 500%+ increase in negotiation volume, 1-7% savings on negotiated spend

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | TypeScript/Node.js (NestJS), Kotlin |
| **Frontend** | React |
| **Database** | PostgreSQL, Redis |
| **Infrastructure** | Google Cloud Platform, Terraform |
| **CI/CD** | Deploy hundreds of times/week, 80%+ test coverage |
| **Practices** | Architecture Decision Records (ADRs), SOLID, DDD |

---

## Security Posture

- **SOC 2 Framework** — Information Security Program follows SOC 2 criteria
- **CSA STAR** certification
- **Third-party penetration testing** at least annually
- **All data on GCP** — encryption at rest + TLS/SSL in transit
- **SSO, 2FA**, least-privilege access control, quarterly access reviews
- **Annual risk assessments** including fraud considerations
- **Trust Center:** https://trust.pactum.com/

**Critical security context:** AI agents have real authority over millions of dollars. A catastrophic mistake is a real risk. Every negotiation decision must be trackable, auditable, and explainable.

---

## Current Open Positions

| Role | Location | Status |
|------|----------|--------|
| **Senior Software Engineer** | Tallinn, Hybrid | Active |
| Developer Experience Engineer | Tallinn | ~4 months ago |
| Open applications | Tallinn | engineering-open-application@pactum.com |

**Interview process:** 45-min intro → 1-hour coding → 2-hour system design (in-person) → Team interview → Offer

**Hiring approach:** "We consider everyone — most common offer is Senior, but we regularly hire high-potential juniors, Staff+ level engineers and Engineering leaders up to executive level."

---

## Recent Developments (2025-2026)

- **March 2026:** Requisition Alignment Agent launched (validates procurement requests for policy compliance)
- **June 2025:** $54M Series C from Insight Partners
- **2025:** Added Honeywell, Novartis, Tetra Pak as clients
- **2025:** Won Digital Europe's Future Unicorn Award
- **2025:** Named to ProcureTech 100

---

## Relevance for Tom (Security/CTO Profile)

**VERY HIGH FIT** — This is arguably the most interesting company for a security-focused CTO:

1. **AI safety engineering** — Agents handle $140M+ deals. The "catastrophic mistake" risk makes this a genuine safety and security problem
2. **Auditability by design** — Every decision must be explainable and auditable (gold standard for trustworthy AI)
3. **Enterprise security at scale** — SOC 2, pen testing, encryption everywhere, 50+ Fortune 500 clients
4. **Novel technical challenges** — Open-ended conversational AI in adversarial contexts (negotiation)
5. **Not "move fast and break things"** — Deploy hundreds of times/week but maintain 80%+ test coverage
6. **10 former startup CTOs on the team** — high-caliber engineering leadership
7. **CTO at MatX.ee** maps well to their leadership-oriented engineering culture

---

## Key Talking Points

- "The 87-second autonomous deal is impressive. How do you handle the safety/risk of AI agents with real financial authority?"
- "You have 10 former startup CTOs on the team. What does engineering culture look like at that level of experience?"
- "How does the security team work with engineering where a bug could mean a bad $140M deal?"
- "You just launched the Requisition Alignment Agent — is the platform heading toward more autonomous end-to-end?"
- Mention FELLIN HÄKK 2026 win — offensive security perspective on AI system robustness

---

## Sources

- https://pactum.com
- https://careers.pactum.com
- https://careers.pactum.com/jobs/6633946-senior-software-engineer
- https://github.com/pactum-ai
- https://pactum.com/security
- https://trust.pactum.com
- https://pactum.com/clients
- https://pactum.com/blog/news-pactum-secures-54-million-in-series-c-funding-to-scale-agentic-ai-in-procurement
- https://www.prnewswire.com/news-releases/pactum-launches-requisition-alignment-agent-to-advance-ai-driven-procurement-workflows-302713782.html
