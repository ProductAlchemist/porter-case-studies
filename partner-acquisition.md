# Partner Acquisition & Growth

## Overview

I built Porter's partner acquisition and growth engine, launching digital marketing channels and OEM partnerships that diversified supply beyond field sales. I established a digital acquisition channel contributing 20% of new partners and 10% of activations, built OEM partnerships delivering 5% of acquisitions, improved conversion rates from 40% to 52%, and implemented basic fraud controls (blocking repeat offenders) as table stakes.

**Timeline:** October 2023 - February 2024
**Role:** Product Manager
**Team:** Cross-functional team including Engineering, Design, Data Science, Growth, and Risk/Compliance

**Note:** This was part of a larger supply acquisition initiative with multiple discovery phases. Due to changing organizational priorities, some planned features (advanced ML-based fraud scoring, expanded OEM partnerships) were deprioritized mid-stream. This case study reflects the reality of product work—delivering measurable impact within shifting constraints while building foundations for future expansion.

---

## 📋 Problem

### Business Challenge

Porter faced a critical growth challenge: **scale partner supply to meet seasonal demand spikes** while ensuring basic trust and compliance as table stakes.

**Primary Growth Problem:**
- **Seasonal Demand Spikes:** Customer demand surged during festivals and peak seasons, but we didn't have enough partners to fulfill orders
- **Single Acquisition Channel:** 100% dependent on field sales—slow, expensive, and couldn't scale fast enough to meet demand
- **No Digital Funnel:** No way to acquire partners through digital channels (paid ads, search, social media)
- **OEM Opportunity Untapped:** Vehicle manufacturers wanted to help drivers start businesses, but no B2B pipeline existed
- **Conversion Leaks:** Poor onboarding experience with 40% CTR on key actions

**Secondary: Basic Trust & Compliance (Table Stakes):**
- **Repeat Offenders:** Blocked partners rejoining with new documents—no systematic way to catch them
- **Low Vehicle Compliance:** Only 50% of partners had valid, verified vehicle documents (RC verification)
- **Fraud Costs:** Material losses from fraudulent activities, needed basic controls

**The Core Challenge:**
- **How do you diversify and scale partner acquisition beyond field sales while maintaining basic platform integrity?**

### Growth Gaps Identified

Through market analysis and data review, I identified critical growth opportunities:

**1. Digital Marketing Channel (Untapped)**
- **Opportunity:** Porter had zero digital partner acquisition. Competitors were using Google Ads, Facebook, Instagram
- **Gap:** No attribution infrastructure, no paid campaigns, no digital funnel
- **Potential:** Industry benchmarks showed 15-25% of partner acquisition could come from digital

**2. OEM Partnerships (Win-Win Model)**
- **Opportunity:** Vehicle manufacturers wanted to help new vehicle buyers start earning
- **Gap:** No B2B sales motion, no bulk onboarding flows, no dealer network integration
- **Potential:** Lower CAC than paid ads, higher quality partners (vehicle owners vs renters)

**3. Conversion Optimization (Quick Wins)**
- **Opportunity:** Onboarding funnel had major drop-off points
- **Gap:** No in-app nudges, manual lead assignment, complex document upload
- **Potential:** 10-20% conversion improvement through basic optimization

**4. Basic Fraud Controls (Necessary Foundation)**
- **Opportunity:** Block obvious repeat offenders before growing supply
- **Gap:** No cross-document blacklist, manual document verification
- **Need:** Table stakes fraud prevention to protect growth investments

### User Experience Considerations

**For New Partners:**
- Fast, frictionless onboarding to maximize conversion
- Clear value proposition and earning potential
- Transparent verification process

**For Growth Teams:**
- Measurable attribution for marketing spend
- Scalable channels that could flex with demand
- Data-driven optimization capabilities

**For OEM Partners:**
- Simple bulk onboarding for dealer networks
- Reporting on partner activation and earnings
- Co-branded materials and incentives

