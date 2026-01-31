# DFS Claims System ITN 2526-01
## 721 Vendor Questions & Answers Analysis

**Prepared for:** Main Street Group Proposal Development  
**Date:** January 31, 2026

---

# EXECUTIVE SUMMARY

## Key Takeaways from 721 Q&A

After analyzing all 721 vendor questions and DFS responses, here are the **critical insights** that will inform MSG's proposal strategy:

### 1. DFS is Technology-Agnostic
- **No specific cloud platform required** (Azure, AWS, or other all acceptable)
- **No specific technology stack preferred** (Microsoft, Salesforce, custom all welcome)
- **Licensing vs. ownership is open** - they'll consider either model
- Single or multi-cloud architecture both acceptable
- Cloud hosting expected, not on-premise state infrastructure

### 2. Budget Reality Check
- **Total project budget: ~$10.4M** (Schedule IV-B)
- **Solution vendor allocation: ~$3.9M** (software configuration, subscription, data conversion, API integration, training)
- This is relatively modest for a 10-year enterprise platform
- Suggests preference for SaaS/configurable solution over custom development

### 3. Integration Landscape is Manageable
- **FileNet** - Required integration (on-premise, API exists)
- **MS Dynamics SL 2018** - Database connection (no API documentation exists)
- **BCC Bulk Mailer** - No API, file-based integration
- **Guaranty Associations** - UDS file format (batch, well-documented via NCIGF)
- **No PALM/FLAIR integration** required
- **No EDI transaction sets** required

### 4. Legacy System Details Revealed
- **Visual FoxPro 9.0** source code available
- **SQL Server 2014** - RL Master Database (~406 GB)
- **115 TB** documents in legacy storage (FileNet + Windows)
- **No data dictionary/ERD exists** - will be provided during negotiations
- Original developers still employed at DFS
- North Highland (Schedule IV-B author) available during negotiations

### 5. Workflow Flexibility
- Many detailed workflow questions answered with "discussed during negotiations"
- DFS wants to see vendor proposals before specifying exact requirements
- Suggests openness to modern workflow approaches
- Low-code/no-code configuration capability requested

### 6. Security Requirements are Standard
- **No special security certifications required**
- TLS 1.2 minimum, TLS 1.3 preferred
- Data residency: U.S. only (CONUS)
- WCAG AA compliance for accessibility
- Standard audit trail requirements

---

# DETAILED Q&A ANALYSIS BY CATEGORY

## Category 1: Technical/Legacy System (92 Questions)

### Critical Findings

| Question | Answer | Strategic Implication |
|----------|--------|----------------------|
| FoxPro source code available? | Yes | Can reference for business logic |
| Data dictionary/ERD exists? | No - provided during negotiations | Migration planning after award |
| Original developers available? | Yes, still at DFS | Knowledge transfer possible |
| SQL Server version? | SQL Server 2014 | Standard migration path |
| Database size? | 406 GB | Manageable migration |
| Document storage size? | 115 TB | Significant - FileNet stays |
| FLAIR integration required? | No | Simplified scope |
| PALM integration required? | No | Simplified scope |

### Key Quote
> "Relevant system information will be provided during the negotiations process."

**Interpretation:** DFS is protecting proprietary details until vendor selection. Don't expect detailed legacy specs before award.

### MSG Advantage
Rich's restructuring experience means we understand the business logic without needing FoxPro expertise. The actual calculations (distributions, reserves, commissions) happen **outside** FoxPro currently.

---

## Category 2: Integration (84 Questions)

### Integration Matrix

| System | Integration Type | Notes |
|--------|-----------------|-------|
| **FileNet** | API (mandatory) | On-premise, stays in place, must integrate |
| **MS Dynamics SL 2018** | Database connection | No API docs available, real-time or batch acceptable |
| **BCC Bulk Mailer** | File-based | No API, vendor provides specs |
| **Guaranty Associations** | UDS files | Batch, NCIGF provides specs |
| **NRS Pro (Abandoned Property)** | TBD | Unclaimed property reporting |
| **OFAC** | TBD | Compliance checking |
| **Address Services** | BCC Bulkmailer | DFS has existing license |

### Critical Q&A

