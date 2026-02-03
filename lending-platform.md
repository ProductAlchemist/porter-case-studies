# Lending Platform (0→1)


## 📋 Problem

### Business Challenge

When taking over the lending vertical, Porter had a lending operation running on Excel spreadsheets with 15,000 legacy loans and no proper loan management system. The business faced multiple critical challenges:

- **Operational Chaos:** Loan data scattered across Excel sheets with no single source of truth
- **Poor Unit Economics:** High CAC (₹625 per loan) and low repayment discipline (73% at 7 DPD) made lending unsustainable
- **Credit Bureau Risk:** Legacy loans weren't properly tracked, creating significant reporting compliance risks
- **Slow Processing:** Manual underwriting and disbursement took 7 days, losing qualified customers to competitors
- **Inefficient Sales:** 80-person sales team handling high-touch processes that should have been self-serve

The opportunity was massive—thousands of driver-partners needed working capital for vehicle maintenance, fuel, and business expansion—but we were leaving money on the table with broken processes.

### User Pain Points

Our driver-partners faced severe credit access challenges:

- **Traditional Banks Rejected Them:** Gig workers without salary slips couldn't access formal credit
- **Predatory Lending:** Many resorted to local moneylenders charging 5-10% monthly interest
- **Long Wait Times:** Our 7-day loan approval process meant partners missed urgent business opportunities
- **Complex Documentation:** Manual KYC and paperwork created friction, especially for partners with limited digital literacy
- **No Second Chances:** Partners who missed one payment were permanently blocked, even if they wanted to repay

### Constraints & Challenges

The team had to navigate significant constraints:

- **Technical Debt:** No LMS existed; Vetted and integrated a third-party Loan Management System 15K legacy loans without disrupting operations
- **Regulatory Compliance:** CKYC requirements, credit bureau reporting (CIBIL), RBI lending guidelines
- **Risk Management:** Balancing growth with portfolio health in an unsecured lending environment
- **Resource Constraints:** Limited engineering bandwidth meant prioritizing ruthlessly
- **Trust Deficit:** Partners were skeptical of digital lending after bad experiences elsewhere

---

## 💡 Solution

### Product Vision

The vision was to build a **behavioral lending platform** that used platform access as both an incentive and enforcement mechanism. Instead of traditional credit scoring alone, The goal was to create a system where:

1. **Access drives discipline:** Platform access tied to repayment behavior
2. **Friction breeds trust:** Simple, transparent processes build confidence
3. **Recovery is redemption:** Defaulters get paths back to good standing, not permanent blocks

The core value proposition: **Fast, fair credit that rewards good behavior and offers second chances.**

### Key Features

**1. Loan Management System (LMS) with Legacy Migration**

Led the migration of 15,000 legacy loans from Excel to a proper LMS while building new origination flows.

**The Challenge:**
- Couldn't stop lending during migration (business continuity requirement)
- Missing/incomplete repayment data in Excel created credit bureau compliance risk
- Operations team was manually tracking collections in spreadsheets (30+ hours/week wasted)
- No audit trail—disputes had no source of truth

**The Solution - Dual-Track Migration:**

*Track 1: New Loan Origination (Week 1-2)*
- Built LMS integration for all NEW loans (post-migration date)
- Every new disbursement went directly into LMS with proper data structure
- Enabled clean slate for automated processes (suspension, reporting, collections)

*Track 2: Legacy Data Backfill (Week 1-8)*
- Operations team manually entered 15K legacy loan details into LMS over 8 weeks
- Prioritized by risk: Active loans with pending repayments → Closed loans (for audit history)
- Validation checkpoints: Weekly data quality reviews (sample 100 loans, verify against Excel)
- Reconciliation: Cross-checked LMS totals vs Excel totals to ensure no data loss

**Execution Challenges:**

*Challenge 1 - Data Quality Issues:*
- **Problem:** Excel data had inconsistencies—missing repayment dates, unclear partner IDs, incomplete KYC
- **Fix:** Built data cleaning scripts to standardize formats before LMS import
- **Manual intervention:** Ops team called 200+ partners to verify missing KYC/repayment info

*Challenge 2 - Cutover Date Confusion:*
- **Problem:** Week 3—ops team accidentally entered some new loans in Excel (old habit) instead of LMS
- **Fix:** Hard cutover—disabled Excel sheet write access, forced all inputs through LMS only
- **Cleanup:** Manually migrated those ~50 loans from Excel to LMS post-facto