---

## 💡 Solution

### Product Vision

I envisioned a **diversified partner acquisition engine** where:

1. **Multiple channels feed sustainable growth:** Digital marketing, OEM partnerships, and field sales work together
2. **Attribution drives accountability:** Every marketing dollar tied to partner activation and retention
3. **Conversion is continuously optimized:** Data-driven improvements to onboarding funnel
4. **Basic fraud controls protect investments:** Simple, effective measures prevent obvious bad actors

**Core Philosophy:** Growth requires diversification. You can't scale a business on a single acquisition channel.

### Multi-Channel Growth Strategy

I built three parallel growth tracks with basic fraud controls:

**Primary Focus: Growth Channels**
1. Launch digital marketing acquisition with proper attribution
2. Build OEM B2B partnerships for sustainable pipeline
3. Optimize conversion through in-app improvements

**Supporting Infrastructure: Basic Fraud Controls**
4. Simple blacklist to block repeat offenders
5. Automated RC verification for compliance

### System Architecture

**Growth Infrastructure (Primary Focus):**

**1. Digital Attribution & Tracking**
- Integrated Adjust (Mobile Measurement Partner) for partner-side attribution
- Tracked campaign performance: installs → signups → document submission → activation
- Enabled paid acquisition via Google Ads, Facebook, Instagram
- Full funnel analytics from ad click to first order
- Performance dashboards for growth team

**2. OEM Partnership Pipeline**
- B2B onboarding flows for manufacturers (Hero, Bajaj, etc.)
- Manufacturer-funded incentive disbursement
- Bulk partner onboarding via dealer networks
- Custom reporting for OEM partners
- Win-win-win model: OEMs get vehicle usage, drivers get income, Porter gets supply

**3. Conversion Optimization**
- Targeted in-app banners based on onboarding stage
- Automated lead assignment to onboarding agents
- Streamlined document upload flows
- Real-time progress tracking for partners
- A/B testing infrastructure for continuous improvement

**Basic Fraud Controls (Table Stakes):**

**4. Simple Blacklist Registry**
- Multi-document blocking (PAN, Aadhaar, DL, RC)
- Cross-reference checks to catch repeat offenders
- Prevent blocked partners from rejoining with new documents

**5. Vahan API Integration**
- Real-time RC verification via government database
- Automated compliance checking
- Faster than manual verification

**Integration Points:**
- All channels (digital, OEM, field) feed into unified onboarding flow
- Attribution system tracks performance across channels
- Fraud checks integrated seamlessly—partners don't see them unless flagged
- Ops dashboard shows unified view of all acquisition channels

### Key Features

**GROWTH TRACK (PRIMARY):**

**1. Digital Marketing Acquisition Channel (Adjust Integration)**

Launched Porter's first digital acquisition channel, enabling paid marketing at scale.

- **What it does:** Tracks partner acquisition from ad click → install → signup → activation, enabling performance marketing
- **Why it matters:** Unlocked scalable, measurable acquisition beyond field sales. Created ability to flex spend based on seasonal demand
- **How it works:**
  - Integrated Adjust SDK in partner app
  - Set up campaign tracking for Google Ads, Facebook, Instagram
  - Built attribution funnel: Click → Install → Signup → Document Upload → Activation → First Order
  - Created performance dashboards for growth team to optimize campaigns
  - Enabled real-time spend adjustments based on CAC vs LTV
- **Impact:** Scaled from 0% → 20% of total partner supply, 10% of activations

**2. OEM Partnerships (B2B Supply Pipeline)**

Established partnerships with vehicle manufacturers to create sustainable acquisition model.

