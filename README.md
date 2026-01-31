<div align="center">

# 🏛️ DRL Claims System Demo

**Florida Department of Financial Services**  
**Division of Rehabilitation & Liquidation**  
**Claims System Modernization MVP**

[![Demo](https://img.shields.io/badge/Live-Demo-success?style=for-the-badge)](https://msg-headquarters.github.io/DLR-Demo/)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react)](https://react.dev)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](./LICENSE)

*Interactive demonstration of Main Street Group's proposed solution for ITN 2526-01*

[**🚀 Launch Demo**](https://msg-headquarters.github.io/DLR-Demo/) · [**📋 Architecture**](./docs/ARCHITECTURE.md) · [**📊 Q&A Analysis**](./docs/QA_ANALYSIS.md)

</div>

---

## 📖 Overview

This interactive demo showcases MSG's proposed modern claims management platform for Florida's insurance receivership operations under **Chapter 631, Florida Statutes**.

The system manages the complete lifecycle of insurance company liquidations—from initial data ingestion through final distribution—implementing the statutory priority waterfall that governs how claimants are paid.

### What This Demo Shows

| Feature | Description |
|---------|-------------|
| **Claims Dashboard** | Real-time KPIs, trend analysis, priority waterfall |
| **Claims Management** | Full CRUD operations, status workflow, filtering |
| **Estate Management** | Multi-estate support, workflow tracking |
| **POC Processing** | Proof of Claim intake and classification |
| **Distribution Calculator** | §631.271 priority waterfall with projections |
| **Claimant Portal** | Public self-service for claim status lookup |

---

## 🖥️ Screenshots

<table>
<tr>
<td width="50%">

### Staff Dashboard
Real-time KPIs, claims trends, priority waterfall visualization

</td>
<td width="50%">

### Claims Management
Full claims table with filtering and detail modals

</td>
</tr>
<tr>
<td width="50%">

### Distribution Calculator
§631.271 priority waterfall with what-if scenarios

</td>
<td width="50%">

### Claimant Portal
Public self-service claim status lookup

</td>
</tr>
</table>

---

## 🔧 Technical Stack

**Demo Implementation:**
- React 18 (via CDN, no build required)
- Recharts for data visualization
- Custom CSS with CSS variables
- Google Fonts (DM Sans, JetBrains Mono)

**Production Architecture (Proposed):**
- Cloud-native PaaS (Azure/AWS)
- .NET Core or Node.js API layer
- SQL Server database
- FileNet document management integration
- MS Dynamics financial connector
- UDS file processing for Guaranty Associations

---

## 📊 Chapter 631 Priority Classes

The demo implements Florida's statutory claims priority waterfall:

| Class | Description | Notes |
|:-----:|-------------|-------|
| 1 | Administrative Costs | Receiver expenses, GA handling |
| 2 | Policy Loss Claims | Policyholder claims, GA reimbursement |
| 3 | Federal Government | Federal claims |
| 4 | OIR Assessments | Office of Insurance Regulation |
| 5 | Employee Wages | Capped at $2,000/employee |
| 6 | General Creditors | Vendors, agents, providers |
| 7 | State/Local Government | State and municipal claims |
| 8-11 | Late-filed, Interest, Shareholders | Lower priority classes |

> 📌 Each class must be paid in full before the next class receives any distribution.

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/MSG-Headquarters/DLR-Demo.git
cd DLR-Demo

# Open directly in browser (no build required)
open index.html

# Or serve locally
python -m http.server 8000
```

Visit `http://localhost:8000` to view the demo.

---

## 📁 Repository Structure

```
DLR-Demo/
├── index.html              # Complete demo application
├── README.md               # This file
└── docs/
    ├── ARCHITECTURE.md     # Full platform architecture
    ├── QA_ANALYSIS.md      # 721 vendor Q&A analysis
    └── BRIDGE_HANDOFF.md   # Deployment instructions
```

---

## 🏢 About Main Street Group

**Main Street Group (MSG)** delivers technology solutions for complex business operations, specializing in:

- Enterprise platform development
- Claims management systems
- Workflow automation
- Business restructuring technology

### Project Team

| Role | Name | Expertise |
|------|------|-----------|
| Engineering Lead | Koda | Platform architecture, full-stack development |
| Domain SME | Rich Caruso | Chapter 9/11 restructuring, liquidation operations |

---

## 📞 Contact

**Main Street Group**  
*Technology Solutions for Complex Business Challenges*

📧 [Request Demo](mailto:info@mainstgroup.com)

---

<div align="center">

*Demo prepared for Florida DFS ITN 2526-01 evaluation*

© 2026 Main Street Group. All rights reserved.

</div>