*Challenge 3 - Credit Bureau Reporting Gap:*
- **Problem:** 2-month migration window = reporting lag to CIBIL (compliance risk)
- **Fix:** Batched bureau reporting—once legacy data backfill completed, submitted bulk historical updates to CIBIL
- **Validation:** CIBIL accepted bulk upload, no compliance penalties incurred

**The Impact:**
- Created single source of truth (no more Excel reconciliation hell)
- Enabled automated reporting (credit bureau, finance, ops dashboards)
- Eliminated operational chaos (30+ hours/week recovered)
- Zero data loss during migration (verified via reconciliation checks)
- Foundation for scaling to 4K loans/month (impossible with Excel)

**2. One-Click Onboarding via CKYC Integration**

I integrated Central KYC (CKYC) through our Lending Service Provider (LSP) to eliminate manual documentation.

- **What it does:** Partners complete KYC in under 2 minutes using Aadhaar-based verification
- **Why it matters:** Reduced loan TAT from 7 days to 2 days—a 71% reduction
- **How it works:** Fetch verified identity data from CKYC registry, auto-populate loan application, instant approval for qualified partners

**3. Automated Suspension Engine (Behavioral Design)**

This was my most impactful innovation—tying platform access directly to repayment discipline.

- **What it does:** Automatically suspends platform access for partners who miss repayments; restores access upon payment
- **Why it matters:** Drove repayment rate from 73% to 90% (7 DPD)—a 17-percentage-point improvement
- **How it works:** Daily job checks repayment status → triggers suspension API → partner sees clear messaging about why they're blocked and how to unlock

**4. Flexible Payment Option (FPO) - Recovery Innovation**

For suspended partners who couldn't pay full dues immediately, we designed a "pay to unlock" model.

- **What it does:** Partners can unlock 7-day platform access by paying ₹1,500, creating a repeatable recovery loop
- **Why it matters:** Used by 2,200+ partners (35% of defaulted NPAs, avg 4 unlock cycles each), recovering ₹2 Cr+ incrementally
- **The Insight:** Partners earning through the platform could repay better than partners blocked from earning—so we created controlled access windows

**Design Decisions & Rationale:**

*Why ₹1,500 specifically?*
- **Too low (₹500):** No intent signal—partners could game the system with minimal commitment
- **Too high (₹3,000+):** Unaffordable for partners in genuine distress, defeats the purpose of gradual recovery
- **₹1,500 sweet spot:** High enough to signal serious intent to repay, low enough to be achievable from 5-7 days of earnings
- **Validation:** Piloted with 500 partners first—35% participation rate validated the pricing

*Why 7-day unlock period?*
- **Too short (3 days):** Not enough earning time to clear meaningful additional dues
- **Too long (14+ days):** Partners disappear to competitors during long unlock periods, losing repayment momentum
- **7 days balance:** Partner can earn ₹3,000-5,000 in a week (based on average daily earnings), enough to make next payment and build confidence
- **Behavioral psychology:** Weekly cadence creates rhythm—partners planned repayments around weekly unlock cycles

**Execution & Iteration:**

*Phase 1 (Pilot - 500 partners):*
- Launched FPO to 500 suspended partners as test cohort
- Success criteria: >30% participation, <10% abuse (multiple unlocks without incremental repayment)
- Results: 35% participated, 8% showed gaming behavior (unlocking 3+ times without paying down principal)

*Phase 2 (Fix & Scale):*
- Identified abuse pattern: Some partners unlocking repeatedly without reducing total dues
- Fix implemented: Cap of 5 unlock cycles before permanent suspension (forced graduation)
- Messaging updated: Clear communication—"You have X unlocks remaining, use them to clear dues"
- Scaled to all 4,000+ suspended partners after validation

*What Broke:*
- **Week 1 issue:** Partners confused about what ₹1,500 applied to (unlock fee vs loan principal)
- **Fix:** Updated in-app messaging to show: "Pay ₹1,500 → Unlocks platform + Applied to your loan dues"
- **Week 3 issue:** Some partners hit 5-unlock cap and complained they were "trying to repay"
- **Fix:** Built appeals flow where ops team could grant extensions for genuine cases with proof of repayment effort

**5. Weekly EWI (Equal Weekly Installments) Structure**

Shifted from monthly EMI to weekly installment structure to match partner cash flow patterns.

