# Partner Acquisition & Growth


## 📋 Problem

### Business Challenge

Porter faced a critical growth challenge: **scale partner supply to meet seasonal demand spikes** while ensuring basic trust and compliance as table stakes.

**Primary Growth Problem:**
- **Seasonal Demand Spikes:** Customer demand surged during festivals and peak seasons, but we didn't have enough partners to fulfill orders
- **Single Acquisition Channel:** 100% dependent on field sales—slow, expensive, and couldn't scale fast enough to meet demand
- **No Digital Attribution:** No way to track or optimize digital acquisition channels
- **OEM Opportunity Untapped:** Vehicle manufacturers wanted to help drivers start businesses, but no B2B pipeline existed
- **Conversion Leaks:** Poor onboarding experience with 40% CTR on key actions

**Secondary: Basic Trust & Compliance (Basic Controls):**
- **Repeat Offenders:** Blocked partners rejoining with new documents—no systematic way to catch them
- **Low Vehicle Compliance:** Only 50% of partners had valid, verified vehicle documents (RC verification)
- **Fraud Costs:** Material losses from fraudulent activities, needed basic controls

**The Core Challenge:**
- **How do you diversify and scale partner acquisition beyond field sales while maintaining basic platform integrity?**

### Growth Gaps Identified

Through market analysis and data review, Identified critical growth opportunities:

**1. Digital Marketing Channel (Untapped)**
- **Opportunity:** Porter had zero digital partner acquisition infrastructure
- **Gap:** No attribution tracking, no performance measurement
- **Potential:** Industry benchmarks showed 15-25% of partner acquisition could come from digital

**2. OEM Partnerships (Win-Win Model)**
- **Opportunity:** Vehicle manufacturers wanted to help new vehicle buyers start earning
- **Gap:** No B2B sales motion, no bulk onboarding flows
- **Potential:** Lower CAC than paid ads, higher quality partners (vehicle owners vs renters)

**3. Conversion Optimization (Quick Wins)**
- **Opportunity:** Onboarding funnel had major drop-off points
- **Gap:** No in-app nudges, manual lead assignment
- **Potential:** 10-20% conversion improvement through basic optimization

**4. Basic Fraud Controls (Necessary Foundation)**
- **Opportunity:** Block obvious repeat offenders before growing supply
- **Gap:** No cross-document blacklist, manual document verification
- **Need:** Table stakes fraud prevention to protect growth investments

---

## 💡 Solution

### Product Vision

The vision was a **diversified partner acquisition engine** where:

1. **Multiple channels feed sustainable growth:** Digital marketing, OEM partnerships, and field sales work together
2. **Attribution drives accountability:** Every marketing dollar tied to partner activation and retention
3. **Conversion is continuously optimized:** Data-driven improvements to onboarding funnel
4. **Basic fraud controls protect investments:** Simple, effective measures prevent obvious bad actors

**Core Philosophy:** Growth requires diversification. You can't scale a business on a single acquisition channel.

### What I Actually Built

We implemented six core features that were shipped to production:

**GROWTH INFRASTRUCTURE:**

**1. Digital Attribution System (Adjust Integration)**
- Integrated Adjust SDK in partner app for end-to-end attribution tracking
- Enabled tracking from install → signup → document submission → activation
- Created performance dashboards for growth team
- Unlocked ability to measure and optimize digital acquisition channels

**2. OEM B2B Partnership Pipeline**
- Established B2B partnerships with vehicle manufacturers
- Built bulk onboarding flows for dealer networks
- Created reporting infrastructure for OEM partners
- Win-win model: OEMs get vehicle usage, drivers get income, Porter gets supply

**3. Conversion Optimization (In-App Banners)**
- Launched targeted in-app banners based on onboarding stage
- Contextual messaging to drive document submission and activation
- A/B testing infrastructure for continuous optimization

**4. Automated Lead Assignment**
- Built automated routing system for partner leads to onboarding agents
- Reduced wait times and improved conversion through faster response

**BASIC FRAUD CONTROLS:**

**5. Multi-Document Blacklist Registry**
- Cross-document blocking system covering PAN, Aadhaar, DL, RC
- Prevents previously-blocked partners from rejoining with new documents
- Real-time checks during onboarding process
- Simple, effective fraud prevention without over-engineering

**6. Vehicle Verification Integration**
- Integrated third-party API for automated RC (vehicle registration) verification
- Real-time validation against government databases
- Replaced manual verification process

### System Architecture

**Growth Infrastructure:**

**Attribution System:**
- Integrated Adjust SDK for mobile measurement
- Tracks full funnel: Install → Signup → Document Upload → Activation → First Order
- Enables growth team to optimize spend by channel performance
- Provides real-time analytics and cohort analysis

