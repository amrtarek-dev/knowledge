As an analyst, you'll detect and respond to incidents and implement actions for recovery.

NIST incident response lifecycle is another NIST framework with additional substeps dedicated to incident response.
- **Preparation**
- **Detection &Analysis**
- **Containment Eradication & Recovery**
- **Post-incident activity**

## Incident
According to NIST it is an occurrence that actually or imminently jeopardizes, without lawful authority, the confidentiality, integrity, or availability of information or an information system or constitutes a violation or imminent threat of violation of law, security policies, security procedures, or acceptable use policies.

> All security incident are events but not all events security incidents

Incident investigation reveals critical information about the five W's of incident:
1. Who triggered
2. What happened
3. When it took place
4. Where it took place
5. Why the incident occurred

A great way to document these questions is using the incident handler's journal

### Incident handler Journal
Is a form documentation used in incident response to answer the 5 w's.

### CSIRT
Computer Security incident response teams
A specialized group of security professionals that are trained in incident management and response.

- Effectively and efficiently manage incidents
- Provide services and resources for response
- Recovery and prevent future incidents

For incident response to be effective and efficient, there must be clear **command**,**control**, and **communication** of the situation to achieve the desired goal. 

- **Command** refers to having the appropriate leadership and direction to oversee the response.
- **Control** refers to the ability to manage technical aspects during incident response, like coordinating resources and assigning tasks.
- **Communication** refers to the ability to keep stakeholders informed.

Some regulatory compliance measures may require organizations to publicly disclose a security incident within a certain timeframe (48 hours).

Positions in CSIRT:
- Security Analyst
- Technical lead
- Incident coordinators


### **Security analyst**
The job of the **security** **analyst** is to continuously monitor an environment for any security threats. This includes: 
- Analyzing and triaging alerts
- Performing root-cause investigations
- Escalating or resolving alerts 

If a critical threat is identified, then analysts escalate it to the appropriate team lead, such as the technical lead.
### **Technical lead**
The job of the technical lead is to manage all of the technical aspects of the incident response process, such as applying software patches or updates.

They do this by first determining the root cause of the incident. Then, they create and implement the strategies for containing, eradicating, and recovering from the incident.

Technical leads often collaborate with other teams to ensure their incident response priorities align with business priorities, such as reducing disruptions for customers or returning to normal operations. 
### **Incident coordinator**
Responding to an incident also requires cross-collaboration with nonsecurity professionals.

CSIRTs will often consult with and leverage the expertise of members from external departments.

The job of the incident coordinator is to coordinate with the relevant departments during a security incident.

By doing so, the lines of communication are open and clear, and all personnel are made aware of the incident status. Incident coordinators can also be found in other teams, like the SOC. 
### **Other roles**
Depending on the organization, many other roles can be found in a CSIRT, including a dedicated communications lead, a legal lead, a planning lead, and more. 

**Note**: Teams, roles, responsibilities, and organizational structures can differ for each company. For example, some different job titles for incident coordinator include incident commander and incident manager.

## Incident Response plans
Regulations may require organizations to report incidents within a certain timeframe, so it is crucial for organization to have a formal incident response plan in place.

it is a document that outlines the procedures to take in each step of incident response.
Elements of an incident plan:
- Incident response procedures: Step by step instructions on how to response to incidents.
- System information: Network diagram, data flow diagram, logging, and asset inventory information.
- Other documents: Contact lists, forms and templates.



## Documentation
- Playbooks: A manual that provides details about any operational action.
- Incident handler's journals
- policies
- Plans
- Final reports