- **What it does:** Manufacturers fund onboarding incentives for drivers buying their vehicles; Porter gets vetted partners at lower CAC
- **Why it matters:** Creates sustainable B2B pipeline with higher-quality partners (vehicle owners vs. renters), significantly lower CAC than paid ads
- **The Model:**
  - OEM pays ₹X incentive per partner activated
  - Drivers learn about Porter at vehicle purchase (dealer touchpoint)
  - Porter provides bulk onboarding via dealer network
  - OEM gets value (vehicle usage), Porter gets supply, driver gets income opportunity
- **Technical Enablers:**
  - Built B2B onboarding flows for bulk partner upload
  - Custom reporting dashboards for OEM partners
  - Co-branded materials and in-dealer marketing
- **Impact:** 5% of total acquisitions, 30% lower CAC than paid ads, higher retention

**3. Conversion Optimization (In-App & Process)**

Improved conversion rates through targeted nudges and process improvements.

- **What it does:** Shows contextual banners, automates lead assignment, reduces friction in document upload
- **Key Changes:**
  - Targeted in-app banners based on onboarding stage (e.g., "Upload RC to start earning!")
  - Automated lead assignment to onboarding agents (reduced wait time)
  - Simplified document upload (one-tap camera vs. gallery upload)
  - Real-time progress tracker ("2/5 steps complete")
  - A/B testing framework for continuous optimization
- **Impact:** CTR improved 40% → 52%, time-to-onboarding reduced by 15%, signup-to-activation conversion up 12%

**BASIC FRAUD CONTROLS (TABLE STAKES):**

**4. Simple Blacklist Registry (Block Repeat Offenders)**

Basic fraud prevention to catch repeat offenders.

- **What it does:** Blocks previously-blocked partners from rejoining with new documents
- **Why it matters:** Prevents obvious repeat offenders, protects growth investments
- **How it works:**
  - When partner is blocked, all their documents (PAN, Aadhaar, DL, RC) added to blacklist
  - At onboarding, check new documents against blacklist
  - Cross-reference: If one document is blacklisted, flag the profile for review
- **Note:** This is table stakes fraud prevention, not advanced ML or behavioral analysis—just blocking known bad actors
- **Impact:** 90% reduction in monthly fraud attempts by repeat offenders

**5. Vahan API Integration (Automated RC Verification)**

Basic vehicle verification for compliance.

- **What it does:** Verifies vehicle registration via government database instead of manual checks
- **Why it matters:** Faster verification, better compliance, reduces manual work
- **How it works:**
  - Partner uploads RC document
  - OCR extracts registration number
  - API call to Vahan database for instant validation
  - Auto-approve if match; flag for manual review if mismatch
- **Impact:** Improved compliance from 50% → 78%, reduced manual verification time by 80%

### Technical & Product Decisions

**Attribution Infrastructure (Adjust vs. In-House):**
- **Decision:** Use third-party MMP (Adjust) instead of building in-house
- **Rationale:** Industry-standard attribution prevents gaming by agencies, faster to market
- **Trade-off:** Vendor cost, but worth it for trusted measurement and speed

**Multi-Channel Attribution (Not Just Last-Touch):**
- **Decision:** Track full funnel from ad click to activation, not just installs
- **Rationale:** Optimize for quality (activations) not just quantity (installs)
- **Implementation:** Built cohort analysis showing which channels drive long-term active partners

**OEM Partnerships (B2B2C Model):**
- **Decision:** Pursue manufacturer partnerships vs. only direct-to-consumer acquisition
- **Rationale:** Lower CAC, higher quality partners, sustainable pipeline
- **Enabler:** Built custom bulk onboarding flows for dealer-driven signups

**Conversion-First Approach:**
- **Decision:** Optimize for conversion rate, not just acquisition volume
- **Rationale:** Better to activate 50% of 1000 partners than 20% of 2000 partners
- **Implementation:** A/B testing on banners, document flows, lead assignment

**Basic Fraud Controls (Not Over-Engineering):**
- **Decision:** Build simple blacklist and RC verification, skip advanced ML/behavioral analysis
- **Rationale:** 80/20 rule—simple controls catch most fraud, can add sophistication later
- **Trade-off:** Won't catch sophisticated fraud, but sufficient for current scale

