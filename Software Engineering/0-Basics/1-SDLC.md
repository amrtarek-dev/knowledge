
## SDLC
The adaption of the the scientific approach to software development has influenced the way software is created and designed.

Today the development process is typically guided by the **Software Development Lifecycle** or SDLC.
Which is identifies the steps needed to develop high quality software.

It is a systematic process defines the steps needed to develop high-quality software in a predictable timeframe and budget. Which aims to produce software that meets the requirements.

It is a cycle of planning, design, and development which initially used the waterfall method (a linear pattern), then it adapted to use iterative methods in response to address the customer needs and shifting requirements.

Advantages
- A **process to follow** rather than the ad hoc approach for development team which improves efficiency and reduce risks.
- A **discrete phases** which Team members know what they should be working on and when.
	- which Facilitates communication among stakeholders.
	- Team members know when development can move to the next phase.
- Iterative way enables respond to changing requirements.
	- Solve problems early in the process
- Each team member has a well defined role, which Reduces conflicts and overlapping responsibilities.


### 6 Phases of SDLC:
1. Planning (Requirements, or analysis)
2. Design
3. Development
4. Testing
5. Deployment
6. Maintenance

Each phase is discrete, meaning that tasks from previous phase do not overlap with tasks in the next phase.
#### 1. Planning Phase:
In this phase the requirements are gathered, analyzed, documented, and prioritized, with consideration of users of the solution, purpose, data input/output, regulations & compliance, Risk Identification, Quality assurance requirements, allocation of human and financial resources, and project scheduling.

- If the stack holders are struggling to define the requirements, often the development team may produce **prototype** during the planning phase to tease out those requirements.
- Prototype is a small-scale replica of the end product used to get stakeholder feedback and establish requirements.
	- To test basic design ideas
	- And it can be developed at various stages of the SDLC.

The Output of this phase is a **software requirements specification (SRS)** which where the requirements are documented in, and all stakeholders must agree

### SRS
Software requirements specifications is the process of collecting and documenting the set of requirements that the software needs to adhere to.
It may include a set of use cases that describe the business needs and user flows that the software must implement.

SRS  are 4 categories:
- Functional: Functions of the software
- External & user interface: Users and interactions with other hardware or software.
- System features: Functions of the system
- Nonfunctional: performance, safety, security, quality.


#### 2. Design Phase: (Requirements to Architecture)
In this phase the **requirements** are gathered from the SRS to develop an **architecture** by breaking down requirements into sets of related components.

It is the process of transforming the requirements into a structure that is implementable using code.

The Technical lead breaks down the requirements into sets of related components, these components defines the system architecture.

The design communicate business rules and application logic, application programming interface design, which is how apps talk to each other or communicate with the database, user interface and database design.

The Output of this phase is the Design document.

#### 3. Development Phase: (Design document to code)
some times it called Build, or implementation phase.
In this phase the project planner uses the Design document to determine and assign coding tasks, and the development team implement the system.
- Using of programming tools, different programming languages, and software stacks.
- Use standards or guidelines that need to be followed.

Coding quality:
- Maintainability
- Readability
- Testability
- Security

Quality code must fulfill the intended requirements of the software without defects.
- Must be clean and consistent
- Easy to read and maintain
- Well documented
- Efficient
by 
- Following coding standards
- Using linters to detect programmatic and stylistic errors.
- Commenting in the code itself to make it easy to understand and modify.

#### 4. Testing
The code is tested to ensure 
Reliability, **stability**, **security**, and efficiency, 
and that it meets requirements from the SRS.
- Manual
- Automated
- Hybrid (Manual and Automated)

It is the process of verifying that the software matches established requirements and is free of bugs.

The output is usually a Bugs reported, tracked, fixed, and retested by:
- Unit testing
	- By the developer, it test the smallest component of code that can be isolated from the rest of the system.
- Integration testing
	- Once the components are integrated into larger product.
- System testing
	- After larger product is deemed completed
- Acceptance testing
	- User Accepting Testing (UAT) or **beta** testing, when the software is tested by the intended end user.

Types of testing categories:
- Functional
- Non-functional
- Regression

#### 5. Deployment Phase
Once the project passes the User Acceptance Testing (UAT), the software is released on the web or app store.

Where the application is release into the production environment and made available to uses.

Types of Releases are intended for different audiences:
- **Alpha**: for a select group of stakeholders.
	- May contain errors, and may not the full features.
- **Beta** (or limited release): Is given to the stakeholders outside of the developing organization.
	- To try out the software in real conditions, test the functionality, and identify any outstanding bugs or errors.
- **GA** (General Availability): Stable version for all users.

### Documentation:
- System documentation:
It is for technical users (engineers, developers, or architects).
To Explain how the software operates or how to use it.
It consists of README files, inline comments, architecture and design documents, verification information, and maintenance guides.
- User documentation:
For non-technical users.
To assist them in the use of the product.
In form of user guides, instructional videos and manuals, online help, and inline help.

#### 6. Maintenance Phase
It happens once the code has been deployed into a production environment to find:
- any other bugs, 
- identify user interface (UI) issues, 
- and identify other requirements that may not have been listed in the SRS.
If bugs are discovered in this phase that were missed during testing, these errors may need to be fixed for high-priority issues or incorporated into the requirements as part of a future software release and the process can start again.
