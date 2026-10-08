# Daily Transaction Monitoring — Lesson 2

## Alert Investigation: From “Red Flag” to Defensible Disposition

**Market focus: 🇺🇸 United States + 🇬🇧 United Kingdom**

Today we are focusing on one of the most important practical skills for a Transaction Monitoring analyst:

> **How do you investigate an alert without jumping to the conclusion that the customer is laundering money?**

This is particularly important for interviews because employers generally don't want someone who simply knows AML terminology. They want someone who can take an alert, gather relevant information, identify meaningful red flags, distinguish unusual activity from genuinely suspicious activity, and document a defensible conclusion.

---

# 1. What exactly is a Transaction Monitoring alert?

A Transaction Monitoring system normally contains rules, scenarios, thresholds, models or other detection mechanisms designed to identify potentially unusual activity.

For example, a US bank could have a scenario designed to identify:

> Multiple incoming payments from unrelated parties followed by rapid outgoing transfers.

A customer triggers the scenario.

The system generates:

**Alert ID: TM-XXXX**

At this point, you have **an alert—not a SAR and not a finding of money laundering.**

This distinction is critical.

FinCEN's guidance says that institutions should consider the overall activity and multiple factors rather than treating one red flag as automatically determinative. ([FinCEN.gov][1])

The analyst therefore needs to investigate the **context surrounding the alert**.

---

# 2. Step One — Understand WHY the alert fired

Before investigating the customer, understand the actual scenario.

Suppose the rule is:

### "Rapid Movement of Funds"

Parameters:

* Multiple incoming transactions
* Multiple counterparties
* Significant aggregate value
* Funds moved out shortly after receipt
* Activity materially different from historical behaviour

The first question should be:

> **Which transactions caused the alert to fire?**

Don't simply look at the customer's most recent transaction.

Identify:

* Date/time
* Amount
* Transaction type
* Originator
* Beneficiary
* Geography
* Payment channel
* Account involved
* Transaction direction
* Reference/payment description

Then reconstruct the activity.

For example:

**Monday**

A → Customer: $25,000

B → Customer: $18,000

C → Customer: $22,000

**Monday evening**

Customer → D: $30,000

Customer → E: $25,000

**Tuesday**

Customer → Cash withdrawal: $7,000

That's much more informative than saying:

> "Customer received $65,000."

You're beginning to see the **flow of funds**.

---

# 3. Step Two — Understand the customer

Now move to KYC/CDD.

For a US or UK investigation, you might review:

* Customer type
* Individual/business
* Occupation/business activity
* Expected account activity
* Source of funds/wealth information
* Customer risk rating
* Geographic footprint
* Account opening date
* Products/services used
* Previous alerts
* Previous SAR-related information where your role permits access
* Adverse media/internal intelligence
* Beneficial ownership for relevant entities

The objective is simple:

> **Does the customer's actual activity make sense given what the institution knows about them?**

Imagine two customers each receive $500,000.

### Customer A

* Large US commercial property business
* Annual revenue: $30 million
* Regular property transactions
* Receives large wire transfers

$500,000 may be completely normal.

### Customer B

* Personal checking account
* Declared occupation: teacher
* Annual income: $65,000
* Historically receives payroll
* Suddenly receives $500,000 from 15 unrelated people

The second scenario requires considerably more investigation.

The **amount alone** isn't the conclusion.

The **mismatch between profile and behaviour** is what makes the activity potentially concerning.

---

# 4. Step Three — Establish the customer's baseline

This is one of the most valuable skills you can develop.

Suppose historical activity shows:

| Activity            | Historical pattern |
| ------------------- | -----------------: |
| Monthly credits     |      $4,000–$7,000 |
| Monthly debits      |      $3,000–$6,000 |
| Counterparties      |                5–8 |
| International wires |               None |
| Cash                |            Minimal |

Then during one week:

> $380,000 incoming
> 31 counterparties
> $350,000 sent onward
> 12 new beneficiaries

The most important observation isn't:

> **"$380,000 is a large amount."**

It's:

> **"The customer's transactional behaviour has materially deviated from their established baseline."**

This is exactly the type of thinking that makes a Transaction Monitoring analyst valuable.

---

# 5. Step Four — Follow the money

Now investigate the transaction chain.

Suppose:

**A → Customer: $80,000**

**B → Customer: $65,000**

**C → Customer: $75,000**

**D → Customer: $60,000**

Total:

**$280,000**

Then:

**Customer → E: $100,000**

