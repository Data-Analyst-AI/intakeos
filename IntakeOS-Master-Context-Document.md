# INTAKEOS MEDICAL — MASTER CONTEXT DOCUMENT
## Everything Claude Needs to Know to Continue Working With This Team

**Generated:** May 16, 2026
**Purpose:** Upload this document to a new Claude Project called "IntakeOS Operations" so Claude has full context from Day 1 without re-explaining anything.

---

## 1. WHAT IS INTAKEOS MEDICAL?

IntakeOS Medical is an AI-powered intake automation system for medical clinics. It replaces the manual process of answering phone calls, booking appointments, sending reminders, and recovering no-shows with a fully automated, compliant (HIPAA/PIPA) system that runs 24/7.

**The core product:** An AI voice agent + web intake form system that captures leads, calls them back within 15 seconds, books appointments, sends reminders, verifies attendance, and recovers no-shows — all with full audit logging for compliance.

**Revenue model:**
- $500 CAD one-time deposit per client (setup fee)
- $100 CAD per confirmed consultation (manager-verified attendance = success fee)
- Monthly retainer TBD based on client size

**Target market:** High-ticket medical clinics in BC, Canada and Western US:
- LASIK / ophthalmology ($4,000-6,000 per procedure)
- Fertility clinics ($10,000-15,000 per cycle)
- Cosmetic surgery ($3,000-8,000 per procedure)
- Hair transplants ($4,000-15,000 per procedure)
- Aesthetic clinics (Botox, fillers, body contouring)
- Dental (implants, cosmetic dentistry)

**Why clinics should care:**
- Average response time to web inquiries is 47 hours — 90% of leads are lost
- No-shows cost $200+ per empty slot
- IntakeOS responds in 15 seconds, 24/7
- Clinics only pay for verified attended consultations (zero risk)
- Full HIPAA/PIPA compliance with audit trails (NemoClaw)

**Competitive advantage over market:**
- Most competitors sell generic chatbots without compliance
- Large platforms (Podium, Weave) cost $500-1,200/month with annual contracts
- IntakeOS charges per verified outcome (success fee model is rare)
- Full stack ownership (dedicated VPS, no vendor lock-in)
- NemoClaw provides audit logging that competitors lack

---

## 2. THE TEAM

### Phill (Co-founder — Architect)
- **Role:** Sales, strategy, client relationships, funding
- **Status:** Has full-time employment, works on IntakeOS part-time (~10-15 hrs/week Phase 1)
- **Puts up:** All Phase 1 capital (~$3,500 CAD)
- **Owns:** Business accounts (billing owner), strategic direction, closes sales
- **This Claude account belongs to Phill**

### Alejandra Martinez Vargas (Co-founder — Operations Coordinator)
- **Role:** Execution, operations, Engineer verification, admin, content, client management
- **Status:** Currently job searching (had interview May 16, 2026), more time available (~15-20 hrs/week)
- **Puts up:** Sweat equity (time and execution)
- **Owns:** Day-to-day operations, Engineer milestone verification, website, outreach execution, client onboarding