- **What it does:** Partners repay loans in weekly installments instead of monthly lump sums
- **Why it matters:** Reduced payment shock, improved repayment consistency for partners who earn daily
- **The Insight:** Driver-partners live paycheck-to-paycheck with daily/weekly earnings—monthly EMI forces them to hold cash for 30 days, increasing temptation to default

**Why Weekly Over Monthly:**
- **Partner cash flow:** Drivers earn ₹800-1,200 daily → Weekly repayment of ₹1,500-2,000 is manageable from 5-7 days of earnings
- **Monthly lump sum:** ₹6,000-8,000 payment requires saving for 30 days → High default risk when unexpected expenses arise
- **Psychological benefit:** Smaller, frequent payments feel less burdensome than large monthly bills
- **Platform leverage:** Weekly check-ins keep partners engaged, easier to catch delinquency early

**Execution Details (The "How"):**

*Technical Implementation:*
1. **LMS Configuration Changes:**
   - Updated repayment_frequency parameter from "MONTHLY" to "WEEKLY" in loan product definitions
   - Modified repayment schedule generation logic to calculate weekly installment amounts
   - Adjusted grace period rules (7 days for monthly → 2 days for weekly to maintain same relative buffer)

2. **API & System Changes:**
   - Updated disbursement service to generate weekly repayment schedules on loan creation
   - Modified payment collection logic to handle weekly due dates (vs monthly)
   - Built new reminder system—SMS sent 2 days before weekly due date (vs 5 days for monthly)
   - Updated suspension engine to trigger after 2 missed weekly installments (equivalent to monthly cadence)

3. **Partner Communication:**
   - In-app messaging explaining weekly structure: "Pay ₹1,800 every Monday vs ₹7,200 once a month"
   - SMS templates updated for weekly repayment reminders
   - Educational content on landing page showing cash flow benefits

**Rollout & Challenges:**

*Timeline:*
- **Planned:** 2 weeks for LMS config + API changes
- **Actual:** 6 weeks end-to-end (NBFC integration delays)

*Key Challenges:*

1. **NBFC Partner Validation (Week 1-3):**
   - **Problem:** NBFC's systems were configured for monthly reporting—needed 2 weeks to validate weekly cadence in their compliance systems
   - **Workaround:** Launched weekly EWI for NEW loans only, kept existing loans on monthly schedule
   - **Resolution:** NBFC validated weekly structure, cleared for production rollout

2. **Edge Case - Existing Loan Migration (Week 4):**
   - **Problem:** 2,000+ existing monthly loans—migrate to weekly or grandfather them?
   - **Decision:** Grandfather existing loans, offer opt-in to weekly for partners struggling with monthly
   - **Result:** 400 partners opted in, 1,600 stayed on monthly (preference respected)

3. **Repayment Tracking Complexity:**
   - **Problem:** Weekly installments = 4x more transactions to track vs monthly
   - **Fix:** Automated reconciliation dashboard showing weekly payment status, ops team no longer manually tracking
   - **Learning:** Automation infrastructure must scale BEFORE adding frequency

**Results from Weekly Structure:**
- Improved on-time repayment rate by 8% (weekly vs monthly cohorts)
- Reduced avg days past due from 12 → 7 days (faster delinquency detection)
- Partner feedback: "Weekly is easier to manage" (78% preference in post-launch survey)

**6. Self-Serve Lending Landing Page**

I replaced high-touch sales with a self-serve funnel featuring educational videos and simplified applications.

- **What it does:** Partners learn about loans, check eligibility, and apply—all without talking to a sales agent
- **Why it matters:** Increased loan leads by 17% while reducing sales team from 80 to 50 agents (37.5% reduction)
- **Strategic shift:** Moved from push-based sales to pull-based demand generation, improving both conversion and unit economics

### Architecture & Technical Approach

**Credit Assessment:**
- Combined traditional credit bureau checks (CIBIL) with Porter platform behavior (delivery completion rate, earnings consistency, tenure)
- Weighted platform data heavily since many partners were "credit invisible" to bureaus
- Built risk tiers enabling different loan amounts and terms based on trust level

**Critical Integrations:**
- CKYC via LSP for identity verification
- Credit bureau APIs for reporting and scoring
- Payment gateway for automated collections and disbursements
- Porter's core platform for suspension/activation triggers

**Automation Philosophy:**
I automated high-volume, low-risk decisions (eligibility, disbursement, suspension) while keeping human review for edge cases and appeals. This balance maintained quality while achieving scale.


---