**Q:** Is FileNet integration mandatory?  
**A:** Yes.

**Q:** MS Dynamics integration real-time or batch?  
**A:** Contingent upon Respondent's proposed solution.

**Q:** UDS file volumes?  
**A:** Varies significantly - from <10 files to several hundred, each with 1 to tens of thousands of records. Volume is particularly high for new Receiverships.

**Q:** Bulk mail API available?  
**A:** No API for Bulk Mailer. Respondent alternatives for correspondence management will be considered.

### MSG Approach
- Build robust file-based integration layer (UDS, bulk mail)
- Propose modern API gateway for FileNet
- Design flexible MS Dynamics connector (database or future API)

---

## Category 3: Data Migration (33 Questions)

### Key Findings

| Question | Answer |
|----------|--------|
| Data cleansing responsibility? | DFS will cleanse before migration |
| Historical data years? | Discussed during negotiations |
| Active liquidations during migration? | Yes - must remain operational |
| Data migration success threshold? | 100% data integrity and accuracy |
| Preferred migration approach? | Open to vendor proposals |
| Canonical data model exists? | No - vendor defines |
| Staging database required? | Yes |

### Critical Quote
> "Success is defined based on acceptance criteria set by DRL with **100% data integrity and accuracy rate**."

**Warning:** Zero tolerance for data loss. Migration approach must include comprehensive validation.

### Migration Scope

- **14.8 million policy records** (all in active estates)
- **406 GB** database
- **115 TB** documents (stays in FileNet/Windows storage)
- All closed claims must be migrated
- Active liquidations must continue during cutover

---

## Category 4: Security & Compliance (59 Questions)

### Requirements Summary

| Requirement | Answer |
|-------------|--------|
| Security certifications | None required |
| Encryption standard | TLS 1.2 minimum, TLS 1.3 preferred |
| Data residency | U.S. only (including DR, backups) |
| Accessibility | WCAG AA |
| Data isolation between estates | 100% required |
| MFA required | Yes (inferred from portal requirements) |
| Audit trail | Required for all data changes |

### Key Flexibility
> "No security certifications are required."

This removes SOC 2 Type II as a barrier to entry - significant for smaller vendors.

### Chapter 60GG-2 and -4 Compliance
DFS references Florida Administrative Code Chapter 60GG which governs IT procurement and security. Key requirements:
- State-approved cloud configurations
- U.S. data residency
- Standard security controls

---

## Category 5: Portal & User Interface (223 Questions)

### User Counts
- **53 internal users** currently
- External claimant portal users: Volume depends on active receiverships
- Concurrent users during peak: Driven by new receivership events

### Portal Requirements

**Claimant Self-Service Portal:**
- Upload documents (POCs, supporting docs)
- Check claim status
- Messaging for claim questions
- Multi-language (English + Spanish desired)

**Internal Staff Portal:**
- Full claims processing workflow
- Role-based access
- Ad-hoc reporting (users create without IT)
- Dashboard with KPIs

**Mobile:**
- Nice to have, not required
- iOS and Android if implemented
- App store publication not required

### Key Q&A

**Q:** Complete system at go-live or phased?  
**A:** "The Department prefers that the complete system would be delivered at go-live."

**Q:** Ad-hoc reporting by business users?  
**A:** "Yes. End users should be able to create reports without IT assistance."

---

## Category 6: Claims Domain (51 Questions)

### Business Rules Revealed

| Topic | Answer |
|-------|--------|
| Statutory class definitions beyond Ch. 631? | No - statute governs |
| Class rules modifiable by users? | Role-based, must be audited |
| GA handles claims, not DRL | Correct - DRL tracks, GA pays covered claims |
| Claim linked to multiple estates? | No |
| Multiple examiners per claim? | Yes |
| POC templates | Single template, DRL maintains |
| Receiver claim number format | `<Company#>-<ID#>-<Suffix>` - must continue |

### Critical Process Clarification

**Q:** How does the system determine whether a claim is handled by a guaranty association versus DRL?  
**A:** "DRL does not handle claims. Claims open at liquidation, reopened post-liquidation, or opened (new) post-liquidation are sent to the appropriate GA for handling."

