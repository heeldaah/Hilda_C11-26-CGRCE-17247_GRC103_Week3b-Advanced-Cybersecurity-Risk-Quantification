# INTERNATIONAL CYBERSECURITY AND DIGITAL FORENSICS ACADEMY (ICDFA)

## Governance, Compliance, and Risk (GCR)

### GRC 103 Risk Assessment and Management Techniques

# Lab 3b: Advanced Cybersecurity Risk Quantification and Control Investment Analysis

### SecureBank Financial: Advanced Cybersecurity Risk Quantification

---

| Student / Assessment Details | Information |
|---|---|
| **Student name** | Hilda Odein Joshua-Jack |
| **Registration number** | C11/26/CGRCE/17247 |
| **Course / cohort** | ICDFA GRC Engineering Cohort 11 |
| **Assessment date** | 1st November 2026 |

---

## 1. Project Overview

This project presents a quantitative cybersecurity risk assessment of SecureBank Financial's SecureMobile banking platform. The assessment considers three security threats identified during a security review: API authentication bypass, database injection and session hijacking.

The objective is to translate the technical weaknesses into potential financial exposure, assess the value of proposed security controls, estimate residual risk and provide management with a prioritised treatment plan.

The analysis uses the scenario dataset supplied for the practical exercise. It is a decision-support model, not a prediction of guaranteed losses or a substitute for a bank-wide risk assessment.

## 2. Assessment Objectives

The assessment was designed to:

- Estimate the potential financial impact of each identified threat.
- Quantify current annualised risk exposure using the supplied likelihood assumptions.
- Evaluate the proposed API Security Gateway, Web Application Firewall (WAF) and Multi-Factor Authentication (MFA) controls.
- Estimate the reduction in exposure and the residual risk after control implementation.
- Compare implementation and maintenance costs with projected avoided losses.
- Present the findings in a format suitable for management review and risk-treatment decisions.

## 3. Executive Summary and Key Findings

The supplied scenario identifies three material risks to the SecureMobile platform. Database injection represents the largest estimated financial exposure because the scenario assigns a potential loss of **$125 million** to the compromise of 500,000 customer profiles at an estimated cost of $250 per record.

Under the modelling assumption that the supplied exploit probabilities represent annual probabilities of one loss event, the combined current annual loss exposure is estimated at **$35 million**. Applying the proposed controls to their corresponding risks reduces the modelled annual exposure to **$8.0375 million**, a reduction of approximately **77%**.

The proposed control portfolio requires an initial investment of **$700,000** and annual maintenance of **$105,000**. Over a three-year evaluation period, the estimated total cost is **$1.015 million**, compared with projected avoided losses of **$80.8875 million**. This produces an indicative three-year portfolio ROI of approximately **7,870%** under the stated assumptions.

These figures are highly dependent on the probability and loss assumptions supplied in the scenario. They should be treated as estimates for prioritisation, not guaranteed financial returns.

## 4. Risk Assessment and Financial Exposure

### 4.1 Scenario inputs

| Risk | Supplied probability | Potential loss basis | Single-loss estimate |
|---|---:|---|---:|
| API authentication bypass | 15% | Maximum single incident loss | $5,000,000 |
| Database injection | 25% | 500,000 profiles × $250 per record | $125,000,000 |
| Session hijacking | 40% | 5,000 simultaneous sessions × $1,500 average loss per account | $7,500,000 |

Other platform context supplied in the scenario includes 500,000 active customers, an average transaction value of $2,500 and approximately 50,000 daily transactions.

### 4.2 Current annualised loss exposure

The model uses the following calculation:

**Single Loss Expectancy (SLE)** = estimated financial loss from one event.

**Annualised Loss Expectancy (ALE) proxy** = SLE × supplied probability.

| Risk | SLE | Probability used | Modelled annual exposure |
|---|---:|---:|---:|
| API authentication bypass | $5,000,000 | 15% | $750,000 |
| Database injection | $125,000,000 | 25% | $31,250,000 |
| Session hijacking | $7,500,000 | 40% | $3,000,000 |
| **Total** | | | **$35,000,000** |