### Equity Structure
- **50/50 equity split** (not formally documented yet)
- **Equity pure model:** Neither takes salary until there's profit
- **Phill provides capital, Alejandra provides labor**
- **Capital repayment method:** NOT YET DECIDED (recommended: first profits repay Phill's investment, then 50/50 split)
- **Founders Agreement:** Draft was created but not yet formalized — they chose to skip legal formalities for now and operate on trust

### The Engineer (Contracted)
- **Status:** Signed agreement, waiting for Escrow to be funded to start Milestone 1
- **Payment:** Milestone-based via Escrow.com (total $2,100 CAD across 4 milestones)
- **Milestone 1:** $550 CAD — VPS setup, infrastructure, security (OpenClaw, NemoClaw, PostgreSQL, Docker, TLS, firewall)
- **Milestone 2:** $550 CAD — API integration, database, agent configuration
- **Milestone 3:** $700 CAD — Full system integration, voice agent, end-to-end testing
- **Milestone 4:** $300 CAD — Documentation (Master Configuration Log + Client Deployment Template)
- **Key terms:** Engineer provides ALL source code, full documentation, no ownership retained. All work verified by Alejandra before payment released. Credentials via Bitwarden only.

### Claude (AI Assistant — "Control Tower")
- **Role:** Produce deliverables (copy, templates, checklists, scripts), provide step-by-step guidance, and control browser when Chrome extension is connected
- **Can do independently:** Website copy, video scripts, email sequences, pitch decks, verification checklists, service agreements, onboarding questionnaires, all content
- **Cannot do:** Purchase accounts, enter passwords/payment info, sign contracts, fund Escrow, make final approval decisions

---

## 3. WHAT'S ALREADY DONE (as of May 16, 2026)

### Completed:
- [x] Engineer agreement signed (milestone-based, v2)
- [x] Operations Coordinator role document created (v2)
- [x] Slack workspace "IntakeOS Medical" created
- [x] Slack channel #client-admin created with description + welcome message + pin
- [x] Slack channel #engineer-updates created with description + welcome message + pin
- [x] Slack channel #verification-log created with description + welcome message + pin
- [x] Slack members: Phill (philk123), Alejandra Martinez Vargas, Engineer (invited)
- [x] Claude Project "IntakeOS Operations" created (on Phill's account)
- [x] 30-Day Launch Plan created (Word document)
- [x] Founders Agreement draft created (markdown)
- [x] Cloudflare + Google Workspace + Wix setup guide created

### NOT YET Done:
- [ ] Cloudflare account + domain purchase (arbitrageclaw.com)
- [ ] Google Workspace setup + operations@arbitrageclaw.com
- [ ] Wix website (template selection, build, content)
- [ ] Escrow.com account + Milestone 1 funding
- [ ] OpenPhone business number
- [ ] Bitwarden shared vault
- [ ] Wave accounting setup
- [ ] Bonsai service agreement + invoice templates
- [ ] Apollo.io account + outreach sequences
- [ ] AI demo video
- [ ] Claude Pro account for Alejandra (separate from Phill's)
- [ ] Claude in Chrome extension (not yet installed — needed for browser control)
- [ ] Google Business Profile

---

## 4. KEY TECHNICAL DETAILS

### Domain & Infrastructure
- **Domain:** arbitrageclaw.com (to be registered on Cloudflare Registrar, ~$10.44/year)
- **Website:** Wix Core plan, connected via pointing method (A record + CNAME, DNS only/gray cloud in Cloudflare)
- **Email:** Google Workspace Business Starter, MX record: smtp.google.com priority 1
- **CRITICAL:** Wix records in Cloudflare must be DNS only (gray cloud), NEVER proxied (orange cloud) — causes SSL errors

### DNS Records Needed in Cloudflare:
| Type | Name | Content | Proxy |
|------|------|---------|-------|
| A | @ | 185.230.63.107 (confirm in Wix wizard) | DNS only |
| CNAME | www | cdn1.wixdns.net | DNS only |
| MX | @ | smtp.google.com (priority 1) | n/a |
| TXT | @ | google-site-verification=... | n/a |
| TXT | @ | v=spf1 include:_spf.google.com ~all | n/a |
| TXT | google._domainkey | (DKIM from Google Admin) | n/a |
| TXT | _dmarc | v=DMARC1; p=none; rua=mailto:operations@arbitrageclaw.com | n/a |

### Engineer Technical Stack (what gets built):
- VPS: OVH Montreal
- Runtime: Node.js 24, pnpm, TypeScript
- Gateway: OpenClaw (systemd daemon)
- Audit: NemoClaw (compliance logging)
- Containers: Docker (OpenClaw, PostgreSQL, Caddy)
- Security: TLS 1.3 (SSL Labs A+), UFW firewall
- Database: PostgreSQL (4 tables per Schedule A)
- Voice: Retell AI integration
- CRM: GHL (GoHighLevel) integration
- API: Anthropic Claude API for AI agent

### Verification Process (Alejandra's responsibility):
For each milestone, Alejandra:
1. Receives "M[X] complete" notification in #engineer-updates
2. Runs ALL verification tests from the Master Engineer Brief
3. Posts each test result in #verification-log with format: [MX-YY] Test — PASS/FAIL [evidence]
4. Compiles evidence in Google Drive folder
5. Shares evidence link with Phill
6. Phill reviews and approves/rejects in Escrow.com
7. Escrow releases payment to Engineer (or dispute process begins)

---

## 5. THE 30-DAY PLAN (SUMMARY)

**Target: First client onboarded and LIVE by June 15, 2026**

### Week 1 (Days 1-5): FOUNDATION
- Buy domain, set up email, Escrow, Slack (done), OpenPhone
- Fund Escrow M1 so Engineer can start
- Claude Pro for Alejandra

### Week 2 (Days 6-10): BUILD + VERIFY M1
- Website live (Wix + all copy + AI video)
- Verify Engineer Milestone 1
- Set up Wave, Bonsai

### Week 3 (Days 11-15): OUTREACH LAUNCH
- Apollo.io configured with prospect lists
- Cold email + LinkedIn sequences launched
- Verify Engineer Milestone 2
- First 50-100 prospects contacted

### Week 4 (Days 16-30): CLOSE + ONBOARD
- Discovery calls with interested prospects
- Send proposals + service agreements
- Verify Engineer Milestones 3 & 4
- First client signs, system deployed, GOES LIVE

### Critical Path (if any slip, 30-day target at risk):
1. Day 1-2: Escrow funded → Engineer starts
2. Day 8-10: Engineer M1 verified
3. Day 14: Apollo outreach launches
4. Day 18-19: Discovery calls happen
5. Day 22-23: Engineer M4 complete (deployment template ready)

---

## 6. BUDGET SUMMARY

| Item | Cost |
|------|------|
| Domain (Cloudflare) | ~$10 USD/year |
| Google Workspace (1 user, monthly) | $8.40 USD/month |
| Wix Core | ~$17 USD/month |
| OpenPhone | $15 USD/month |
| Claude Pro (Alejandra) | $20 USD/month |
| Apollo.io Basic | $49 USD/month |
| AI Video Tool (1 month) | ~$29-59 USD |
| Engineer (4 milestones via Escrow) | $2,100 CAD (~$1,550 USD) |
| Escrow fees (~3.25%) | ~$68 CAD |
| **TOTAL PHASE 1** | **~$1,850-$1,950 USD** |

---

## 7. DECISIONS MADE

1. **Equity:** 50/50, equity pure (no salary until profit)
2. **Capital:** Phill funds Phase 1, Alejandra executes operations
3. **Legal:** No formal founders agreement yet (operating on trust)
4. **Website:** Wix (not custom-built)
5. **Domain registrar:** Cloudflare (at-cost pricing)
6. **Email:** Google Workspace Business Starter
7. **Outreach:** Apollo.io for cold email sequences
8. **Engineer payment:** Milestone-based via Escrow.com
9. **Verification:** Alejandra verifies all Engineer milestones before payment
10. **Claude's role:** "Control Tower" — produces deliverables, guides step-by-step, controls browser when extension connected

---

## 8. DECISIONS NOT YET MADE

1. Capital repayment method (Phill's $3,500+ investment)
2. Tie-breaker mechanism for founder disagreements
3. Non-compete terms if a founder leaves
4. Fair market value calculation for potential buyout
5. AI video tool selection (HeyGen vs Synthesia vs other)
6. Specific Wix template selection
7. Whether to incorporate as BC company (recommended but not decided)

---

## 9. COMMUNICATION PREFERENCES

- **Phill:** Prefers English, strategic thinker, wants Claude to be "control tower" and execute independently where possible
- **Alejandra:** Prefers Spanish (but can work in English), learning on the job, needs step-by-step guidance with explanations of WHY, not just HOW
- **Both:** Want brief, clear responses — not walls of text
- **Slack channels:**
  - #engineer-updates → Engineer daily progress
  - #verification-log → Alejandra's test evidence
  - #client-admin → General coordination

---

## 10. FILES TO ALSO UPLOAD TO THIS PROJECT

When setting up the new Claude Project, upload these files alongside this Master Context Document:

1. **ops-coordinator-role-v2.docx** — Full Operations Coordinator job description with weekly tasks
2. **engineer-agreement-v2.docx** — Full Engineer contract with milestone details and verification criteria
3. **IntakeOS-30-Day-Launch-Plan.docx** — Detailed day-by-day plan with task ownership
4. **IntakeOS-Founders-Agreement-DRAFT.md** — Draft founders agreement (optional, for reference)
5. **Master Engineer Brief** — Contains all verification test criteria per milestone (if you have this document)
6. **SOUL.md examples** — Brand voice and agent personality templates (if available)
7. **Brand voice guide** — Tone and messaging guidelines (if available)

---

## 11. HOW TO USE THIS DOCUMENT

When you start a new conversation in your Claude Project, Claude will automatically have access to everything above. You can simply say:

- "Pick up where we left off — what's the next task on the 30-day plan?"
- "Write the website homepage copy"
- "Create the Apollo cold email sequence for fertility clinics"
- "Give me the Milestone 1 verification checklist"
- "Help me set up Escrow.com"

Claude will know the full context without you re-explaining anything.

---

*End of Master Context Document*