**Customer → F: $90,000**

**Customer → G: $70,000**

You need to understand:

### Source

Who sent the money?

### Purpose

Why?

### Relationship

How are they connected to the customer?

### Destination

Who received it?

### Velocity

How quickly did it move?

### Economic rationale

Does the overall flow make sense?

This can reveal patterns associated with:

* money mule activity
* layering
* fraud proceeds
* funnel accounts
* third-party payment activity
* trade-based schemes
* sanctions evasion
* other illicit finance typologies

---

# 6. Step Five — Don't confuse "unusual" with "suspicious"

This is one of the most important interview concepts.

Suppose a customer normally receives $5,000/month.

Suddenly they receive:

**$250,000.**

That's clearly unusual.

But you don't immediately conclude:

> "Money laundering."

The customer may have:

* sold a property
* received an inheritance
* sold a business
* received an insurance settlement
* received a legitimate investment payout
* received a documented loan

The investigation determines whether there is a credible explanation.

FinCEN's standard is based on knowledge, suspicion, or reason to suspect qualifying suspicious activity, including activity involving illegal proceeds, attempts to disguise such proceeds, BSA evasion, or transactions lacking a business or apparent lawful purpose where no reasonable explanation is identified after examining available facts. ([FinCEN.gov][2])

---

# 7. US vs UK: A very important distinction

You need to become comfortable switching between the two regulatory environments.

## 🇺🇸 United States

The suspicious activity reporting framework is centered around the **BSA/AML regime** and **FinCEN**.

For covered financial institutions, suspicious activity may lead to a **SAR filed with FinCEN**.

FinCEN's rules generally require reporting within the applicable regulatory timeframe after initial detection of reportable suspicious activity. Supporting documentation must also be maintained. ([FinCEN.gov][3])

For an analyst, think:

**Alert → Investigation → Suspicion determination → SAR decision/escalation → SAR narrative/supporting documentation**

---

## 🇬🇧 United Kingdom

The UK framework uses the **SAR regime administered by the UKFIU**, which sits within the National Crime Agency.

UK SARs are used to provide intelligence to law enforcement concerning suspected money laundering or terrorist financing. ([National Crime Agency][4])

The UK approach also has an important connection with:

* Proceeds of Crime Act 2002
* Money Laundering Regulations
* UKFIU
* NCA
* FCA expectations
* DAML/DATF concepts in appropriate cases

UK regulated-sector guidance states that where the legal reporting obligation applies, a SAR should be submitted as soon as practicable after suspicion is formed. ([GOV.UK][5])

### Interview shortcut

If asked:

**"What's the difference between US and UK suspicious activity reporting?"**

Think:

> **US → FinCEN SAR / BSA framework**

> **UK → UKFIU SAR / POCA framework**

Don't assume the underlying investigative logic is completely different. The analyst still needs to establish **who, what, why, source, destination, pattern, risk and evidence**.

---

# 8. Real-world US case — TD Bank

### FACTUAL CASE — not hypothetical

One of the most important Transaction Monitoring cases for you to study is **United States v. TD Bank**.

On **October 10, 2024**, the US Department of Justice announced that TD Bank pleaded guilty to violations involving its AML program and CTR obligations.

The case is extremely relevant to Transaction Monitoring.

According to DOJ, between 2014 and 2023 TD Bank failed to adequately update its AML program despite known risks.

More importantly for a Transaction Monitoring analyst:

> **From 2014 through 2022, TD Bank did not add new transaction-monitoring scenarios despite known deficiencies, emerging money-laundering risks, and new products/services.**

DOJ also stated that TD Bank excluded domestic ACH transactions, most check activity and other transaction types from automated monitoring.

The resulting gap meant approximately **92% of total transaction volume—about $18.3 trillion—was unmonitored between January 2018 and April 2024**.

Three money-laundering networks subsequently moved more than **$670 million** through TD Bank accounts between 2019 and 2023. ([Department of Justice][6])

### Why this case matters to YOU

This case teaches something extremely important:

> **Transaction Monitoring isn't only about investigating alerts. You must also understand what the monitoring system is NOT seeing.**

If a payment type is excluded from monitoring, there may be no alert to investigate.

Therefore:

**Incomplete transaction coverage = potential blind spot.**

This is a fantastic interview point.

If asked:

> "What makes an effective Transaction Monitoring system?"

Don't only say:

> "Good scenarios and thresholds."

Say:

