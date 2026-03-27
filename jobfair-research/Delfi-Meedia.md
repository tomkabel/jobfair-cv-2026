# Delfi Meedia — Job Fair Research Report

**Prepared for:** kood/JobFair 2026 attendee (Tom Kristian Abel)  
**Date:** March 27, 2026  
**Relevance:** Security researcher / CTO — offensive security, DevOps, web security

---

## Company Overview

**Delfi Meedia AS** (formerly Ekspress Meedia) is Estonia's largest digital media company and subsidiary of **AS Ekspress Grupp** (listed on Nasdaq Tallinn).

| Metric | Value |
|--------|-------|
| **Employees** | 425+ |
| **Subscribers** | 200,000+ digital (~21% of Estonia's online population) |
| **Monthly readers** | 700,000+ |
| **Page views** | 110M monthly |
| **Revenue** | 88% from digital |
| **Parent** | AS Ekspress Grupp (~1,700 employees, Baltic-wide) |

**Portfolio:** Delfi.ee (Estonia's largest news portal), 20+ portals, podcasts (50+ shows), events platform, unified subscription system.

---

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Architecture** | Micro-frontend (each portal component = separate application) |
| **CMS** | Custom-built (with Civitta) |
| **Backend** | Node.js |
| **Cloud** | Microsoft Azure |
| **AI/ML** | Internal translation (4 languages), transcription, archive search, recommendation engine, court case summarization, data chatbot |
| **DevOps** | Active DevOps roles (hired Oct 2025) |

---

## Security-Relevant Aspects

1. **Large attack surface** — 110M monthly page views, 20+ portals, subscription paywall
2. **Micro-frontend architecture** — security boundaries between components, API gateway security
3. **Paywall/authentication** — identity management, session security across portals
4. **AI integration risks** — prompt injection on internal chatbots, data leakage through LLM tools
5. **GDPR compliance** — EU-based media handling user data across 20+ portals
6. **Azure data consolidation** — 8 years of consolidated data warehouse, cloud security

---

## Current Opportunities

- **Delfi Suvine Praktika 2026** (Summer Internship) — deadline April 30, 2026, Tallinn/Tartu
- **Technical Challenge** at job fair — Level 🌶️🌶️🌶️, prize is internship
- Spontaneous applications accepted via careers page

---

## Relevance for Tom (Security/CTO Profile)

**MEDIUM FIT** — Interesting from a web security perspective but less security-focused than other companies:

1. **Web application security** — massive public-facing platform with micro-frontend architecture
2. **Paywall bypass** — authentication and session management across 20+ portals
3. **AI security** — securing internal AI tools (chatbots, translation, transcription)
4. **Content integrity** — defending against misinformation, content injection
5. **Azure cloud security** — data governance for consolidated media data

**Note:** Delfi Meedia doesn't appear to have a dedicated security team. Security may be handled within DevOps/general engineering. This could be an opportunity to propose security improvements.

---

## Key Talking Points

- "How do you handle security for 20+ portals behind a unified paywall?"
- "The micro-frontend architecture — how do you handle security boundaries between components?"
- "Your internal AI chatbot for data querying — how do you prevent data leakage?"
- "What's your approach to content integrity and defending against AI-generated misinformation?"

---

## Sources

- https://delfimeedia.ee/
- https://delfimeedia.ee/talent/
- https://pressgazette.co.uk/paywalls/delfi-meedia-ai/
- https://civitta.com/our-work/delfi-building-a-cutting-edge-technology-for-content-management-system/
- https://egrupp.ee/en/
- https://www.cv.ee/en/vacancy/1519022/delfi-meedia-as/delfi-suvine-praktika-2026