## 📊 Impact

### Quantitative Metrics

**Adoption & Growth**
- **10x growth:** 400 → 4,000 loans/month (April 2022 - Present)
- **₹100 Cr+ disbursed** in total credit to driver-partners
- **2-day average TAT** (down from 7 days)
- Enabled thousands of partners to access working capital for the first time

**Portfolio Health & Risk**
- **90% repayment rate** at 7 DPD (up from 73%)—a 23% relative improvement
- **₹2 Cr+ recovered** through Flexible Payment Option from 2,200+ partners
- **35% of defaulted NPAs** actively using FPO to repay incrementally
- Reduced write-offs and improved overall portfolio quality

**Unit Economics & Efficiency**
- **40% CAC reduction:** ₹625 → ₹375 per loan
- **37.5% sales team reduction:** 80 → 50 agents while scaling 10x
- **71% faster processing:** 7 days → 2 days TAT
- Self-serve funnel drove 17% increase in qualified leads

**Operational Excellence**
- Migrated 15,000 legacy loans from Excel to LMS with zero data loss
- Eliminated credit bureau compliance risk through proper reporting
- Automated 90%+ of loan decisions, suspensions, and activations

### Qualitative Impact

**Business Transformation**
- Turned lending from a cost center to a sustainable, scalable revenue driver
- Created competitive moat—Porter became known as the platform that "supports partners" through credit access
- Enabled partnerships with financial institutions who trust our underwriting and portfolio management

**Driver-Partner Empowerment**
- Gave gig workers access to formal credit, often their first experience with institutional lending
- Built credit histories for partners who were previously "credit invisible"
- Created pathway for partners to improve their standing through good behavior (FPO redemption loop)

**Product Influence**
- Suspension engine approach inspired similar behavioral mechanics in other Porter verticals
- Demonstrated power of using platform access as leverage in marketplace dynamics
- Proved that empathy-driven product design (second chances via FPO) can coexist with strong unit economics

---

## 🎓 Learnings

### What Worked Well

**1. Behavioral Design Over Brute Force**
- **What I did:** Instead of aggressive collections or legal action, I used platform access suspension as a nudge
- **Why it worked:** Partners valued platform access more than anything—it was their livelihood. Suspending access created immediate, strong motivation to repay
- **Results:** 73% → 90% repayment rate without antagonizing partners or incurring collections costs

**2. Build Redemption Loops, Not Dead Ends**
- **What I did:** Created Flexible Payment Option so defaulters could earn their way back to good standing
- **Why it worked:** Permanent blocks push partners to competitors and guarantee write-offs. FPO kept them engaged, earning, and repaying incrementally
- **Results:** 2,200+ partners actively repaying through FPO, ₹2 Cr+ recovered from what would have been full write-offs

**3. Self-Serve Beats High-Touch at Scale**
- **What I did:** Replaced 80-person sales team with educational landing page and automated flows
- **Why it worked:** Partners want speed and simplicity, not sales calls. Self-serve reduced friction, built trust, and improved economics
- **Results:** 17% more leads, 37.5% fewer agents, 40% lower CAC

**4. Platform Data > Traditional Credit Scores**
- **What I did:** Weighted Porter behavioral data (delivery consistency, tenure, earnings) alongside CIBIL scores
- **Why it worked:** Many partners were "credit invisible" but had strong platform behavior. Our data was more predictive for this segment
- **Results:** Approved partners traditional lenders rejected—while maintaining 90% repayment rate

**5. Migrate Without Disruption**
- **What I did:** Built dual-track system to launch LMS while backfilling 15K legacy loans over 2 months
- **Why it worked:** Couldn't pause lending for migration. Dual-track let us move fast without breaking existing operations
- **Results:** Zero disruption, clean migration, credit bureau compliance restored

### Challenges & How We Overcame Them

**1. Credit Bureau Risk from Legacy Loans**
- **The Problem:** 15,000 loans in Excel with incomplete repayment data, creating massive compliance risk with CIBIL/credit bureaus
- **How I Solved It:** Designed phased migration—onboarded new loans in LMS while ops team backfilled legacy data. Set up automated bureau reporting to prevent future gaps
- **Outcome:** Eliminated compliance risk, established clean reporting foundation for scale

**2. Balancing Growth vs. Risk**
- **The Problem:** Pressure to scale loans quickly vs. maintaining portfolio health (avoiding NPAs)
- **How I Solved It:** Focused on behavior-driven repayment (suspension engine) before scaling aggressively. Proved 90% repayment rate at smaller scale, then confidently scaled to 4K/month
- **Outcome:** Achieved both—10x growth AND improved portfolio health

