# Porter PM Case Studies

**Deep dives into platform development, behavioral design, and systems architecture at scale**

These case studies document ~4 years of PM work at Porter, focusing on:
- Building 0→1 platforms in fintech (lending, taxation, fraud prevention)
- Behavioral product design (psychology-driven mechanisms)
- Systems thinking (coordinated infrastructure, not isolated features)

---

## About Porter

**What Porter Does:**
- Intra-city logistics marketplace connecting businesses with driver-partners
- Two-sided platform: Customers book deliveries, driver-partners fulfill orders
- Operates in 100+ cities across India
- Scale: 50K+ partners, 1M+ monthly transactions

**My Scope:**
- Product Manager for entire Partner App platform (Apr 2022 - Present, approaching 4 years)
- Own order lifecycle for partner side (onboarding → earnings → compliance → retention)
- Built fintech infrastructure (lending, taxation), trust systems (fraud prevention), and growth channels (digital acquisition)

---

## Evolution Arc: From Features to Platforms

**Phase 1 (2022): Feature Shipping**
- Built individual solutions to immediate problems
- Focus: Get things working, ship quickly
- Example: Partner onboarding flows, earnings dashboard

**Phase 2 (2023): Behavioral Design**
- Discovered traditional product levers (pricing, features) had limits
- Started exploring psychology-driven mechanisms
- Example: Flexible Payment Option (behavioral recovery loop)

**Phase 3 (2024-Present): Platform Thinking**
- Shifted from one-off solutions to extensible systems
- Built infrastructure that unlocks future capabilities
- Example: Taxation engine (TCS-ready before TCS existed)

**This repository documents Phase 2-3 work** (where platform + behavioral depth emerged)

---

## Case Studies

### 1. Lending Platform: Behavioral Recovery System ⭐ PRIMARY

**What I Built:**
End-to-end lending experience for driver-partners, scaling from 400 → 4K loans/month (₹100 Cr+ disbursed) while improving repayment from 73% → 90% and reducing acquisition cost by 40%.

**Why This Matters:**
- **Behavioral design depth:** Created recovery mechanism based on psychology (gradual repayment path vs binary suspension)
- **Platform infrastructure:** Built LMS integration, automated suspension engine, self-serve landing page
- **Business impact:** ₹2 Cr+ recovered incrementally, 1M+ supply hours added

**Signature Work: Flexible Payment Option**
- Psychology: Access denial drives behavior better than pricing changes
- Mechanism: Pay ₹1,500 → unlock 7 days → earn → clear more dues → repeat
- Proof: 2,200+ partners participated (avg 4 cycles each), many graduated out completely

**Read full case study:** [lending-platform.md](./lending-platform.md)

**Key Questions Answered:**
- How do you design products that change behavior, not just add features?
- How do you balance enforcement (suspensions) with support (gradual repayment)?
- How do you scale infrastructure while maintaining unit economics?

---

### 2. Taxation Platform: Configurable Compliance Engine

**What I Built:**
Rule-based tax compliance engine automating TDS deductions across 50K+ partners and 1M+ monthly transactions, improving recovery from 75% → 99% (₹2.4 Cr annually saved) while eliminating 3-4 days of month-end manual reconciliation.

**Why This Matters:**
- **Platform thinking:** Built for extensibility (TCS-ready without re-engineering)
- **Systems architecture:** Replaced city-by-city batch scripts with real-time, order-level engine
- **Regulatory depth:** Handles 8+ cohorts (PAN type, Aadhaar linkage, vehicle count, business model) automatically

**Architecture Decision:**
```
❌ Feature: Build TDS-specific logic
✅ Platform: Build rule-based engine for ANY tax type
```

**Outcome:** When TCS discussions started, zero re-engineering needed (just add new rules to engine)

**Read full case study:** [taxation-system.md](./taxation-system.md)

**Key Questions Answered:**
- How do you build products that handle future requirements you didn't anticipate?
- How do you automate complex regulatory compliance at scale?
- How do you migrate legacy systems (15K loans in Excel) without breaking operations?

---

### 3. Partner Acquisition & Trust Infrastructure

**What I Built:**
Supply acquisition and trust infrastructure, launching digital marketing channel (20% of new partners, 10% of activations) while blocking ₹50L+ in fraud losses and improving compliance to 78%.