### Implementation Strategy

**Phase 1: Digital Attribution Foundation (Month 1-2)**
- Integrated Adjust SDK for partner app
- Set up first campaigns (Google Ads, Facebook)
- Built attribution funnel and dashboards
- Started with small test budget (₹5L/month)
- **Rationale:** Prove digital acquisition works before scaling spend

**Phase 2: Scale Digital Channel (Month 3-4)**
- Optimized campaigns based on activation rate, not just installs
- Scaled spend based on CAC vs. LTV
- Expanded to Instagram, search ads
- Grew to 20% of total supply

**Phase 3: OEM Partnerships (Month 4-6)**
- Pitched Hero, Bajaj, TVS on partnership model
- Built B2B onboarding flows
- Piloted with 2 OEMs, scaled to 5
- Reached 5% of acquisitions

**Phase 4: Conversion Optimization (Month 5-7)**
- Analyzed drop-off points in onboarding funnel
- Launched in-app banners (40% → 52% CTR)
- Automated lead assignment
- Reduced time-to-onboarding by 15%

**Phase 5: Basic Fraud Controls (Parallel Track)**
- Built simple blacklist registry
- Integrated Vahan API for RC verification
- Just enough to prevent repeat offenders
- Not the primary focus—table stakes infrastructure

**Testing & Monitoring:**
- **A/B Testing:** All in-app changes tested before full rollout
- **Attribution Validation:** Cross-checked Adjust data with internal analytics
- **Channel Performance:** Weekly reviews of CAC, activation rate, retention by channel
- **Fraud Monitoring:** Basic dashboards to catch repeat offenders

---

## 📊 Impact

### Quantitative Metrics

**GROWTH ACHIEVEMENTS (PRIMARY IMPACT)**

**Digital Acquisition Channel:**
- **20% of total partner supply** via digital marketing (from 0%)
- **10% of activations** (partners completing first order)
- **Scalable spend:** Could increase/decrease budget based on seasonal demand
- Unlocked new partner demographics (younger, tech-savvy drivers)
- Proved Porter could acquire digitally, enabling future expansion

**OEM Partnerships:**
- **5% of total acquisitions** via manufacturer partnerships
- **30% lower CAC** than digital ads
- **Higher retention:** Vehicle owners vs. renters = better long-term engagement
- 5 OEM partnerships established (Hero, Bajaj, TVS, etc.)
- Created sustainable, scalable B2B pipeline

**Conversion Improvements:**
- **CTR: 40% → 52%** on in-app onboarding banners (30% relative improvement)
- **Time-to-onboarding reduced by 15%** through automated lead assignment
- **Signup → activation conversion improved by 12%**
- Compounding effect: Better conversion × more channels = significant growth

**BASIC FRAUD CONTROLS (TABLE STAKES)**

**Fraud Prevention:**
- **90% reduction in monthly fraud attempts** by repeat offenders (simple blacklist)
- **₹50L+ in fraud losses blocked** annually through basic controls
- Caught repeat offenders before they could place fraudulent orders
- Good enough for current scale—not advanced ML, just blocking known bad actors

**Compliance:**
- **Vehicle compliance: 50% → 78%** (automated RC verification via Vahan)
- **80% reduction** in manual RC verification time
- **99%+ legitimate partner approval rate** (low false positive rate)

**Channel Diversification:**
- **From 1 channel → 3 channels** (field sales, digital, OEM)
- **Risk reduction:** No longer dependent on single acquisition source
- **Flexibility:** Can adjust channel mix based on CAC, seasonality, market conditions

### Qualitative Impact

**Business Transformation**

**Growth Enablement (Primary Achievement):**
- **Unlocked digital marketing** as scalable acquisition channel—no longer 100% dependent on field sales
- **Created B2B partnerships** that provide sustainable, high-quality supply pipeline
- **Proved multi-channel model:** Porter can acquire partners through digital, OEM, and field sales
- **Enabled seasonal flexibility:** Can scale up digital spend during peak demand periods

