Security plans are based on the analysis of three elements:
1. Assets
2. Threats
3. Vulnerabilities
can effect on confidentiality, integrity, and availability of information systems.

**Risk**: Anything that can impact the confidentiality, integrity, or availability of an assets.

**Assets**: is an item perceived as having value to an organization.
	- Digital Assets
	- Physical Assets
	- Intangible Assets (brand reputation, intellectual property)

**Threats**: is any circumstance or event that can negatively impact assets.

**Asset management** is the process of tracking assets and the risks that effects them.
- **Asset inventory**: A catalog of assets that need to be protected
- **Asset Classification**: The practice of labeling assets based on sensitivity and importance to an organization.
	- Public (shared with anyone)
	- internal-only (shared with anyone in the orgainzation)
	- confidential (Specific group team)
	- restricted (Specific small group)

### Digital Assets
- Data: Information that is translated, processed, or stored by a computer.
State of data:
- In use (Been accessed by one or more users).
- In transit (Traveling from one point to another).
- At rest (currently not being accessed).


**Vulnerability**: is a weakness that can be exploited by a threat.

## Risk Factors
- Threats
	- Intentional (hacker)
	- Unintentional (employee opens door to someone else)
- Vulnerabilities
	- Technical (misconfiguration)
	- human (employee loses their access card)

A fundamental truth of security is you can only protect the things you account for.
#### Information Security (InfoSec)
The practice of keeping data in all states away from unauthorized users.

## Security Plan
The purpose of the security plan is mitigate the risks

Risk categories:
- Damage
- Disclosure
- Loss of information

To do so the security plan uses 3 elements:
1. Policies: a set of rules to reduce risk and protects information.
	1. Acceptable use policy (AUP)
2. Standards: Are reference to how to set policies.
	1. Password must be 8 characters long (NIST Special Publication 800-63B)
3. Procedures: Step by step instructions to perform a specific security task.
	1. Steps for employees can securely reset a password.


After the security plan is ready there is another part called compliance.

#### Compliance
Is the process of adhering to internal standards and external regulations.

Meeting compliance standards is usually a continual, two-part process of security audits and assessments:
- A **security audit** is a review of an organization's security controls, policies, and procedures against a set of expectations.
- A **security assessment** is a check to determine how resilient current security implementations are against threats.

#### Regulations
Rules set by a government or other authority to control the way something is done.

#### NIST (National Institute of Standard and Technology) Cybersecurity Framework (CSF):
is a voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk.
It has 3 components:
1. Core: A simplified version of the functions, duties of a security plan. the 5 functions:
	1. Identify
	2. Protect
	3. Detect
	4. Respond
	5. Recover
2. Tiers: Provide security teams with a way to measure performance across each of five functions of core, range from level-1 to 4
	1. level-1 (Passive): indicates a function is reaching bare minimum standards.
	2. level-2
	3. level-3
	4. level-4 (Adaptive): indicates that a function is being performed at an exemplary standard.
3. Profiles: Provide insights into the current state of a security plan. (photo capturing a moment of time.)


#### CISA (Cybersecurity and Infrastructure Security Agency)
it provide detailed guidance that any organization can use to implement the CSF.
- **Create a current profile** of the security operations and outline the specific needs of your business.
- **Perform a risk assessment** to identify which of your current operations are meeting business and regulatory standards.
- **Analyze and prioritize existing gaps** in security operations that place the businesses assets at risk.
- **Implement a plan of action** to achieve your organization’s goals and objectives.

> Always consider current risk, threat, and vulnerability trends when using the NIST CSF.

## Security Controls
Are the safeguards designed to reduce specific security risks.
- Technical
- Operational
- Managerial

Technical control types include the many technologies used to protect assets (Encryption, authentication systems, and others).

Operational controls include maintaining the day-to-day security environment (For people). (awareness training and incident response).

Managerial controls are centered around how the other two reduce risks (policies, standards, procedures)

### Information privacy
The protection from the unauthorized access and distribution of data.

### Information security (InfoSec)
The practice of keeping data in all states away from unauthorized users.

The key difference: Privacy is about providing people with control over their personal information and how it's shared. Security is about protecting people’s choices and keeping their information safe from potential threats.

#### Security controls 
are the technologies used to regulate information privacy.

#### Separation of duties
Divides tasks and responsibilities among different users to prevent giving a single user complete control over critical business functions.

#### Principle of least privilege (NIST SP 800-53: AC-6)
The concept of granting only the minimal access and authorization required to complete a task or function.
- Limiting access to sensitive information
- Reducing the chances of accidental data modification, tampering, or loss
- Supporting system monitoring and administration

Which relay of differentiating between 
- data owners 
- data custodians.

##### Data Owners
the person that decides who can access, edit, use, or destroy their information.

##### Data custodian
Anyone or anything that's responsible for the safe handling, transport, and storage of information. (people, organizations, their systems)

##### Privilege creep
Users accumulate more access privileges than they need over time.
Prevent it by privilege audits

##### Account change audits
Account directory service keep records and logs associated with each user 
- Directory service can be configured to alert system administrator of suspicious activity.

## Data Lifecycle
It is an important model that security teams consider when protecting information. It influences how they set policies that align with business objectives.
- Collect
- Store
- Use
- Archive
- Destroy

### Data Governance
It is a set of processes that define how an organization manages information. To keep data private, accurate, available and secure throughout its lifecycle.
Data governance policies commonly categorize individuals into a specific role:
- **Data owner:** the person that decides who can access, edit, use, or destroy their information.
- **Data custodian**: anyone or anything that's responsible for the safe handling, transport, and storage of information.
- **Data steward**: the person or group that maintains and implements data governance policies set by an organization.

Governments and other regulatory agencies have bridged this gap by creating rules that specify the types of information that organizations must protect by default:

- **PII** (Personally identifiable information) refers to information that can be used to contact or locate someone.
- **SPII** (Sensitive Personally identifiable information) falls under stricter handling guidelines that should only be accessed on a need-to-know basis, such as a bank account number or login credentials.
- **PHI** (Protected Health Information) information that relates to the past, present, or future physical or mental health or condition of an individual.
	- In USA: HIPAA (Health Insurance Portability and Accountability Act).
	- In EU: GDPR (General Data Protection Regulation)
	- PCI DSS: (Payment Card Industry Data Security Standard)