**Implication:** DRL is primarily a **tracking and reporting system**, not a claims adjudication system. GAs do the actual claims work. DRL:
- Receives POC forms
- Evaluates for classification/priority
- Issues NODs
- Prepares court reports (ICR/FCR)
- Manages distributions

### Objection Statistics
DFS provided actual objection rates from closed receiverships:
- Company 1: 1,759 claims, 4 objections (0.23%)
- Company 2: 53 claims, 0 objections (0%)
- Company 3: 30 claims, 0 objections (0%)
- Company 4: 3,233 claims, 23 objections (0.71%)
- Company 5: 33,606 claims, 57 objections (0.17%)

**Takeaway:** Objections are rare (<1%). Full legal case management not needed - just date/status tracking.

---

## Category 7: Workflow & Process (43 Questions)

### Flexibility Signals

Many workflow questions received the answer:
> "These details may be discussed during negotiations and with the awarded Contractor."

Topics deferred to negotiations:
- SLA matrices
- Examiner routing rules
- Reconciliation workflows
- Unclaimed property workflows
- FCR approval triggers

**Interpretation:** DFS wants vendor expertise to inform workflow design. They're not prescribing a rigid process.

### Key Workflow Insights

**Q:** Is ingestion of Estate Data a one-time event or ongoing?  
**A:** "Generally estate data is not a 'one & done' load process. Pieces of the data get loaded in at different times."

**Q:** Can validation rules be shared across estates?  
**A:** "Generally, validation rules can be configurable by estate, and there are instances where the validation rules are shared across estates."

---

## Category 8: Contract & Commercial (47 Questions)

### Critical Commercial Findings

| Question | Answer |
|----------|--------|
| Award structure | Single contract (one vendor, may have subs) |
| License vs. own IP | Contingent on vendor proposal |
| Contract term flexibility | Terms defined in Section 1.5 (5+5 years) |
| Existing RMIS contract transferable? | No, negotiated separately |
| Funding appropriated? | Portions allocated, annual budget updates |

### Budget Allocation (from Schedule IV-B)

Per DFS response, the **solution vendor allocation is ~$3.9M** covering:
- Software Configuration
- Software Subscription Fees
- Data and Records Conversion
- API Integration
- System Admin Training

This is separate from:
- Project management
- Internal DFS staff costs
- Infrastructure/hosting (may be separate)

### Contract Exception Process
DFS clearly stated multiple times:
> "Please note your exceptions in Volume 4: Contract Exceptions, as indicated in the ITN."

They expect and will consider exceptions during negotiations.

---

## Category 9: Deployment & Hosting (17 Questions)

### Cloud Requirements

| Requirement | Answer |
|-------------|--------|
| Approved cloud providers? | No specific requirement |
| Multi-cloud acceptable? | Yes, open to proposals |
| Single tenant required? | Open to multi-tenant with logical separation |
| DR location | CONUS required |
| GovCloud required? | Not specified |

### RTO/RPO
> "Additional details related to RTO and RPO targets will be discussed during the negotiation process."

### Support Model
Vendor expected to provide:
- Ongoing operations/support (managed service)
- Monitoring, patching coordination
- Incident response through hypercare and warranty periods

---

## Category 10: Reporting (24 Questions)

### Report Types

**Court Reports:**
- Interim Claims Report (ICR) - periodic, to court
- Final Claims Report (FCR) - final, to court
- Templates exist, can be provided during negotiations

**Operational Reports:**
- Most reports are real-time, few static
- Dashboards with KPIs desired
- Random sampling reports
- Distribution projection ("what-if" scenarios)

### Reporting Tools
- DFS currently uses **Lumigent** for data lineage/traceability
- End users should create reports without IT assistance

---

# STRATEGIC IMPLICATIONS FOR MSG PROPOSAL

## Strengths to Emphasize

### 1. Business Domain Expertise
Rich Caruso's Chapter 9/11 restructuring experience is **directly applicable**:
- Priority class waterfall logic
- Claims adjudication workflows
- Court reporting requirements
- Distribution calculations
- Creditor/claimant management

**Proposal Angle:** "Our team has hands-on experience with the exact business processes DRL uses - liquidation, claims classification, priority distributions, and court filings."

