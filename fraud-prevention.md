# Supply Acquisition & Trust Infrastructure

## Overview

I built Porter's supply acquisition and trust infrastructure, creating a dual system that accelerated growth while protecting platform integrity. I launched a digital marketing channel contributing 20% of new partners and 10% of activations, established OEM partnerships delivering 5% of acquisitions, and built fraud prevention systems that blocked ₹50L+ in losses while improving vehicle compliance from 50% to 78%.

**Timeline:** 2023-2024
**Role:** Product Manager
**Team:** Cross-functional team including Engineering, Design, Data Science, Risk/Compliance, and Growth

---

## 📋 Problem

### Business Challenge

Porter faced a dual challenge: **grow supply fast to meet seasonal demand spikes** while **stopping fraud that was bleeding money and eroding trust**.

**Growth Problem:**
- **Seasonal Demand Spikes:** Customer demand surged during festivals and peak seasons, but we didn't have enough partners to fulfill orders
- **Single Acquisition Channel:** 100% dependent on field sales—slow, expensive, and couldn't scale fast enough
- **No Digital Funnel:** No way to acquire partners through digital channels (paid ads, search, social)
- **OEM Opportunity Untapped:** Vehicle manufacturers wanted to help drivers start businesses, but no B2B pipeline existed

**Trust & Compliance Problem:**
- **Fraud Bleeding Money:** Partners running fraudulent orders, fake deliveries, document manipulation
- **Repeat Offenders:** Blocked partners rejoining with new documents—no systematic way to catch them
- **₹50L+ Annual Losses:** Fraud costs were material and growing
- **Low Compliance:** Only 50% of partners had valid, verified vehicle documents (RC verification)
- **No Governance:** No clear appeals process, audit trails, or fair enforcement mechanisms

**The Strategic Tension:**
- Growing fast meant onboarding partners quickly with minimal friction
- Stopping fraud meant adding verification steps and blocking risky partners
- **How do you accelerate growth AND reduce fraud simultaneously?**

### Fraud Patterns Identified

Through data analysis and ops team insights, I identified three major fraud vectors:

**1. Repeat Offenders with New Documents**
- **How it worked:** Partners blocked for fraud (fake deliveries, customer complaints) would rejoin using new PAN, Aadhaar, or DL
- **Detection gap:** No cross-document blacklist—blocking one document type didn't prevent rejoining with another
- **Impact:** One partner attempted ₹8L in fraudulent orders across multiple accounts before we caught them manually

**2. Invalid/Fake Vehicle Documents**
- **How it worked:** Partners submitted forged or expired RC (vehicle registration) documents to bypass verification
- **Detection gap:** Manual RC verification was slow and error-prone. No real-time government database checks
- **Impact:** 50% of partners had unverified or invalid RCs, creating compliance and insurance liability risks

**3. Document Manipulation at OCR Level**
- **How it worked:** Sophisticated fraudsters edited PDFs/images to pass OCR (Optical Character Recognition) checks but fail manual review
- **Detection gap:** OCR extracted text looked valid, but underlying document was fake
- **Impact:** Fraud attempts passed initial automated checks, only caught in manual review (if at all)

### The Challenge

I had to balance competing priorities:

**Growth vs. Risk:**
- **Growth teams wanted:** Fast onboarding, minimal friction, high conversion rates
- **Risk teams wanted:** Multiple verification steps, manual reviews, conservative blocking
- **The balance:** How do you verify rigorously without killing conversion?

**False Positives vs. False Negatives:**
- **False positives:** Blocking legitimate partners hurts supply, damages brand trust
- **False negatives:** Letting fraudsters through costs money, harms customers
- **The trade-off:** Where do you set the threshold?

**Scale & Speed:**
- Fraud patterns evolve—yesterday's rules don't catch today's attacks
- Manual review doesn't scale to thousands of onboarding attempts
- Need automated systems that adapt without constant engineering

### User Experience Consideration

**Legitimate Partners:**
- Should feel welcomed, not suspected
- Verification should be fast and transparent
- Appeals process should be fair if wrongly blocked

**Growth Metrics:**
- Fraud prevention shouldn't tank conversion rates
- Time-to-onboarding should stay competitive
- Partner acquisition cost (CAC) should remain efficient

