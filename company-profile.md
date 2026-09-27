[company-profile.md](https://github.com/user-attachments/files/32708241/company-profile.md)

# Fictional Company Profile — MeridianPay Financial Services

> Reference document used across all NIST CSF 2.0 portfolio projects (Gap Assessment, Framework Crosswalk, Vendor Risk Assessment). Keep this file at the root of the GitHub repo so every project links back to a consistent scenario.

## 1. Company Overview
- **Name:** MeridianPay Financial Services
- **Industry:** Cross-border payments & remittance fintech
- **Headquarters:** Dubai International Financial Centre (DIFC), UAE
- **Size:** ~350 employees | ~$45M annual revenue
- **Founded:** 2016
- **Business model:** Digital wallet + cross-border remittance platform, serving retail customers in the UAE/GCC with growing transaction corridors into the US and UK

## 2. Why NIST CSF Matters to MeridianPay
- MeridianPay recently signed a banking-as-a-service partnership with a US-licensed money transmitter to enable USD settlement corridors.
- The US partner's third-party risk program requires evidence of a documented cybersecurity risk management program aligned to **NIST CSF 2.0** as part of onboarding due diligence.
- MeridianPay is also pursuing cyber insurance renewal, and the insurer's underwriting questionnaire is structured around CSF's six Functions.
- Leadership (newly hired CISO) wants a baseline "Govern" function in place — until now, security was handled informally by the Head of IT.

## 3. Regulatory & Compliance Context
- **UAE:** Central Bank of the UAE (CBUAE) regulations, DIFC Data Protection Law, UAE PDPL
- **US exposure (via partner):** expectations aligned to NIST CSF 2.0 / NIST 800-53 (through partner due diligence, not direct regulatory obligation)
- **Card/payment scheme:** PCI DSS (for card-linked wallet top-ups)
- MeridianPay has no ISO 27001 certification yet, but has an internal controls mapping exercise in progress (separate portfolio project)

## 4. Organizational Structure (Security-Relevant)
- CISO (hired 4 months ago) — building the security program largely from scratch
- Head of IT Infrastructure — manages cloud environment and helpdesk
- Head of Product/Engineering — owns the payments platform and mobile app
- Compliance & MLRO (Money Laundering Reporting Officer) — owns AML/KYC obligations
- No dedicated GRC analyst or security operations team yet (a gap in itself — useful for your assessment)

## 5. Technology Environment
- **Core payments platform:** custom-built, hosted on AWS (multi-region: UAE + Ireland)
- **Mobile app:** iOS/Android wallet app
- **KYC/AML screening:** third-party SaaS vendor (sanctions/PEP screening)
- **CRM & customer support:** cloud CRM + outsourced customer support desk
- **HR/Payroll:** cloud HR/payroll SaaS
- **Corporate IT:** Microsoft 365, VPN, company-managed laptops; some BYOD for customer support staff
- **MSP:** an external managed IT services provider supports helpdesk and endpoint management

## 6. Third-Party / Vendor Landscape (for Vendor Risk Assessment project)
| Vendor | Function | Data Sensitivity | Notes |
|---|---|---|---|
| CloudCore AWS environment | Infrastructure hosting | High (PII, transaction data) | Primary production environment |
| ScreenSafe KYC/AML | Identity & sanctions screening | High (PII, government ID data) | Regulatory-critical vendor |
| PaySettle Gateway | Payment processing/settlement | High (financial transaction data) | Critical to core business function |
| HelpDesk Solutions (MSP) | IT support, endpoint management | Medium (privileged access) | Has admin access to endpoints |
| CloudHR Payroll | HR/payroll SaaS | Medium (employee PII, payroll data) | |
| BrightWave Support Outsourcing | Customer support (outsourced) | Medium (customer PII) | Overseas support team |
| AdReach Marketing Agency | Marketing/campaigns | Low (limited customer contact data) | |

## 7. Current Security Maturity (Baseline — Intentionally Immature)
Use this as your "as-is" state for the Gap Assessment. Deliberately gives you real gaps to find:
- No formal risk register or documented risk management process
- No written incident response plan (informal, ad hoc response only)
- Security policies exist only for password requirements and acceptable use — no asset management, no data classification, no vendor risk policy
- No formal vendor risk assessment process — vendors onboarded based on business need only
- MFA enforced on production AWS accounts but inconsistent on corporate SaaS tools
- No security awareness training program
- Logging exists (CloudTrail, app logs) but no centralized monitoring/SIEM
- No tested backup/recovery plan for the payments platform

## 8. Target State
MeridianPay wants to reach a level of maturity sufficient to:
1. Satisfy the US banking partner's third-party risk due diligence
2. Support a clean cyber insurance renewal
3. Prepare the ground for a future ISO 27001 certification effort