### 2. Modern Portal & Workflow Capabilities
Zenith OS platform aligns with DFS requirements:
- Cloud-native architecture
- Role-based access control
- Configurable workflows
- Self-service portals
- Dashboard/reporting capabilities

### 3. Integration Experience
MSG has built integrations with:
- Database connectors (like MS Dynamics requirement)
- File-based batch processing (like UDS, bulk mail)
- Document management systems
- External APIs

### 4. Flexible Technology Approach
DFS explicitly stated no technology preference. MSG can propose:
- Modern, maintainable stack
- Lower total cost of ownership
- Faster implementation through configuration vs. custom code

---

## Challenges to Address

### 1. Insurance Industry Experience
**Gap:** No direct insurance receivership projects  
**Mitigation:** 
- Rich Caruso as SME for business domain
- Emphasize transferable bankruptcy/restructuring expertise
- Propose partnership with insurance domain consultant

### 2. State Government References
**Gap:** Limited Florida state contract history  
**Mitigation:**
- Emphasize relevant private sector projects
- Highlight security and compliance capabilities
- Consider teaming arrangement with established state vendor

### 3. FileNet Integration
**Gap:** No direct FileNet experience  
**Mitigation:**
- FileNet APIs are well-documented (IBM)
- Propose dedicated integration sprint
- Include FileNet specialist subcontractor if needed

### 4. Scale of Data Migration
**Challenge:** 406 GB database, 14.8M policy records, 100% accuracy required  
**Mitigation:**
- Comprehensive validation framework in proposal
- Phased migration with verification gates
- DFS confirmed they will cleanse data first

---

## Recommended Proposal Strategy

### 1. Lead with Business Understanding
Open the proposal demonstrating deep understanding of:
- Chapter 631 F.S. claims process
- Priority class waterfall
- GA interaction model (DRL tracks, GA pays)
- Court reporting requirements (ICR/FCR)

### 2. Propose Modern, Configurable Platform
Position as:
- Cloud-native SaaS solution
- Configurable without code changes
- Role-based security built-in
- Workflow engine for claims processing
- Self-service portal for claimants

### 3. Integration Architecture
Present clear integration approach for:
- FileNet (document retrieval/storage)
- MS Dynamics (financial data)
- BCC Bulk Mailer (correspondence)
- Guaranty Associations (UDS files)

### 4. Migration Methodology
Emphasize:
- Zero-tolerance for data loss
- Parallel running capability
- Comprehensive validation framework
- Rollback procedures

### 5. Price Competitively
With ~$3.9M vendor allocation:
- Focus on licensing/subscription model
- Minimize custom development
- Leverage existing platform capabilities

---

# QUESTIONS TO ASK IN NEGOTIATION

If MSG advances to negotiation, prioritize:

1. **Data Dictionary/ERD** - Essential for migration planning
2. **Sample ICR/FCR templates** - Format requirements
3. **FileNet API documentation** - Integration specifics
4. **UDS file samples** - GA data exchange format
5. **Current workflow documentation** - Process details
6. **Reserve calculation logic** - Currently outside FoxPro
7. **Distribution calculation formulas** - Business rules
8. **Performance baselines** - Current system metrics

---

# APPENDIX: FULL Q&A CATEGORIZATION

| Category | Count | Key Themes |
|----------|-------|------------|
| Portal/UI | 223 | User experience, mobile, claimant self-service |
| Technical/Legacy | 92 | FoxPro, SQL Server, existing system details |
| Integration | 84 | FileNet, Dynamics, GA, bulk mail |
| Security/Compliance | 59 | Encryption, audit, access control |
| Claims Domain | 51 | Business rules, priority classes, POC/NOD |
| Contract/Commercial | 47 | Pricing, IP, terms |
| Workflow/Process | 43 | Automation, routing, approvals |
| Data Migration | 33 | ETL, validation, staging |
| Reporting | 24 | ICR/FCR, dashboards, ad-hoc |
| Deployment/Hosting | 17 | Cloud, DR, environments |
| Other | 48 | Miscellaneous |
| **TOTAL** | **721** | |

---

**Document Classification:** MSG Internal - Proposal Development  
**Last Updated:** January 31, 2026