**Ops Teams:**
- Need tools to investigate fraud quickly
- Audit trails for compliance and dispute resolution
- Clear governance frameworks to make blocking decisions

---

## 💡 Solution

### Product Vision

I envisioned an **integrated growth and trust platform** where:

1. **Growth and fraud prevention reinforce each other:** Digital channels bring higher-quality partners; trust infrastructure protects growth investments
2. **Verification is invisible when it works:** Legitimate partners sail through; fraudsters hit walls at every turn
3. **Systems adapt automatically:** Fraud patterns change, but the platform learns and adjusts without manual rules updates
4. **Governance is fair and transparent:** Clear policies, appeals processes, and audit trails build trust

**Core Philosophy:** You don't choose between growth and safety. You build systems where **trust enables faster growth**.

### Dual-Track Approach

I built two parallel systems that worked together:

**Track 1: Growth Acceleration (New Supply Channels)**
- Launch digital marketing acquisition
- Build OEM B2B partnerships
- Optimize conversion through in-app improvements

**Track 2: Trust Infrastructure (Fraud Prevention)**
- Real-time blacklist registry
- Vehicle verification via government APIs
- Governance framework with appeals

### System Architecture

**Growth Infrastructure:**

**1. Digital Attribution & Tracking**
- Integrated Adjust (Mobile Measurement Partner) for partner-side attribution
- Tracked campaign performance: installs → signups → document submission → activation
- Enabled paid acquisition via Google Ads, Facebook, Instagram
- Full funnel analytics from ad click to first order

**2. OEM Partnership Pipeline**
- B2B onboarding flows for manufacturers (Hero, Bajaj, etc.)
- Manufacturer-funded incentive disbursement
- Bulk partner onboarding via dealer networks
- Custom reporting for OEM partners

**3. Conversion Optimization**
- Targeted in-app banners based on onboarding stage
- Automated lead assignment to onboarding agents
- Streamlined document upload flows
- Real-time progress tracking for partners

**Trust Infrastructure:**

**1. Real-Time Blacklist Registry**
- Multi-document blocking (PAN, Aadhaar, DL, RC)
- OCR-level blocking (detect manipulated documents)
- Cross-reference checks across document types
- Immutable audit log of all blocks

**2. Vahan API Integration**
- Real-time RC verification via government database
- Instant validation of vehicle ownership, registration status
- Automated compliance scoring
- Historical verification tracking

**3. Governance Framework**
- 3-attempt threshold before permanent block
- Appeals process with SLA (48-hour resolution)
- Manual review queue with context
- Audit traceability for regulatory compliance

**Integration Points:**
- **Onboarding Flow:** Fraud checks integrated seamlessly—partners don't see them unless flagged
- **Attribution System:** Digital campaigns feed into same verification pipeline as field sales
- **Partner App:** Compliance status, verification progress, appeals interface
- **Ops Dashboard:** Unified view of fraud cases, OEM pipeline, digital channel performance

### Key Features

**GROWTH TRACK:**

**1. Digital Marketing Acquisition Channel (Adjust Integration)**

Launched Porter's first digital acquisition channel, enabling paid marketing at scale.

- **What it does:** Tracks partner acquisition from ad click → install → signup → activation, enabling performance marketing
- **Why it matters:** Unlocked scalable, measurable acquisition beyond field sales. Could turn on/off spend based on ROI
- **How it works:**
  - Integrated Adjust SDK in partner app
  - Set up campaign tracking for Google Ads, Facebook, Instagram
  - Built attribution funnel: Click → Install → Signup → Document Upload → Activation → First Order
  - Created performance dashboards for growth team
- **Impact:** Scaled from 0% → 20% of total partner supply, 10% of activations

**2. OEM Partnerships (B2B Supply Pipeline)**

Established partnerships with vehicle manufacturers to create win-win acquisition model.

- **What it does:** Manufacturers fund onboarding incentives for drivers buying their vehicles; Porter gets vetted partners at lower CAC
- **Why it matters:** Creates sustainable B2B pipeline with higher-quality partners (vehicle owners vs. renters)
- **The Model:**
  - OEM pays ₹X incentive per partner activated
  - Drivers learn about Porter at vehicle purchase (dealer touchpoint)
  - Porter provides bulk onboarding via dealer network
  - OEM gets value (vehicle usage), Porter gets supply, driver gets income opportunity