> **"The institution needs complete and accurate transaction data coverage, appropriate risk-based scenarios, effective thresholds, periodic tuning and validation, and a process for identifying emerging risks."**

That is a much stronger answer.

---

# 9. Synthetic Investigation Case

### ⚠️ FICTIONALIZED — modeled on documented US/UK typologies

### Customer profile

**Customer:** Michael R.
**Location:** United States
**Age:** 27
**Occupation:** Freelance graphic designer
**Annual income:** $70,000
**Account:** Personal checking
**Account age:** 14 months

### Historical behaviour

Average monthly:

* Incoming: $4,500
* Outgoing: $3,800
* Counterparties: 8–12
* International transactions: None

---

## Alert-triggering activity

During 5 days:

**24 incoming transactions**

Total:

**$186,000**

Sources:

**19 unrelated individuals**

Then:

**$161,000 sent out**

Destinations:

* 8 different domestic accounts
* 3 international wires
* 2 cash withdrawals

### Alert trigger

> Rapid receipt and dispersal of funds involving numerous counterparties and activity materially inconsistent with historical customer behaviour.

---

# 10. Red flags

### 🔴 Profile mismatch

A freelance designer earning $70k has suddenly processed $186k in five days.

### 🔴 Multiple unrelated originators

19 people sending funds.

### 🔴 Rapid movement

Most funds leave shortly after receipt.

### 🔴 New beneficiaries

11 new destinations.

### 🔴 Cross-border activity

International transfers appear for the first time.

### 🔴 Low retention

The account retains little of the incoming funds.

None of these proves money laundering.

Together, however, they create a strong basis for further investigation.

---

# 11. Investigation plan

### Step 1 — KYC review

Check:

* occupation
* income
* expected activity
* account purpose
* risk rating

### Step 2 — Historical comparison

Compare:

**5-day alert period vs previous 12 months**

### Step 3 — Originator analysis

Determine:

* Are originators connected?
* Are there common addresses?
* Common phone numbers?
* Common businesses?
* Common devices/IPs where available?
* Are any known previously suspicious?

### Step 4 — Beneficiary analysis

Identify:

* who received the funds
* whether beneficiaries are related
* whether they are businesses
* whether they appear elsewhere in the institution's network

### Step 5 — Payment narrative analysis

Review:

* wire descriptions
* payment references
* memo fields
* invoices where available
* stated purposes

### Step 6 — Source-of-funds investigation

Ask:

> Where did the money originate?

### Step 7 — Purpose investigation

Ask:

> Why did 19 unrelated individuals pay this customer?

### Step 8 — Follow the money

Construct:

**Originators → Michael → Beneficiaries**

Look for network relationships.

---

# 12. Evidence you may request/review

Depending on the institution and investigation:

* invoices
* contracts
* employment/business documentation
* source-of-funds evidence
* explanation of relationships with counterparties
* payment purpose
* supporting correspondence
* account statements from relevant external accounts
* documentation supporting international transfers

FinCEN explicitly treats records such as transaction records, new-account information, correspondence and other records that helped the institution make its SAR determination as potential supporting documentation. ([FinCEN.gov][3])

---

# 13. Likely disposition

### Scenario A — Legitimate explanation

Customer demonstrates that they temporarily collected payments on behalf of a legitimate design agency, provides contracts/invoices, and counterparties can be independently connected to the business.

**Potential disposition:**

> Close / no further action, subject to institution policy and adequate documentation.

### Scenario B — Explanation unsupported

Customer cannot explain the counterparties, has no supporting documentation, funds are rapidly dispersed, and network analysis identifies links to other suspicious accounts.

**Potential disposition:**

> Escalate for further investigation and potential SAR reporting according to the institution's procedures.

Again:

**The alert doesn't determine the outcome. The evidence does.**

---

# 14. Today's Key Takeaways

### 1. Alert ≠ suspicious activity

An alert is an investigative starting point.

### 2. Establish the baseline

Know what normal looks like before deciding what unusual means.

### 3. Follow the money

**Source → Customer → Destination → Counterparty → Purpose**

### 4. Red flags are cumulative

One unusual transaction may have a legitimate explanation. Multiple unexplained indicators create a stronger concern.

### 5. Learn the US/UK reporting distinction

**US:** FinCEN / BSA / SAR

**UK:** UKFIU / NCA / SAR / POCA

---

# Interview Practice

### Q1. "Walk me through how you would investigate a Transaction Monitoring alert."

**Strong answer:**