**OEM Partnership Flow:**
- B2B onboarding portal for manufacturer partnerships
- Bulk partner upload via dealer networks
- Automated incentive tracking and disbursement
- Custom reporting for OEM partners

**Conversion Optimization:**
- Targeted in-app banners based on user state
- A/B testing framework for continuous improvement
- Real-time progress tracking for partners

**Basic Fraud Controls:**

**Blacklist Registry:**
- Multi-document cross-reference checks
- Blocks repeat offenders at onboarding
- Low false positive rate, high fraud catch rate

**Vehicle Verification:**
- API integration with third-party verification provider
- Instant RC validation
- Automated compliance checking

### Technical & Product Decisions

**Attribution Infrastructure (Adjust vs. In-House):**
- **Decision:** Use third-party Mobile Measurement Partner (Adjust) instead of building in-house
- **Rationale:** Industry-standard attribution prevents gaming by agencies, faster to market
- **Trade-off:** Vendor cost, but worth it for trusted measurement and speed

**OEM Partnerships (B2B2C Model):**
- **Decision:** Pursue manufacturer partnerships vs. only direct-to-consumer acquisition
- **Rationale:** Lower CAC, higher quality partners, sustainable pipeline
- **Implementation:** Built custom bulk onboarding flows for dealer-driven signups

**Conversion-First Approach:**
- **Decision:** Optimize for conversion rate, not just acquisition volume
- **Rationale:** Better to activate 50% of 1000 partners than 20% of 2000 partners
- **Implementation:** A/B testing on banners and lead assignment

**Basic Fraud Controls (Not Over-Engineering):**
- **Decision:** Build simple blacklist and verification checks, skip advanced ML/behavioral analysis
- **Rationale:** 80/20 rule—simple controls catch most fraud, can add sophistication later
- **Trade-off:** Won't catch sophisticated fraud, but sufficient for current scale

### Implementation Strategy

**Phase 1: Digital Attribution Foundation (Month 1-2)**
- Integrated Adjust SDK for partner app
- Set up attribution tracking infrastructure
- Built performance dashboards
- Started small test campaigns to validate

**Phase 2: OEM Partnerships (Month 2-4)**
- Pitched manufacturer partnerships
- Built B2B onboarding flows
- Piloted with initial OEM partners
- Reached 5% of acquisitions

**Phase 3: Conversion Optimization (Month 3-4)**
- Launched in-app banners (40% → 52% CTR)
- Automated lead assignment
- Reduced onboarding friction

**Phase 4: Basic Fraud Controls (Parallel Track)**
- Built multi-document blacklist registry
- Integrated vehicle verification API
- Just enough to prevent repeat offenders

**Testing & Monitoring:**
- **A/B Testing:** All in-app changes tested before full rollout
- **Attribution Validation:** Cross-checked third-party data with internal analytics
- **Channel Performance:** Weekly reviews of CAC, activation rate, retention by channel
- **Fraud Monitoring:** Basic dashboards to catch repeat offenders

---

## 📊 Impact

### Quantitative Metrics

**GROWTH ACHIEVEMENTS**

**Digital Acquisition Channel:**
- **20% of total partner supply** via digital marketing (from 0%)
- **10% of activations** (partners completing first order)
- Scalable spend: Could increase/decrease budget based on seasonal demand
- Unlocked new partner demographics
- Proved Porter could acquire digitally

**OEM Partnerships:**
- **5% of total acquisitions** via manufacturer partnerships
- Lower CAC than digital ads
- Higher retention: Vehicle owners vs. renters = better long-term engagement
- Created sustainable, scalable B2B pipeline

**Conversion Improvements:**
- **CTR: 40% → 52%** on in-app onboarding banners (30% relative improvement)
- **Automated lead assignment** reduced wait times
- Better signup → activation conversion

**BASIC FRAUD CONTROLS (TABLE STAKES)**

**Fraud Prevention:**
- **90% reduction in monthly fraud attempts** by repeat offenders (simple blacklist)
- **₹50L+ in fraud losses blocked** annually through basic controls
- Caught repeat offenders before they could place fraudulent orders
- Good enough for current scale—not advanced ML, just blocking known bad actors

**Compliance:**
- **Vehicle compliance: 50% → 78%** (automated RC verification)
- Faster verification vs. manual process
- Low false positive rate

**Channel Diversification:**
- **From 1 channel → 3 channels** (field sales, digital, OEM)
- **Risk reduction:** No longer dependent on single acquisition source
- **Flexibility:** Can adjust channel mix based on CAC, seasonality, market conditions

### Qualitative Impact

**Business Transformation**