**3. Partner Pushback on Suspensions**
- **The Problem:** Partners initially resented being locked out of the platform for missed payments
- **How I Solved It:** Clear, empathetic messaging explaining why suspension happened and exactly how to unlock. Introduced FPO as a middle path for those who couldn't pay full dues
- **Outcome:** Transformed suspensions from "punishment" to "motivation," maintaining partner trust while enforcing discipline

**4. Engineering Bandwidth Constraints**
- **The Problem:** Limited dev resources to build LMS, integrations, suspension engine, and landing page simultaneously
- **How I Solved It:** Ruthless prioritization—shipped LMS MVP first (migrate legacy loans), then CKYC integration (biggest TAT win), then suspension engine (biggest repayment impact)
- **Outcome:** Sequenced launches to maximize impact per engineering sprint

### Key Takeaways

- **Behavioral > Financial Incentives:** Platform access proved more motivating than interest rates or rewards. Use what users value most as your lever.

- **Second Chances Create Value:** FPO showed that "defaulters" aren't a monolith—some need flexibility to recover. Redemption loops recover money AND retain customers.

- **Self-Serve Scales, High-Touch Doesn't:** For transactional products like lending, invest in automated experiences, not sales headcount. Better economics, better UX.

- **Platform Data is Gold:** For gig/informal workers, behavioral data from your platform is more predictive than traditional credit scores. Use your unique data advantage.

- **Migration Strategy Matters:** You can't pause business to rebuild infrastructure. Design dual-track systems to ship new while fixing old.

- **Empathy + Discipline = Sustainable Growth:** You don't have to choose between being partner-friendly and running a healthy portfolio. Behavioral design lets you do both.

### What I'd Do Differently

**1. Validate Instant Disbursals with Data, Not Assumptions**

*What happened:*
- Leadership was adamant about instant disbursals (< 1 hour vs 2-day TAT)
- We built instant disbursement flow without experimentingto validate retention/conversion benefits
- **Honest reflection:** We don't actually know if instant disbursals drove measurably better outcomes vs 2-day TAT

*What I'd do differently:*
- Run A/B test: Instant (< 1hr) vs Fast (same-day) vs Standard (2-day) disbursement
- Measure: Repeat borrowing rate, partner retention, NPS by cohort
- **Why it matters:** Instant disbursals add operational complexity—should validate the juice is worth the squeeze
- **Constraint acknowledged:** Sometimes leadership-driven decisions happen, but push for data validation where possible

**2. Earlier Focus on Collections UX**

*What happened:*
- Relied heavily on suspension as primary enforcement mechanism
- Built gentler nudges (in-app reminders, payment flows) as afterthoughts

*What I'd do differently:*
- Design full collections UX upfront: Pre-due reminders → Due-date nudges → Post-due warnings → Suspension (last resort)
- Hypothesis: Better UX prevents delinquencies before suspension needed
- Could have reduced suspension rate (and partner frustration) with proactive nudging

**3. More Granular Risk Segmentation from Day 1**

*What happened:*
- Initial risk tiers were broad (Low/Medium/High risk)
- All "Medium risk" partners got same loan amount/rate despite different behavior profiles

*What I'd do differently:*
- Finer segmentation based on: Earnings volatility, seasonality, tenure, delivery consistency
- Top-tier partners could get better rates (reward loyalty), higher-risk partners get smaller loans (protect downside)
- **Learning:** Risk segmentation compounds—small improvements in underwriting = big portfolio health gains at scale

**4. Structured Experimentation Cadence**

*What happened:*
- Weekly EWI, FPO unlock amount (₹1,500), unlock period (7 days) were designed based on intuition + light validation
- Could have tested more variations systematically

*What I'd do differently:*
- Establish experimentation framework: Every major product decision = hypothesis → test → validate → scale
- Test FPO unlock amounts (₹1,000 vs ₹1,500 vs ₹2,000), unlock periods (5-day vs 7-day vs 10-day)
- Test weekly EWI vs bi-weekly to find optimal repayment cadence
- **Why:** Marginal gains from experimentation compound—5% better FPO conversion = ₹10L more recovery annually

---


---

---

← [Back to Porter Case Studies](https://github.com/ProductAlchemist/porter-case-studies)
---