> "First, I would understand the scenario and identify the transactions that triggered it. Then I would review the customer's KYC profile, expected activity and historical transaction behaviour. I would analyse the source and destination of funds, counterparties, transaction velocity, geography and payment channels. I would then look for a legitimate economic rationale and obtain or review supporting evidence where appropriate. Finally, I would document my findings objectively and determine whether the alert can be closed or needs escalation according to the firm's procedures."

---

### Q2. "Would you file a SAR simply because multiple red flags are present?"

**Strong answer:**

> "Not automatically. Red flags are indicators that require investigation. I would assess them collectively against the customer's profile, historical behaviour, transaction pattern and available evidence. If the investigation establishes the applicable level of suspicion under the firm's procedures and regulatory framework, I would escalate for SAR consideration."

That answer demonstrates **analytical judgment**, rather than simply memorizing:

> "Red flags = SAR."

---

### Q3. "What did the TD Bank case teach you about Transaction Monitoring?"

**Strong answer:**

> "It demonstrated that having a Transaction Monitoring system is not enough. Institutions need complete transaction coverage, appropriate and current monitoring scenarios, effective risk-based controls and governance. TD Bank had significant transaction types outside its automated monitoring, resulting in a major monitoring blind spot. For an analyst, it highlights the importance of understanding both what an alert detects and what activity may not be covered by the monitoring framework."

That is a **very strong interview answer** because you're connecting a real enforcement case to actual Transaction Monitoring operations.

---

## Today's study article