- **Impact:** 5% of total acquisitions, significantly lower CAC than paid ads

**3. Conversion Optimization (In-App & Process)**

Improved conversion rates through targeted nudges and process improvements.

- **What it does:** Shows contextual banners, automates lead assignment, reduces friction in document upload
- **Key Changes:**
  - Targeted in-app banners based on onboarding stage (e.g., "Upload RC to start earning!")
  - Automated lead assignment to onboarding agents (reduced wait time)
  - Simplified document upload (one-tap camera vs. gallery upload)
  - Real-time progress tracker ("2/5 steps complete")
- **Impact:** CTR improved 40% → 52%, time-to-onboarding reduced by 15%

**TRUST TRACK:**

**4. Real-Time Blacklist Registry (Multi-Document Blocking)**

Built comprehensive blacklist spanning all identity and vehicle documents.

- **What it does:** Blocks fraudsters across PAN, Aadhaar, DL, and RC—even if they try to rejoin with new documents
- **Why it matters:** Catches repeat offenders who would otherwise create new accounts. Stopped one partner who attempted ₹8L in fraud
- **How it works:**
  - When partner is blocked, all their documents (PAN, Aadhaar, DL, RC) added to blacklist
  - At onboarding, check new documents against blacklist
  - OCR-level blocking: extract text from documents, check against known fraudulent entries
  - Cross-reference: If PAN is blacklisted, auto-flag Aadhaar even if different
- **Technical Innovation:** OCR text extraction + fuzzy matching to catch edited documents
- **Impact:** 90% reduction in monthly fraud attempts, ₹50L+ blocked

**5. Vahan API Integration (Real-Time Vehicle Verification)**

Integrated government vehicle database for instant RC verification.

- **What it does:** Verifies vehicle registration, ownership, and validity in real-time via Vahan (government RC database)
- **Why it matters:** Eliminated fake/forged RC documents, improved compliance from 50% → 78%
- **How it works:**
  - Partner uploads RC document
  - OCR extracts registration number
  - API call to Vahan database
  - Instant validation: Owner name, vehicle type, registration status, expiry
  - Auto-approve if match; flag for manual review if mismatch
- **Compliance Boost:** From 50% verified RCs → 78% in 6 months
- **Operational Impact:** Reduced manual RC verification time by 80%

**6. Governance Framework (Fair Enforcement)**

Established clear policies and appeals processes to balance enforcement with fairness.

- **3-Attempt Threshold:**
  - Partners get 3 chances to fix issues (invalid docs, failed verification)
  - Clear communication: "Attempt 1/3 failed. Here's why. Here's how to fix."
  - Permanent block only after 3 failures or confirmed fraud

- **Appeals Process:**
  - Partners can appeal blocks via in-app button
  - 48-hour SLA for resolution
  - Manual review with full context (block reason, document history, order history)
  - Clear communication of appeal outcome

- **Audit Traceability:**
  - Every block logged with reason, evidence, reviewer
  - Immutable audit trail for compliance (GDPR, local regulations)
  - Monthly fraud reports for leadership

### Technical & Product Decisions

**Growth + Trust Integration (Not Separate Systems):**
- **Decision:** Build fraud checks INTO the growth funnel, not as separate step
- **Rationale:** Seamless experience for legitimate partners; fraudsters blocked invisibly
- **Implementation:** Blacklist/Vahan checks run during document upload—partners don't see them unless flagged

**Real-Time Verification Over Batch:**
- **Decision:** Check documents at submission time, not end-of-day batch
- **Rationale:** Faster feedback to partners, prevents fraudsters from placing orders before detection
- **Trade-off:** Higher system load, but better UX and risk management

**Configurable Blocking Rules (Not Hardcoded):**
- **Decision:** Fraud rules configurable by risk team, not engineering deploys
- **Rationale:** Fraud patterns evolve weekly. Risk team needs control to adapt
- **Implementation:** Rule engine similar to tax system—config-driven blocking logic

**Attribution (Adjust) for Accountability:**
- **Decision:** Use third-party MMP (Adjust) instead of building in-house
- **Rationale:** Industry-standard attribution, prevents gaming by marketing agencies
- **Trade-off:** Vendor cost, but worth it for trusted measurement