**Strategic Advantage:**
- **Channel diversification** became competitive moat—competitors often stuck on single channel
- **OEM partnerships** created unique supply pipeline that competitors couldn't easily replicate
- **Attribution infrastructure** enabled data-driven marketing optimization
- **Foundation for expansion:** Multi-channel playbook ready for new cities/markets

**Team & Culture:**
- **Established playbook** for launching new acquisition channels
- **Data-driven mindset:** Proved importance of attribution and funnel optimization
- **Cross-functional collaboration:** Growth, engineering, design, risk working together
- **B2B sales capability:** Showed Porter could do enterprise partnerships, not just B2C

**Basic Trust (Table Stakes):**
- Simple fraud controls prevented obvious repeat offenders
- RC verification improved compliance without over-engineering
- Good enough for current scale, foundation for future sophistication

---

## 🎓 Learnings

### What Worked Well

**1. Digital Attribution Infrastructure (Adjust)**
- **What I did:** Integrated third-party attribution platform instead of building in-house
- **Why it worked:** Faster to market, industry-standard, prevented gaming by agencies
- **Impact:** Enabled 20% of supply via digital in 6 months vs. 12+ months to build in-house

**2. OEM Partnerships (B2B2C Model)**
- **What I did:** Built partnerships with vehicle manufacturers to create win-win acquisition model
- **Why it worked:** Lower CAC than ads, higher quality partners, sustainable pipeline
- **Impact:** 5% of acquisitions at 30% lower CAC, became repeatable B2B playbook

**3. Optimize for Activation, Not Just Installs**
- **What I did:** Shifted digital campaigns from install volume to activation quality
- **Why it worked:** Better to activate 50% of 1000 partners than 20% of 2000 partners
- **Impact:** Improved activation rate by 18% by reallocating budget to high-quality channels

**4. Conversion Optimization (Quick Wins)**
- **What I did:** A/B tested in-app banners, automated lead assignment, simplified uploads
- **Why it worked:** Small friction reductions compound across funnel
- **Impact:** 40% → 52% CTR, 15% faster onboarding, 12% better signup-to-activation

**5. Basic Fraud Controls (Not Over-Engineering)**
- **What I did:** Built simple blacklist and RC verification, skipped advanced ML
- **Why it worked:** 80/20 rule—simple controls catch most fraud, faster to ship
- **Impact:** 90% fraud reduction without months of ML model development

### Challenges & How We Overcame Them

**1. Attribution Data Quality (Digital Campaigns)**
- **The Problem:** Initial campaigns showed high installs but low activations—were we acquiring low-quality partners?
- **How I Solved It:**
  - Optimized campaigns for activation, not just install (shifted budget to high-performing channels)
  - Built cohort analysis: Which campaigns drive long-term active partners?
  - Added fraud checks to exclude bad actors from performance metrics
- **Outcome:** Improved activation rate by 18% through channel reallocation

**2. OEM Sales Cycle (Slow B2B Deals)**
- **The Problem:** OEM partnerships took 3-4 months to close (procurement, legal, onboarding setup)
- **How I Solved It:**
  - Started with 2 pilot OEMs willing to move fast
  - Used pilot results to sell other manufacturers ("Hero sees X activations")
  - Built reusable B2B onboarding templates to reduce setup time
- **Outcome:** Closed 5 OEM partnerships in 6 months after slow start

**3. Conversion Optimization (Too Many Ideas)**
- **The Problem:** Teams wanted to test dozens of funnel improvements—couldn't ship all at once
- **How I Solved It:**
  - Prioritized based on impact × effort (focused on high-leverage changes)
  - Ran A/B tests sequentially to isolate impact
  - Shipped quick wins first (banners, lead assignment) before complex changes