**Primary US source:** [U.S. Department of Justice — United States v. TD Bank, N.A.](https://www.justice.gov/criminal/case/united-states-america-v-td-bank-na?utm_source=chatgpt.com)

**US SAR guidance:** [FinCEN — Suspicious Activity Reporting Requirements](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2017-a003?utm_source=chatgpt.com)

**US SAR documentation:** [FinCEN — SAR Supporting Documentation](https://www.fincen.gov/resources/statutes-regulations/guidance/suspicious-activity-report-supporting-documentation?utm_source=chatgpt.com)

**UK SAR framework:** [National Crime Agency — Suspicious Activity Reports](https://www.nationalcrimeagency.gov.uk/what-we-do/crime-threats/money-laundering-and-illicit-finance/suspicious-activity-reports?utm_source=chatgpt.com)

**UK reporting guidance:** [HMRC — Reporting Suspicious Activity](https://www.gov.uk/hmrc-internal-manuals/economic-crime-supervision-handbook/ecsh34225?utm_source=chatgpt.com)

### One sentence to remember today

> **A Transaction Monitoring analyst does not investigate whether a transaction "looks suspicious"; they investigate whether the customer's overall activity is consistent with their known profile and whether the available evidence provides a reasonable explanation for the observed behaviour.**

[1]: https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2017-a007-0?utm_source=chatgpt.com "FinCEN Advisory FIN-2017-A007 | FinCEN.gov"
[2]: https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2017-a003?utm_source=chatgpt.com "FinCEN Advisory - FIN-2017-A003 | FinCEN.gov"
[3]: https://www.fincen.gov/resources/statutes-regulations/guidance/suspicious-activity-report-supporting-documentation?utm_source=chatgpt.com "Suspicious Activity Report Supporting Documentation | FinCEN.gov"
[4]: https://www.nationalcrimeagency.gov.uk/what-we-do/crime-threats/money-laundering-and-illicit-finance/suspicious-activity-reports?utm_source=chatgpt.com "Suspicious Activity Reports - National Crime Agency"
[5]: https://www.gov.uk/hmrc-internal-manuals/economic-crime-supervision-handbook/ecsh34225?utm_source=chatgpt.com "ECSH34225 - Suspicious activity reports - HMRC internal manual - GOV.UK"
[6]: https://www.justice.gov/criminal/case/united-states-america-v-td-bank-us-holding-company?utm_source=chatgpt.com "Criminal Division | United States of America v. TD Bank US Holding Company | United States Department of Justice"


 ## 1\. OFAC

 **OFAC = Office of Foreign Assets Control**

 OFAC is a department within the **U.S. Department of the Treasury**.

 ### What does OFAC do?

 OFAC administers and enforces **U.S. economic sanctions** against countries, organizations, companies, and individuals that the U.S. has designated under various sanctions programs.

 In simple words:

 > **OFAC helps ensure that U.S. persons and businesses do not conduct prohibited transactions with sanctioned people, organizations, or countries.**

 ### Example

 Suppose a company is processing an international payment.

 Before completing the payment, the company may check whether the people or organizations involved appear on a relevant U.S. sanctions list.

 If the transaction involves a sanctioned person, the company may have to **block or reject the transaction**, depending on the applicable sanctions program and circumstances.

 ### What is the OFAC SDN List?

 One important OFAC list is the:

 **SDN List = Specially Designated Nationals and Blocked Persons List**

 It contains individuals and entities that are subject to certain blocking sanctions.

 Financial institutions commonly screen:

 - Customers
- Beneficial owners
- Businesses
- Payments
- Vendors
- Other transaction parties

 against applicable sanctions lists.

 ### Important point

 OFAC is primarily about **sanctions**, rather than being a general AML regulator.

 Think:

 **OFAC → Sanctions → Who are we prohibited from dealing with?**

---

 # 2\. FATF

 **FATF = Financial Action Task Force**

 FATF is an **international organization** that develops global standards for fighting:

 - Money laundering
- Terrorist financing
- Financing of proliferation of weapons of mass destruction

 ### What does FATF do?

 FATF creates recommendations and standards that countries use to develop their AML/CFT systems.

 For example, FATF standards cover areas such as:

 - Customer Due Diligence (CDD)
- Beneficial ownership
- Suspicious transaction reporting
- Risk assessment
- Sanctions
- International cooperation
- Financial institution supervision

 ### Simple example

 Imagine 200 countries each had completely different approaches to money laundering.

 Criminals could exploit countries with weak controls.

 FATF tries to create a **common international framework** so countries can strengthen their systems and cooperate with each other.

 ### FATF Recommendations

 FATF has a set of international standards commonly referred to as the **FATF Recommendations**.

 They are often called the **"40 Recommendations."**

 They provide a framework for countries to establish effective AML/CFT systems.

 ### FATF does NOT normally work like a bank regulator

 FATF generally doesn't investigate your individual bank account.

 Instead, it evaluates how effectively **countries** implement AML/CFT standards.

 Think:

 **FATF → Global standards → How should countries fight financial crime?**

---

 # 3\. CFT

 **CFT = Combating the Financing of Terrorism**

 CFT means measures designed to prevent people or organizations from providing or moving money or other financial resources for **terrorist activities or terrorist organizations**.

 ### What is terrorist financing?

 In simple terms:

 > Terrorist financing involves providing, collecting, moving, or making available funds or other assets for terrorist activities or organizations, where prohibited by applicable law.

 ### AML vs CFT

 This distinction is very important.

 **AML** focuses primarily on preventing and detecting **money laundering**.

 Money laundering generally involves taking money connected to criminal activity and making it appear legitimate.

 **CFT** focuses on preventing money or assets from being used to support **terrorism or terrorist activity**.

 ### A major difference

 With money laundering, the money is often generated **illegally first**.

 For example:

 > Drug trafficking → illegal proceeds → money laundering

 With terrorist financing, the money can come from **legitimate or illegitimate sources**, depending on the circumstances.

 For example:

 > Legitimate income/donation → funds diverted to terrorist activity

 Therefore:

 **AML asks:**\
 "Could this money be proceeds of crime?"

 **CFT asks:**\
 "Could this money be supporting terrorism?"

 ### CFT controls can include:

 - Customer identification
- Transaction monitoring
- Sanctions screening
- Suspicious transaction reporting
- Beneficial ownership checks
- Monitoring unusual transfers
- Screening against relevant terrorist-designation lists

 Think:

 **CFT → Prevent money/resources from reaching terrorist activities or organizations.**

---

 # 4\. BSA

 **BSA = Bank Secrecy Act**

 The Bank Secrecy Act is a major **U.S. federal law** concerning financial records and reporting designed to help government authorities detect and prevent financial crimes, including money laundering.

 It was enacted in **1970** and has been amended by subsequent laws.

 ### What does the BSA require?

 Among other things, covered financial institutions have obligations involving:

 - Recordkeeping
- Reporting certain transactions
- Customer identification and due diligence
- Suspicious Activity Reports (SARs)
- Currency Transaction Reports (CTRs)
- AML programs

 ### Example: CTR

 A **Currency Transaction Report (CTR)** is generally required for certain cash transactions **over $10,000 in a business day**.

 For example:

 A customer deposits $15,000 in cash.

 The bank may have a CTR reporting obligation.

 ### Example: SAR

 A **Suspicious Activity Report (SAR)** is used by covered financial institutions to report potentially suspicious activity to the U.S. government.

 For example, suppose a customer's transactions appear structured to avoid reporting requirements.

 The bank may investigate and, where the legal requirements are met, file a SAR.

 ### Who administers BSA requirements?

 The **Financial Crimes Enforcement Network (FinCEN)**, a bureau of the U.S. Treasury Department, plays a central role in administering and enforcing the BSA.

 Think:

 **BSA → U.S. law → Financial reporting and AML requirements**

---

 # 5\. USA PATRIOT Act

 **USA PATRIOT Act = Uniting and Strengthening America by Providing Appropriate Tools Required to Intercept and Obstruct Terrorism Act**

 It was enacted in the United States in **2001**, following the September 11 terrorist attacks.

 It covers many areas related to national security and law enforcement.

 For AML/CFT, one particularly important part is **Title III**, which strengthened U.S. measures against money laundering and terrorist financing.

---

 ## What did the USA PATRIOT Act do for financial institutions?

 It strengthened requirements concerning areas such as:

 - Customer identification
- AML programs
- Correspondent banking
- Foreign financial institutions
- Suspicious financial activity
- Information sharing
- Terrorist financing

 ### Customer Identification Program (CIP)

 One important concept is the **Customer Identification Program**.

 Banks generally need procedures to obtain and verify information about customers when establishing accounts.

 For example, a bank may collect information such as:

 - Name
- Date of birth
- Address
- Identification number/document information

 The purpose is to help the institution understand **who the customer actually is**.

 Think:

 **USA PATRIOT Act → Strengthened U.S. AML/CFT framework, especially after 9/11.**

---

 # How are all five connected?

 This is the most important part to understand.

 Imagine a bank receives an international transaction.

 The bank may have to consider several different areas:

 ### Step 1 — Identify the customer

 The bank needs to know who its customer is.

 This relates to **KYC/CDD** and U.S. requirements including the BSA and USA PATRIOT Act.

 ↓

 ### Step 2 — Understand the customer's risk

 The bank considers factors such as:

 - Customer type
- Business activity
- Geography
- Products/services
- Transaction behavior

 ↓

 ### Step 3 — Monitor transactions

 The bank looks for unusual or potentially suspicious activity.

 This is strongly connected with **BSA/AML requirements**.

 ↓

 ### Step 4 — Check sanctions

 The bank checks relevant sanctions information.

 This is where **OFAC** becomes particularly important.

 ↓

 ### Step 5 — Consider terrorist financing

 The institution considers whether activity could involve terrorist financing.

 This relates to **CFT**.

 ↓

 ### Step 6 — Follow international standards

 The country's AML/CFT framework is influenced by international standards developed by **FATF**.

---

 # Easy way to remember them

 | Term | Full form | Main idea |
| --- | --- | --- |
| **OFAC** | Office of Foreign Assets Control | 🇺🇸 **Sanctions** |
| **FATF** | Financial Action Task Force | 🌎 **Global AML/CFT standards** |
| **CFT** | Combating the Financing of Terrorism | 🚫 **Stop terrorist financing** |
| **BSA** | Bank Secrecy Act | 🇺🇸 **U.S. AML/reporting law** |
| **USA PATRIOT Act** | Uniting and Strengthening America by Providing Appropriate Tools Required to Intercept and Obstruct Terrorism Act | 🇺🇸 **Strengthened AML/CFT and national-security measures** |

## One-line memory trick

 **OFAC = Sanctions**\
 **FATF = Global standards**\
 **CFT = Stop terrorist financing**\
 **BSA = U.S. AML law/reporting**\
 **PATRIOT Act = Strengthened U.S. AML/CFT framework**

 ### A simple real-world example

 Suppose **ABC Bank** in the U.S. has a customer who sends an international payment.

 ABC Bank might:

 **1\. Identify the customer** → KYC/CIP\
 **2\. Understand the customer's risk** → CDD\
 **3\. Monitor the transaction** → AML/BSA\
 **4\. Check applicable sanctions** → OFAC\
 **5\. Look for potential terrorist financing** → CFT\
 **6\. File a SAR if legally required** → BSA\
 **7\. Operate within the broader international AML/CFT framework** → FATF standards

 So, these aren't five completely separate concepts. They are **different pieces of the broader financial-crime compliance system**.


 FATF 40 RECOMMENDATIONS 

 https://www.linkedin.com/posts/muhammadshakil1_fatf-40-recommendations-at-a-glance-money-activity-7479101382428397568-E2kd