**OEM Partnerships (B2B2C Model):**
- **Decision:** Pursue manufacturer partnerships vs. only direct-to-consumer acquisition
- **Rationale:** Lower CAC, higher quality partners (vehicle owners), sustainable pipeline
- **Enabler:** Built custom onboarding flows for bulk dealer-driven signups

### Implementation Strategy

**Phase 1: Trust Infrastructure (Month 1-2)**
- Built blacklist registry and integrated into onboarding flow
- Integrated Vahan API for RC verification
- Established governance framework (3-attempt threshold, appeals)
- **Rationale:** Get fraud prevention foundation in place BEFORE scaling growth

**Phase 2: Digital Attribution (Month 3-4)**
- Integrated Adjust SDK for partner app
- Set up first campaigns (Google Ads, Facebook)
- Built attribution funnel and dashboards
- Started with small test budget (₹5L/month)

**Phase 3: Scale Digital Channel (Month 5-7)**
- Scaled spend based on CAC vs. LTV
- Optimized campaigns based on activation rate, not just installs
- Grew to 20% of total supply

**Phase 4: OEM Partnerships (Month 6-9)**
- Pitched Hero, Bajaj, TVS on partnership model
- Built B2B onboarding flows
- Piloted with 2 OEMs, scaled to 5
- Reached 5% of acquisitions

**Phase 5: Conversion Optimization (Month 8-10)**
- Analyzed drop-off points in onboarding funnel
- Launched in-app banners (40% → 52% CTR)
- Automated lead assignment
- Reduced time-to-onboarding by 15%

**Testing & Monitoring:**
- **Shadow Mode:** Ran blacklist checks in shadow mode for 2 weeks before enforcement (validated accuracy)
- **A/B Testing:** Tested in-app banners, document upload flows
- **Weekly Fraud Reviews:** Risk team reviewed blocked cases, tuned rules
- **Attribution Validation:** Cross-checked Adjust data with internal analytics

---

## 📊 Impact

### Quantitative Metrics

**Growth Acceleration**

**Digital Acquisition Channel:**
- **20% of total partner supply** via digital marketing (from 0%)
- **10% of activations** (partners completing first order)
- **Scalable spend:** Could increase/decrease budget based on seasonal demand
- Unlocked new partner demographics (younger, tech-savvy drivers)

**OEM Partnerships:**
- **5% of total acquisitions** via manufacturer partnerships
- **Lower CAC:** 30% cheaper than digital ads
- **Higher quality:** Vehicle owners vs. renters = better retention
- 5 OEM partnerships established (Hero, Bajaj, TVS, etc.)

**Conversion Improvements:**
- **CTR: 40% → 52%** on in-app onboarding banners (30% relative improvement)
- **Time-to-onboarding reduced by 15%** through automated lead assignment
- Signup → activation conversion improved by 12%

**Fraud Prevention**

**Financial Impact:**
- **₹50L+ in fraud losses blocked** annually
- **90% reduction in monthly fraud attempts** after blacklist launch
- Caught one partner who attempted **₹8L in fraudulent orders** across multiple accounts
- Reduced fraud-related chargebacks and customer complaints

**Compliance Improvement:**
- **Vehicle compliance: 50% → 78%** (verified RC documents)
- **99%+ legitimate partner approval rate** (low false positive rate)
- Zero regulatory penalties for document fraud

**Operational Efficiency:**
- **80% reduction** in manual RC verification time (Vahan API automation)
- **48-hour SLA** for appeals resolution
- **3-attempt threshold** reduced unnecessary blocks by 40%

**Scale:**
- Blacklist registry processing **thousands of onboarding checks daily**
- Vahan API handling **500+ RC verifications per day**
- Digital channel contributing **hundreds of new partners monthly**

### Qualitative Impact

**Business Transformation**

**Growth Enablement:**
- Unlocked digital marketing as scalable acquisition channel—no longer dependent on field sales
- Created B2B partnerships that provide sustainable, high-quality supply
- Proved Porter could acquire partners digitally, enabling future expansion strategies

