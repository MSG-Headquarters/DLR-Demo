# DRL Claims System Demo - Bridge Handoff Document
## For Forged App Builder Deployment

**Project:** Florida DFS Division of Rehabilitation & Liquidation (DRL) Claims System Modernization  
**Purpose:** Interactive demo for ITN 2526-01 proposal showcasing MSG's platform capabilities  
**Target Deployment:** GitHub Pages → SSI Demo Environment  
**Repository:** https://github.com/MSG-Headquarters/DLR-Demo.git

---

## Executive Summary

This demo showcases Main Street Group's proposed solution for the Florida Department of Financial Services' insurance liquidation claims management system. The ITN response deadline is **February 13, 2026**, and this demo will be referenced in our technical proposal and potentially shown to evaluators.

### What This Demo Proves

1. **Domain Expertise** - We understand Chapter 631 F.S. insurance receivership workflow
2. **Rapid Prototyping** - Built functional MVP in hours, not weeks
3. **Modern UX** - Clean, professional interface for government users
4. **Full-Stack Capability** - Both staff portal and public claimant portal
5. **Business Logic Implementation** - Priority waterfall, claims classification, workflow states

---

## Technical Specifications

### Current State
- **Single HTML file** with embedded React/Babel
- **No build process required** - runs directly in browser
- **Dependencies loaded via CDN:**
  - React 18.2.0
  - ReactDOM 18.2.0
  - Babel Standalone 7.23.5
  - Recharts 2.10.3
  - Google Fonts (DM Sans, JetBrains Mono)

### Recommended Enhancements for Production Demo

| Priority | Enhancement | Purpose |
|----------|-------------|---------|
| HIGH | Add MSG branding/logo | Professional appearance |
| HIGH | Add "Request Demo" CTA | Lead capture for proposal |
| MEDIUM | Add more sample data | Richer demo experience |
| MEDIUM | Mobile responsiveness polish | Show PWA capability |
| LOW | Add print-friendly ICR/FCR preview | Show reporting capability |
| LOW | Add Spanish language toggle | Show multi-language support |

---

## File Structure for Deployment

```
DLR-Demo/
├── index.html                 # Main demo application
├── README.md                  # Project overview
├── docs/
│   ├── ARCHITECTURE.md        # Full platform architecture document
│   ├── QA_ANALYSIS.md         # 721 Q&A analysis from ITN
│   └── DOMAIN_OVERVIEW.md     # Chapter 631 F.S. domain primer
├── assets/
│   ├── msg-logo.svg           # MSG branding (need to add)
│   ├── fl-seal.svg            # Florida state seal (need to add)
│   └── screenshots/           # Demo screenshots for proposal
│       ├── dashboard.png
│       ├── claims.png
│       ├── distribution.png
│       └── claimant-portal.png
└── CNAME                      # For custom domain (optional)
```

---

## Demo Features Walkthrough

### Staff Portal (Internal DRL Users)

#### 1. Dashboard (`view: 'dashboard'`)
**What it shows:**
- KPI cards: Active Claims (3,456), Pending Review (47), Total Distributed ($34.2M), NODs This Month (156)
- Claims trend chart (received vs. approved over 6 months)
- Priority waterfall visualization (Classes 1-7 distribution)
- Recent claims activity table
- ICR filing deadline alert banner

**Business context:** This is what a Claims Supervisor like Rich would see daily to manage receivership operations.

#### 2. Claims Management (`view: 'claims'`)
**What it shows:**
- Tabbed interface: All | Pending | Review | Approved | Denied
- Full claims table with: Claim ID, Claimant, Estate, Class, Amount, Recommended, Status
- Click-through to claim detail modal

**Business context:** The core workflow - processing Proof of Claim forms and issuing determinations.

#### 3. Active Estates (`view: 'estates'`)
**What it shows:**
- Estate cards: Sunshine State Insurance, Gulf Coast Casualty, Palm Beach Mutual
- Estate details form (NAIC, Court Case, Bar Date, Lines of Business)
- Workflow timeline: Data Ingestion → POC Notices → Claims Processing → ICR Filing → Distribution

**Business context:** Each insolvent insurance company becomes an "estate" that DRL manages through its lifecycle.

#### 4. POC Processing (`view: 'poc'`)
**What it shows:**
- New POC entry form with all required fields
- Priority class auto-assignment based on claimant type
- Document upload zone
- Pending POCs queue

**Business context:** When a claimant submits a Proof of Claim form, this is where staff process it.

#### 5. Distribution Calculator (`view: 'distribution'`)
**What it shows:**
- §631.271 priority waterfall table
- Total Assets vs. Total Claims vs. Recovery Rate
- Class-by-class: Claims count, Approved amount, Available funds, Distribution %, Status
- "What-If" scenario button (placeholder)

**Business context:** The statutory distribution priority per Florida law - must pay Class 1 in full before Class 2, etc.

### Claimant Portal (Public Self-Service)

#### Claim Lookup
**What it shows:**
- Florida DFS branding
- Lookup form: Claim Number + Last 4 SSN
- Claim status view with timeline
- Document upload and NOD download buttons

**Business context:** Public-facing portal for policyholders and creditors to check their claim status.

---

## Sample Data Reference