**Why This Matters:**
- **0→1 channel:** Built digital attribution from scratch (Adjust MMP integration)
- **Fraud prevention at scale:** Document blacklist registry blocking 1,200+ re-onboarding attempts
- **Compliance infrastructure:** Vahan API real-time vehicle verification (50% → 78% compliant partners)

**Systems Design:**
- Real-time blacklist spanning multiple document types (PAN, Aadhaar, DL, RC) at OCR level
- Caught repeat offenders (one partner attempted ₹8L in fraud orders)
- Governance: 3-attempt threshold, appeals process, audit traceability

**Read full case study:** [partner-acquisition.md](./partner-acquisition.md)

**Key Questions Answered:**
- How do you build trust infrastructure that scales to 50K+ partners?
- How do you balance fraud prevention with legitimate partner experience?
- How do you measure success for 0→1 channels (attribution, CAC, activation rate)?

---

### 4. Discovery Framework: Opportunity Sizing (UNSHIPPED)

**What I Built:**
Comprehensive opportunity sizing framework identifying ₹8.5 Cr TAM across 20+ acquisition channels (OEM partnerships, corporate tie-ups, ride-hailing partnerships, student/gig worker programs).

**What Shipped:**
5/20+ recommendations (digital attribution, OEM partnerships, fraud blacklist, Vahan integration, educational landing page)

**Why Most Didn't Ship:**
Org focus shifted to unsecured loans regulatory challenges — most recommendations deprioritized despite validated TAM.

**Why This Is Included:**
- **Honest constraints:** Shows reality of product work (opportunity sizing ≠ execution guarantee)
- **Framework value:** Methodology reusable even if specific recommendations deprioritized
- **Stakeholder alignment:** Learning — TAM validation is useless without org buy-in

**Read full case study:** [acquisition-opportunity-sizing.md](./acquisition-opportunity-sizing.md)

**Key Questions Answered:**
- How do you size opportunities systematically (not just gut feel)?
- What do you do when validated opportunities don't ship?
- How do you prioritize across 20+ options with limited resources?

---

## Common Themes Across Case Studies

### 1. Platform Thinking Over Feature Shipping

**Taxation Example:**
- ❌ Feature: Build TDS deduction logic
- ✅ Platform: Build rule-based engine for ANY tax type (TCS-ready)

**Lending Example:**
- ❌ Feature: Add loan disbursement
- ✅ Platform: Integrate LMS (CKYC, CIBIL, automated suspensions) — enables future loan products

**Why It Matters:** Platforms unlock capabilities you didn't plan for

---

### 2. Behavioral Design Depth

**Flexible Payment Option:**
- Traditional lever: Pricing (lower interest rates to incentivize repayment)
- Behavioral lever: Access denial (suspend platform → pay to unlock → gradual repayment path)
- Psychology: Loss aversion + gradual commitment vs all-or-nothing

**Why It Works:** Access denial drives behavior better than pricing changes

---

### 3. Metrics-First Hypotheses

**Every product decision is a hypothesis to test:**

**Lending Recovery:**
- **Hypothesis:** Gradual repayment path increases recovery vs binary suspension
- **Mechanism:** ₹1,500 unlock fee → 7-day access → earn to clear more dues
- **Test:** Launched with 500 partners, measured participation rate + recovery amount
- **Outcome:** 35% of defaulters participated, avg 4 cycles, ₹2 Cr+ recovered
- **Conclusion:** Hypothesis validated → scale to 4K loans/month

---

### 4. Honest About Constraints

**What Worked:**
- Lending: Behavioral recovery loop (₹2 Cr+ recovered)
- Taxation: Rule-based engine (75% → 99% recovery)
- Fraud: Blacklist registry (₹50L+ blocked)

**What Didn't Ship:**
- Discovery Framework: 15/20+ recommendations deprioritized (org focus elsewhere)
- Taxation Edge Cases: Took 2 months post-launch to reach 99% (real-world complexity)

**Why This Matters:** Honest case studies are more credible than sanitized success stories

---

## Technical Depth Demonstrated

**What These Case Studies Show:**

1. **Systems Architecture:** Rule-based engines, real-time blacklists, coordinated infrastructure
2. **API Integrations:** CKYC, Vahan, Adjust, LMS integrations with external systems
3. **Data Modeling:** NoSQL structure (Firebase), cohort logic, transaction-level calculations
4. **Scalability Constraints:** 50K partners × 1M transactions/month = architectural considerations