**Platform Integrity:**
- Shifted from reactive fraud detection (catching after losses) to proactive prevention (blocking before damage)
- Built trust with customers and partners—platform is safer, fairer
- Enabled partnerships with financial institutions who valued fraud controls (lending, insurance)

**Strategic Advantage:**
- Dual capability (growth + trust) became competitive moat—competitors often only have one or the other
- OEM partnerships created unique supply pipeline competitors couldn't replicate
- Fraud prevention infrastructure ready for international expansion

**Compliance & Risk:**
- Vehicle verification (50% → 78%) reduced insurance liability risks
- Audit trails and governance framework prepared Porter for regulatory scrutiny
- Appeals process built partner trust even when enforcement was tough

**Team & Culture:**
- Proved growth and trust teams can collaborate (not compete)
- Established playbook for launching new acquisition channels
- Risk team gained product tools (not just manual reviews)

---

## 🎓 Learnings

### What Worked Well

**1. Growth + Trust as Integrated Strategy**
- **What I did:** Built fraud prevention INTO growth systems from day 1, not as afterthought
- **Why it worked:** Legitimate partners had seamless experience; fraudsters blocked invisibly. No trade-off between growth and safety
- **Impact:** 20% of supply via digital with 90% fraud reduction. Both metrics improved simultaneously

**2. Real-Time Verification (Vahan API) Over Manual Reviews**
- **What I did:** Integrated government RC database for instant, automated verification
- **Why it worked:** Faster than manual (seconds vs. days), more accurate (source of truth), scales infinitely
- **Impact:** 50% → 78% compliance, 80% reduction in manual verification time

**3. Multi-Document Blacklist (Catch Repeat Offenders)**
- **What I did:** Blocked across PAN, Aadhaar, DL, RC—not just one document type
- **Why it worked:** Fraudsters can't just swap documents and rejoin. Cross-reference catches them
- **Impact:** Caught partner who attempted ₹8L in fraud; 90% reduction in repeat fraud attempts

**4. OEM Partnerships (B2B2C Model)**
- **What I did:** Built partnerships with vehicle manufacturers to create funded onboarding pipeline
- **Why it worked:** Win-win-win: OEMs get vehicle usage, drivers get income opportunity, Porter gets vetted supply at lower CAC
- **Impact:** 5% of acquisitions, 30% lower CAC than paid ads, higher retention

**5. Governance Framework (3-Attempt Threshold + Appeals)**
- **What I did:** Gave partners 3 chances to fix issues before permanent block; built appeals process
- **Why it worked:** Reduced false positives (legitimate partners blocked unfairly), built trust in enforcement
- **Impact:** 40% fewer unnecessary blocks, near-zero partner complaints about unfair treatment

### Challenges & How We Overcame Them

**1. Balancing Growth Team vs. Risk Team Priorities**
- **The Problem:** Growth wanted fast onboarding; risk wanted thorough verification. Tension over where to add friction
- **How I Solved It:**
  - Ran joint workshops mapping fraud risk vs. conversion impact at each step
  - Automated high-confidence checks (Vahan, blacklist) to remove manual friction
  - Set clear metrics: "We optimize for activation rate AND fraud rate, not one or the other"
  - Built shared dashboard showing both metrics—aligned incentives
- **Outcome:** Both teams became advocates for integrated approach. Growth team championed fraud prevention because it protected their investments

**2. OCR-Level Document Manipulation**
- **The Problem:** Fraudsters editing PDFs/images to pass OCR but fail manual review
- **How I Solved It:**
  - Added OCR text extraction to blacklist checks (not just document number, but full extracted text)
  - Fuzzy matching to catch typos/edits
  - Image hash comparison for known fraudulent documents
  - Manual review queue for edge cases
- **Outcome:** Caught manipulated documents that would have passed simple number checks

**3. Vahan API Rate Limits & Downtime**
- **The Problem:** Government API had rate limits (requests/min) and occasional downtime
- **How I Solved It:**
  - Implemented request queuing with backoff
  - Cached results for same RC number (TTL: 30 days)
  - Fallback to manual review when API down
  - Monitored API health, alerted ops team
- **Outcome:** 99.5% verification success rate despite API constraints