- **Outcome:** Delivered 30% CTR improvement in 2 months vs. 6-month roadmap

**4. Balancing Growth vs. Fraud Prevention**
- **The Problem:** Growth teams wanted fast onboarding; risk teams wanted thorough verification
- **How I Solved It:**
  - Built simple, automated fraud checks (blacklist, Vahan) that didn't slow onboarding
  - Showed growth team that basic fraud controls protect their marketing investments
  - Set shared metrics: optimize for activation rate AND fraud rate, not one or the other
- **Outcome:** Both teams aligned on "growth with basic controls" approach

### Key Takeaways

- **Multi-Channel > Single Channel:** Diversification reduces risk and enables flexibility. Don't put all acquisition eggs in one basket.

- **Attribution Drives Accountability:** Without trusted attribution (Adjust), growth spend becomes a black box. Third-party measurement prevents gaming.

- **Optimize for Quality, Not Just Quantity:** Activation rate matters more than install volume. Better to grow slower with higher-quality partners.

- **B2B Partnerships Beat Pure B2C:** OEM partnerships provided sustainable, high-quality supply at lower CAC. B2B2C model scales better than pure consumer acquisition.

- **Basic Fraud Controls Are Table Stakes:** Simple blacklist and RC verification caught 90% of fraud. Don't over-engineer—ship basics fast, add sophistication later.

- **Conversion Improvements Compound:** Small friction reductions (better banners, faster lead assignment) add up across the funnel to significant lift.

### What I'd Do Differently

**Earlier Focus on Activation Quality**
- Spent first 2 months optimizing for install volume before realizing activation rate mattered more. Should have optimized for quality from day 1.

**Parallel OEM Outreach**
- Approached OEMs sequentially (one at a time) due to caution. Should have pitched 5-10 simultaneously to account for slow sales cycles.

**A/B Testing Infrastructure Earlier**
- Built testing framework in month 5. Should have launched in month 1 to enable faster iteration on conversion improvements.

**More Regional Language Content**
- Digital campaigns were mostly English/Hindi. Should have launched Tamil, Telugu, Kannada campaigns earlier to reach underserved segments.

---

## 🔮 Future Roadmap

**Planned Growth Enhancements:**

**Channel Expansion:**
- **Referral Program:** Partner-to-partner referrals with incentives (lower CAC than paid ads)
- **Regional Language Campaigns:** Digital ads in Tamil, Telugu, Kannada to reach underserved segments
- **Dealer Network Scaling:** Expand OEM partnerships to 10+ manufacturers
- **Influencer Partnerships:** Local influencers in gig economy space

**Conversion Optimization:**
- **Smart Lead Routing:** Assign partners to best-fit onboarding agents based on language, location
- **Document Auto-Fill:** OCR pre-fill forms from uploaded documents (reduce typing)
- **Video KYC:** Live video verification as alternative to in-person verification
- **Gamification:** Progress bars, achievement badges to increase completion rates

**Advanced Attribution:**
- **Multi-Touch Attribution:** Credit all touchpoints in partner journey, not just last click
- **Cohort LTV Analysis:** Track long-term partner value by acquisition channel
- **Predictive CAC Models:** Forecast optimal spend allocation across channels

**Basic Fraud Evolution (If Needed):**
- **Behavioral Signals:** Add simple checks for suspicious order patterns (only if fraud increases)
- **Network Detection:** Flag partners operating from same location/device (table stakes)
- Would only invest in advanced ML if fraud becomes material problem—not a priority now

---

## 🔗 Related Work

- [Lending Platform Case Study](./lending-platform.md) - Another growth initiative with trust as necessary foundation
- [Taxation Infrastructure Case Study](./taxation-system.md) - Platform thinking and automation

---

*This case study demonstrates how to build multi-channel partner acquisition, establish B2B partnerships, optimize conversion funnels, and implement basic fraud controls as table stakes—with growth as the primary story.*
