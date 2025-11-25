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

- **The Challenge:** We couldn't stop lending during migration, and missing repayment data created credit bureau risk
- **The Solution:** Built a dual-track system that onboarded new loans in LMS while backfilling legacy data over 2 months
- **The Impact:** Created single source of truth, enabled automated reporting, eliminated operational chaos

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

For suspended partners who couldn't pay full dues immediately, We designed a "pay to unlock" model.

- **What it does:** Partners can unlock 7-day platform access by paying ₹500, creating a repeatable recovery loop
- **Why it matters:** Used by 2,200+ partners (35% of defaulted NPAs), recovering ₹2 Cr+ incrementally
- **The Insight:** Partners earning through the platform could repay better than partners blocked from earning—so we created controlled access windows

**5. Self-Serve Lending Landing Page**

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

**Earlier Focus on Collections UX**
- I should have built better in-app reminders and payment flows earlier. We relied too much on suspension as the primary nudge, when gentler prompts could have prevented some delinquencies.

**Faster Experimentation with Loan Products**
- We stuck with standard 30-day loans for too long. Wish I'd tested weekly micro-loans or income-linked repayments earlier to see if different structures improved outcomes.

**More Granular Risk Segmentation**
- Initial risk tiers were too broad. Finer segmentation (based on earnings volatility, seasonality, etc.) could have let us offer better rates to top-tier partners while protecting downside risk.

---


---

---

← [Back to Porter Case Studies](https://github.com/ProductAlchemist/porter-case-studies)
---

