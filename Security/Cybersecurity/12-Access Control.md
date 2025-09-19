IAM (Identity and Access management)
Security controls that manage access, authorizatation, and accountability of information.

To maintain CIA triad (confidentiality, Integrity, Availability)

## AAA Framework
- Authentication
- Authorization
- Accounting

### Authentication
How Are You

Factor of authentication:
1. Knowledge: something the user knows
	1. Password, or security question
2. Ownership: something the user possesses
	1. OTP (On Time Password)
3. Characteristic: something the user is
	1. Biometrics (Finger print or facial scan)

### User Provisioning
Is the process of creating and maintaining user's digital identity
### User deprovision
Is the practice that removes a user's access rights when they should no longer have them.

To make access systems more convenient, these days:
#### Single Sign-On (SSO)
Is a technology that combines several different logins into one.

It is automating how trust is established between a user and a service provider.
it uses 2 different authentication protocols:
1. LDAP (Lightweight Directory Access Protocol)
	1. Used for transmission on-premises.
2. SAML (Security Assertion Markup Language)
	1. Used for transmission off-premises.

Risk of SSO when using a single form of authentication
#### Multi-factor authentication (MFA)
A security measure which requires a user to verify their identity in two or more ways to access a system or network.
Using the AAA framework:

### Authentication
- Something the user know (username, password)
- Something the user has (OTP)
- Something the user is (fingerprint)

### Authorization
Assigning responsibility for certain systems and processes.
It determines what the user allow to do.

- Least privilege
	- Access to data is only less as long as needed.
- Separated duets
	- User should not be given levels of authorization that would allow them to misuse a system.

Authorization over network there are two access protocols:
- HTTP/s basic auth
- OAuth

HTTPs (Hybertext transfer protocol secure) uses basic auth to establish a user's request to access a server.

**OAuth** An Open-standard authorization protocol that shares designated access between applications, using API token.

API token
A small block of encrypted code that contains information about a user.
- Identity
- Site permission
- ...

#### Granting Authotization
There are 3 common frameworks that organizations use to handle this step:
- Mandatory Access Control (MAC) (non-discretinoary AC)
	- Access to information must be granted manually by a central authority.
- Discretionary Access Control (DAC)
	- Data owner decides appropriate levels of access
- Role-based Access Control (RBAC)
	- Authorization is determined by a user's role within an organization.

- [IDPro](https://idpro.org/)© is a professional organization dedicated to sharing essential IAM industry knowledge.
### Accounting
Is the practice of monitoring the access logs of a system.
These logs contain information like who accessed the system, and why, and what resources they used.

Anytime a user accesses a system they initiate a session

#### A Session
is a sequence of network HTTP basic auth requests and responses associated with the same user.

- Create Session ID : a unique token that identifies a user and their device while accessing the system.
- Exchange of session cookies: which is a token that websites use to validate a session and determine how long that session should last.

##### Session Hijacking
An attacker can impersonate a user using their stolen cookie (session token).
It is when attacker obtain a legitimate user's session ID.