**4. False Positives in Blacklist (Legitimate Partners Blocked)**
- **The Problem:** Initial blacklist rules too aggressive—blocked partners with similar names, typos
- **How I Solved It:**
  - Tuned matching thresholds (exact match for PAN/Aadhaar, fuzzy match with manual review for names)
  - Added appeals process with 48-hour SLA
  - Manual review queue with full context (why blocked, document history)
  - Monitored false positive rate weekly, adjusted rules
- **Outcome:** False positive rate dropped from 5% → <1%

**5. Attribution Data Quality (Adjust Integration)**
- **The Problem:** Initial attribution data showed high installs but low activations—were we acquiring low-quality partners?
- **How I Solved It:**
  - Optimized campaigns for activation, not just install (shifted budget to high-performing channels)
  - Added fraud checks to attribution funnel (exclude fraudsters from performance metrics)
  - Built cohort analysis: Which campaigns drive long-term active partners?
- **Outcome:** Improved activation rate by 18% by reallocating budget to high-quality channels

### Key Takeaways

- **Growth + Trust Aren't Trade-Offs:** When you build fraud prevention into growth systems (not bolted on after), both metrics improve. Automated verification enables faster onboarding, not slower.

- **Real-Time > Batch for Fraud:** Catching fraudsters at onboarding (before they place orders) prevents losses. Batch detection (after fraud) is too late.

- **Multi-Layered Defense Wins:** No single check catches all fraud. Blacklist + Vahan + OCR + manual review creates redundancy that fraudsters can't bypass.

- **B2B Partnerships Beat Pure B2C:** OEM partnerships provided sustainable, high-quality supply at lower CAC. B2B2C model (manufacturer → dealer → driver) scales better than pure consumer acquisition.

- **Attribution Accountability Matters:** Without trusted attribution (Adjust), growth spend becomes a black box. Third-party MMP prevents gaming and enables optimization.

- **Governance Builds Trust:** 3-attempt threshold and appeals process made enforcement fair. Partners accepted tough fraud controls because process was transparent.

### What I'd Do Differently

**Earlier Focus on Quality Metrics (Not Just Volume)**
- Wish I'd optimized digital campaigns for activation rate from day 1, not just install volume. Spent 2 months acquiring high-install, low-activation partners before realizing quality mattered more.

**Predictive Fraud Scoring (ML Model)**
- Built rule-based fraud detection (blacklist, document checks) which worked well, but wish I'd invested in ML-based risk scoring earlier. Could have caught behavioral patterns (order frequency, location anomalies) that rules missed.

**In-App Fraud Education for Partners**
- Should have built educational content explaining why verification matters (safety, insurance, trust). Would have reduced appeals volume and built cultural norm against fraud.

---

## 🔮 Future Roadmap

**Planned Enhancements:**

**Advanced Fraud Detection:**
- **ML-Based Risk Scoring:** Behavioral signals (order patterns, location, earnings consistency) to predict fraud before it happens
- **Network Analysis:** Detect fraud rings (multiple partners operating from same location, sharing devices)
- **Biometric Verification:** Face match between selfie and government ID for high-risk onboarding

**Growth Expansion:**
- **Referral Program:** Partner-to-partner referrals with incentives (lower CAC than paid ads)
- **Regional Language Campaigns:** Digital ads in Hindi, Tamil, Telugu to reach underserved segments
- **Dealer Network Scaling:** Expand OEM partnerships to 10+ manufacturers

**Compliance Automation:**
- **Insurance Verification:** Real-time insurance policy checks via APIs
- **DL Expiry Tracking:** Auto-flag partners with expiring driving licenses
- **Periodic Re-Verification:** Annual RC/DL re-checks to maintain compliance over time

**Conversion Optimization:**
- **Smart Lead Routing:** Assign partners to best-fit onboarding agents based on language, location
- **Document Auto-Fill:** OCR pre-fill forms from uploaded documents (reduce typing)
- **Video KYC:** Live video verification for high-value partners (alternative to in-person)

---

## 🔗 Related Work

- [Lending Platform Case Study](./lending-platform.md) - Another example of building trust through behavioral design
- [Taxation Infrastructure Case Study](./taxation-system.md) - Platform thinking and compliance automation

---

*This case study demonstrates how to balance growth acceleration with fraud prevention, build B2B partnerships, and create trust infrastructure that enables (rather than hinders) scale.*