**Growth Enablement:**
- **Unlocked digital marketing** as scalable acquisition channel—no longer 100% dependent on field sales
- **Created B2B partnerships** that provide sustainable, high-quality supply pipeline
- **Proved multi-channel model:** Porter can acquire partners through digital, OEM, and field sales
- **Enabled seasonal flexibility:** Can scale up digital spend during peak demand periods

**Strategic Advantage:**
- **Channel diversification** became competitive moat
- **OEM partnerships** created unique supply pipeline
- **Attribution infrastructure** enabled data-driven marketing optimization
- **Foundation for expansion:** Multi-channel playbook ready for new cities/markets

**Team & Culture:**
- **Established playbook** for launching new acquisition channels
- **Data-driven mindset:** Proved importance of attribution and funnel optimization
- **Cross-functional collaboration:** Growth, engineering, design, risk working together
- **B2B sales capability:** Showed Porter could do enterprise partnerships, not just B2C

**Basic Trust (Basic Controls):**
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
- **Impact:** 5% of acquisitions, became repeatable B2B playbook

**3. Optimize for Activation, Not Just Installs**
- **What I did:** Focused on activation quality rather than just acquisition volume
- **Why it worked:** Better to activate 50% of 1000 partners than 20% of 2000 partners
- **Impact:** Better unit economics and partner quality

**4. Conversion Optimization (Quick Wins)**
- **What I did:** A/B tested in-app banners, automated lead assignment
- **Why it worked:** Small friction reductions compound across funnel
- **Impact:** 40% → 52% CTR, better signup-to-activation

**5. Basic Fraud Controls (Not Over-Engineering)**
- **What I did:** Built simple blacklist and verification, skipped advanced ML
- **Why it worked:** 80/20 rule—simple controls catch most fraud, faster to ship
- **Impact:** 90% fraud reduction without months of ML model development

### Challenges & How We Overcame Them

**1. Attribution Data Quality**
- **The Problem:** Needed to ensure attribution data was accurate and trustworthy
- **How I Solved It:**
  - Used industry-standard third-party platform (Adjust) to prevent gaming
  - Built cohort analysis to validate quality vs. just volume
  - Cross-checked attribution data with internal analytics
- **Outcome:** Trusted data enabled confident marketing spend decisions

**2. OEM Sales Cycle**
- **The Problem:** B2B partnerships took longer to close than expected
- **How I Solved It:**
  - Started with pilot partners willing to move fast
  - Used pilot results to sell additional manufacturers
  - Built reusable onboarding templates to reduce setup time
- **Outcome:** Successfully established OEM pipeline contributing 5% of acquisitions

**3. Conversion Optimization Prioritization**
- **The Problem:** Many potential funnel improvements, limited resources
- **How I Solved It:**
  - Prioritized based on impact × effort
  - Ran A/B tests to validate impact
  - Shipped quick wins first (banners, lead assignment)
- **Outcome:** Delivered 30% CTR improvement efficiently

**4. Balancing Growth vs. Fraud Prevention**
- **The Problem:** Growth teams wanted fast onboarding; risk teams wanted thorough verification
- **How I Solved It:**
  - Built simple, automated fraud checks that didn't slow onboarding
  - Showed growth team that basic fraud controls protect their marketing investments
  - Set shared metrics: optimize for activation rate AND fraud rate
- **Outcome:** Both teams aligned on "growth with basic controls" approach

### Key Takeaways

- **Multi-Channel > Single Channel:** Diversification reduces risk and enables flexibility. Don't put all acquisition eggs in one basket.

- **Attribution Drives Accountability:** Without trusted attribution, growth spend becomes a black box. Third-party measurement prevents gaming.

- **Optimize for Quality, Not Just Quantity:** Activation rate matters more than install volume. Better to grow slower with higher-quality partners.

- **B2B Partnerships Beat Pure B2C:** OEM partnerships provided sustainable, high-quality supply at lower CAC. B2B2C model scales better than pure consumer acquisition.

- **Basic Fraud Controls Are Basic Controls:** Simple blacklist and verification caught 90% of fraud. Don't over-engineer—ship basics fast, add sophistication later.

- **Conversion Improvements Compound:** Small friction reductions (better banners, faster lead assignment) add up across the funnel to significant lift.

### What I'd Do Differently

**Earlier Focus on Activation Quality**
- Spent initial time optimizing for volume before pivoting to quality. Should have optimized for activation rate from day 1.

**Parallel OEM Outreach**
- Approached OEMs sequentially. Should have pitched multiple simultaneously to account for slow sales cycles.

**More Regional Content**
- Digital campaigns could have included more regional language content earlier to reach underserved segments.

---


---

---

← [Back to Porter Case Studies](https://github.com/ProductAlchemist/porter-case-studies)
---