Database injection is the dominant financial risk in the model, accounting for approximately 89.3% of the total estimated current annual exposure. Session hijacking has the highest supplied probability, but its estimated financial impact is lower than that of database injection.

## 5. Proposed Security Controls

The scenario provides three proposed controls. Each control is mapped to one principal risk for the purpose of this model to avoid counting the same reduction against multiple risks.

| Proposed control | Primary risk addressed | Initial cost | Annual maintenance | Stated effectiveness |
|---|---|---:|---:|---:|
| Advanced API Security Gateway | API authentication bypass | $350,000 | $50,000 | 90% reduction in API vulnerabilities |
| Web Application Firewall (WAF) | Database injection | $150,000 | $25,000 | 75% reduction in web vulnerabilities |
| MFA enhancement | Session hijacking | $200,000 | $30,000 | 95% reduction in account takeover |

**Control-mapping assumption:** The WAF is treated as reducing the database-injection risk because the model assumes the relevant web/API traffic passes through it. The MFA enhancement is applied to the session-hijacking risk. Actual effectiveness will depend on architecture, configuration, coverage, user adoption and testing.

## 6. Residual Risk After Control Implementation

The model applies each control's stated effectiveness to the annual exposure of its mapped risk.

| Risk | Current annual exposure | Assumed reduction | Annual exposure reduction | Residual annual exposure |
|---|---:|---:|---:|---:|
| API authentication bypass | $750,000 | 90% | $675,000 | $75,000 |
| Database injection | $31,250,000 | 75% | $23,437,500 | $7,812,500 |
| Session hijacking | $3,000,000 | 95% | $2,850,000 | $150,000 |
| **Total** | **$35,000,000** | | **$26,962,500** | **$8,037,500** |

The proposed controls reduce the modelled annual exposure by approximately **77%**. However, the residual exposure remains material, particularly for database injection. Control implementation should therefore be followed by validation, monitoring and further risk treatment where necessary.

## 7. Investment and Return Analysis

### 7.1 Portfolio investment

| Cost item | Amount |
|---|---:|
| Initial implementation costs | $700,000 |
| Annual maintenance costs | $105,000 |
| Three-year maintenance costs | $315,000 |
| **Total three-year cost** | **$1,015,000** |

### 7.2 Three-year financial comparison

| Measure | Estimate |
|---|---:|
| Annual modelled exposure reduction | $26,962,500 |
| Three-year projected avoided losses | $80,887,500 |
| Total three-year control cost | $1,015,000 |
| Indicative three-year portfolio ROI | Approximately 7,870% |

ROI is calculated as:

**ROI** = ((projected avoided losses − total control costs) ÷ total control costs) × 100.

The model assumes the controls are fully implemented and effective for the full three-year period, with no discounting, implementation delay or change in threat conditions. The result is therefore an indicative comparison, not a guaranteed return.

## 8. Risk Prioritisation

The assessment prioritises risks using both estimated financial exposure and a qualitative probability-impact matrix.

| Risk | Probability category | Impact category | Indicative matrix rating | Treatment priority |
|---|---|---|---|---|
| API authentication bypass | Low | Medium | Medium | Moderate |
| Database injection | Medium | High | High | Critical |
| Session hijacking | High | Medium | High | High |

The probability and impact bands used in the matrix are analyst-defined working thresholds for this exercise. They are not presented as SecureBank's approved enterprise risk appetite or risk-rating standard.

Although API authentication bypass has a lower supplied probability, its potential single-incident loss is substantial. It should not be ignored solely because its matrix rating is lower than the other two risks.

## 9. Recommended Risk Treatment Plan

### Phase 1: Immediate priorities

- Prioritise remediation of database injection weaknesses.
- Review database input validation, parameterised queries, privileged access and data-access pathways.
- Confirm that all relevant web and API traffic is routed through the WAF.
- Validate API authentication and authorisation controls, including negative testing for bypass scenarios.
- Review session management, token handling, session expiry and revocation.