### Estates
```javascript
const estates = [
    { id: 'EST-2024-001', name: 'Sunshine State Insurance Co.', status: 'active', claims: 3456, amount: 45678900, policies: 12500 },
    { id: 'EST-2024-002', name: 'Gulf Coast Casualty', status: 'active', claims: 1823, amount: 23456700, policies: 8200 },
    { id: 'EST-2023-015', name: 'Palm Beach Mutual', status: 'distributing', claims: 892, amount: 12340000, policies: 4100 },
];
```

### Claims
```javascript
const claims = [
    { id: '001-45678-01', claimant: 'Johnson Family Trust', type: 'Policyholder', amount: 125000, status: 'approved', class: 2, estate: 'Sunshine State Insurance', date: '2024-04-02' },
    { id: '001-45679-01', claimant: 'ABC Medical Center', type: 'Healthcare Provider', amount: 89500, status: 'review', class: 2, estate: 'Sunshine State Insurance', date: '2024-04-03' },
    // ... more claims
];
```

### Priority Waterfall (§631.271 F.S.)
```javascript
const waterfall = [
    { class: 1, name: 'Administrative', amt: 2450000, total: 2500000, pct: 98, color: '#FF5630' },
    { class: 2, name: 'Policy Claims', amt: 28500000, total: 32000000, pct: 89, color: '#FF8B00' },
    { class: 3, name: 'Federal Govt', amt: 0, total: 0, pct: 0, color: '#FFAB00' },
    { class: 4, name: 'OIR Assessments', amt: 125000, total: 125000, pct: 100, color: '#36B37E' },
    { class: 5, name: 'Employee Wages', amt: 85000, total: 85000, pct: 100, color: '#00B8D9' },
    { class: 6, name: 'General Creditors', amt: 3200000, total: 8500000, pct: 38, color: '#6554C0' },
    { class: 7, name: 'State/Local Govt', amt: 0, total: 450000, pct: 0, color: '#8777D9' },
];
```

---

## Deployment Instructions

### Option 1: GitHub Pages (Recommended)

1. Push `index.html` to the repo root
2. Go to **Settings → Pages**
3. Set Source to "Deploy from a branch"
4. Select `main` branch, `/ (root)` folder
5. Save - site will be live at `https://msg-headquarters.github.io/DLR-Demo/`

### Option 2: SSI Deployment

If deploying to MSG's SSI environment:
1. Create subdomain: `drl-demo.umbrassi.com`
2. Upload `index.html` to web root
3. Configure SSL certificate
4. Add to MSG demo portfolio

### Option 3: Vercel/Netlify (Quick Alternative)

1. Connect GitHub repo
2. Auto-deploys on push
3. Free tier supports custom domains

---

## Customization Points

### Branding Updates Needed

```css
/* MSG Logo - replace logo-icon content */
.logo-icon {
    background: url('assets/msg-logo.svg') center/contain no-repeat;
}

/* Florida Seal - add to portal header */
.portal-logo-icon {
    background: url('assets/fl-seal.svg') center/contain no-repeat;
}
```

### Demo Mode Banner (Add to show this is a demo)

```html
<div class="demo-banner">
    🎯 Interactive Demo | Main Street Group | ITN 2526-01 Response
    <a href="mailto:info@mainstgroup.com">Request Full Presentation →</a>
</div>
```

### Add More Sample Claims

Expand the `claims` array with more diverse examples:
- Workers' comp claims
- Life insurance claims
- Guaranty Association reimbursements
- Late-filed claims (Class 8)
- Agent commission claims

---

## ITN Context for Evaluators

If evaluators interact with this demo, key points to highlight:

1. **§631.271 Compliance** - Priority waterfall follows Florida statute exactly
2. **Receiver Claim Number Format** - Uses `<Company#>-<ID#>-<Suffix>` per DRL standard
3. **Guaranty Association Integration** - Shows GA claims (FIGA) as Class 2
4. **Multi-Estate Support** - Three concurrent receiverships demonstrated
5. **Dual Portal Architecture** - Staff and public portals as ITN requires
6. **Modern Tech Stack** - React, responsive design, real-time charts

---

## Related Documents

| Document | Location | Purpose |
|----------|----------|---------|
| Platform Architecture | `/docs/ARCHITECTURE.md` | Full technical design |
| Q&A Analysis | `/docs/QA_ANALYSIS.md` | Insights from 721 vendor questions |
| ITN Package | (Internal) | Complete procurement documents |
| Proposal Draft | (In Progress) | MSG's response to ITN |

---

## Contact & Ownership

**Project Lead:** Koda (MSG Engineering)  
**Domain SME:** Rich Caruso (Restructuring & Liquidation)  
**Deployment:** Forged App Builder  

**Timeline:**
- Demo ready: January 31, 2026 ✓
- GitHub deployment: ASAP
- SSI deployment: Before Feb 7, 2026 (go/no-go decision)
- ITN Response Due: February 13, 2026

---

## Quick Start for Forged

```bash
# Clone the repo
git clone https://github.com/MSG-Headquarters/DLR-Demo.git
cd DLR-Demo

# The index.html is the complete demo - just open in browser
open index.html

# Or serve locally
python -m http.server 8000
# Then visit http://localhost:8000
```

**No npm install, no build process, no dependencies to manage.**

---

*Bridge document prepared by Claude for MSG Engineering Team*  
*Last updated: January 31, 2026*