**Why This Matters for PM Work:**
- Better product judgment (understand what's hard vs easy for engineering)
- Better prioritization (know where technical debt lives)
- Better stakeholder communication (can discuss architecture, not just features)

**Note:** I can now build React + TypeScript + Firebase apps myself (see [PlayLoop Studios](https://github.com/ProductAlchemist/playloop-studios)) — this technical depth directly improves PM decisions.

---

## How to Read These Case Studies

**For Hiring Managers:**
- **Looking for behavioral design?** Start with [Lending Platform](./lending-platform.md) (flexible payment mechanism)
- **Looking for platform thinking?** Start with [Taxation Platform](./taxation-system.md) (TCS-ready architecture)
- **Looking for 0→1 experience?** Start with [Partner Acquisition](./partner-acquisition.md) (digital channel from scratch)
- **Looking for honest constraints?** Start with [Discovery Framework](./acquisition-opportunity-sizing.md) (what didn't ship and why)

**For PMs:**
- Each case study includes: Problem context, solution mechanism, metrics with baselines, constraints faced, learnings
- Not sanitized success stories — includes what didn't work and why
- Replicable frameworks (opportunity sizing template, behavioral design principles)

---

## Evolution as PM (Meta-Learning)

**What I've Learned Through These Projects:**

1. **Features → Platforms:** Extensible systems unlock future capabilities (taxation TCS-ready)
2. **Pricing → Behavioral Levers:** Psychology-driven mechanisms > traditional product levers (flexible payments)
3. **Individual Solutions → Coordinated Infrastructure:** Shared systems prevent duplicated work (blacklist registry, CKYC integration)
4. **Perfect v1 → Iterative Optimization:** Ship, learn, optimize in production (taxation edge cases took 2 months)
5. **Opportunity Sizing → Stakeholder Alignment:** TAM validation is useless without org buy-in (discovery learnings)

**These learnings apply beyond Porter** — transferable to any platform, growth, or fintech PM role.

---

## Connect

**GitHub:** [ProductAlchemist](https://github.com/ProductAlchemist)
**LinkedIn:** [kshitijkulkarni-productmanager](https://www.linkedin.com/in/kshitijkulkarni-productmanager/)
**Email:** kshitijkulkarni95@gmail.com

**Currently exploring:** Senior PM roles (Platform PM, Growth PM, Fintech PM, AI PM) where I can apply platform thinking + behavioral design + technical depth at scale.
```

### Rationale for Changes

**From Previous (Summary-Level):**
- Brief case study descriptions
- Metrics without context
- No evolution arc or themes

**To This (Comprehensive):**
- **Evolution arc:** Feature shipping → behavioral design → platform thinking (shows growth as PM)
- **Why each case study matters:** Not just "what I built" but "why it demonstrates specific capability"
- **Common themes:** Platform thinking, behavioral design, metrics-first, honest constraints
- **Reading guide:** Helps hiring managers find what they're looking for quickly
- **Technical depth:** Shows systems architecture understanding (not just product specs)
- **Meta-learning:** Documents evolution as PM (transferable beyond Porter)
- **Honest constraints:** Discovery framework didn't ship (shows reality, not sanitized story)

**What Makes This Compelling:**
1. Shows progression (not static snapshot)
2. Connects case studies (not isolated projects)
3. Explains "why it matters" (not just metrics)
4. Includes what didn't work (credible vs sanitized)
5. Demonstrates transferable skills (frameworks, principles)

### Commit Message
```
Complete rewrite of porter-case-studies README with evolution arc and thematic connections

- Add evolution arc (feature shipping → behavioral design → platform thinking) showing PM growth
- Add "why this matters" for each case study (platform thinking, behavioral depth, 0→1 experience)
- Document common themes (platform over features, behavioral design depth, metrics-first hypotheses, honest constraints)
- Add reading guide for hiring managers (find what you're looking for quickly)
- Show technical depth (systems architecture, API integrations, scalability constraints)
- Include meta-learning section (what I learned through these projects)
- Add honest constraints (discovery framework didn't ship, taxation edge cases took 2 months)
- Connect to target roles (Senior PM, Platform PM, Growth PM, Fintech PM)

Focus: Show evolution and interconnectedness, not just isolated case summaries.