### Phase 2: Control implementation and validation

- Deploy and configure the Advanced API Security Gateway.
- Implement the WAF with appropriate rules, logging and tuning.
- Roll out MFA enhancement for relevant customer and privileged-user journeys.
- Test each control against the threat it is intended to mitigate.
- Record implementation evidence, control owners, exceptions and residual-risk acceptance.

### Phase 3: Continuous monitoring

- Monitor API gateway and WAF alerts, blocked requests and rule effectiveness.
- Monitor suspicious authentication patterns, session anomalies and account-takeover indicators.
- Track vulnerability remediation, control coverage and security incidents.
- Reassess likelihood and impact using actual incident and loss data.
- Review residual risks periodically and escalate risks that exceed approved tolerance.

## 10. Methodology, Assumptions and Limitations

The assessment is based on the scenario dataset provided for the practical exercise. Calculations are shown in the accompanying workbook and summarised in the executive report.

Key assumptions and limitations:

1. **Probability period:** The scenario gives exploit probabilities but does not specify a time period. For calculation purposes, this assessment interprets them as annual probabilities of one loss event. They are not treated as annual incident frequencies or Annual Rate of Occurrence (ARO) values.
2. **ALE interpretation:** SLE multiplied by the assumed annual probability is used as an annualised loss-exposure proxy under a simplified single-event model. It does not model repeated incidents, event frequency distributions or multiple losses within a year.
3. **Loss estimates:** The supplied maximum or estimated losses are used as the SLE basis. Actual losses could be lower or higher and may include legal, regulatory, response, operational, reputational and customer-remediation costs not separately quantified in the scenario.
4. **Control effectiveness:** The stated percentages are applied directly to the mapped risk exposure. This assumes the effectiveness percentages translate proportionally into risk reduction. Actual effectiveness must be validated through design review, configuration assessment and testing.
5. **No double counting:** Each proposed control is assigned to one primary risk in the model. In practice, controls may influence more than one threat, but overlapping benefits have not been claimed.
6. **WAF coverage:** The WAF is assumed to inspect the relevant traffic associated with the database-injection scenario. This needs architectural confirmation.
7. **Evaluation period:** ROI is calculated over three years. The model does not include discount rates, inflation, tax, implementation delays, changing threat conditions or the cost of control failure.
8. **Risk matrix:** Probability and impact thresholds are analyst-defined for this exercise and should be replaced with the organisation's approved risk-rating methodology when available.

## 11. Project Files

The repository contains the following deliverables:

| File | Description |
|---|---|
| [01_Risk_Quantification_Workbook.xlsx_Download](./01_Risk_Quantification_Workbook.xlsx) | Excel workbook containing assumptions, risk calculations, control analysis, residual risk, treatment plan and dashboard visualisations. |
| [02_Risk_Assessment_Executive_Report.docx](./02_Risk_Assessment_Executive_Report.docx) | Written assessment covering the scenario, methodology, financial exposure, control evaluation, recommendations and limitations. |
| [03_Executive_Dashboard.pdf](./03_Executive_Dashboard.pdf) | Management-facing dashboard summarising key risk and investment findings. |

## 12. Conclusion

The assessment indicates that database injection is SecureBank Financial's most significant modelled financial exposure, while session hijacking presents the highest supplied exploit probability. The proposed control portfolio materially reduces the estimated exposure, but does not eliminate risk.

Management should prioritise database-injection remediation while implementing and validating the API Security Gateway, WAF and MFA enhancements. The organisation should then monitor control performance, reassess residual risk using operational evidence and ensure that any remaining exposure is formally owned and accepted at the appropriate level.

---

**Programme:** ICDFA GRC Engineering Cohort 11  
**Practical:** GRC103 – Advanced Cybersecurity Risk Quantification  
**Organisation in case study:** SecureBank Financial  
**Platform assessed:** SecureMobile Banking Platform  
**Prepared by:** Hilda Odein Joshua-Jack  
**Registration number:** C11/26/CGRCE/17247
