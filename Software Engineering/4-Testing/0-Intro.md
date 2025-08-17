## Software testing
It is the practice of integrating quality checks throughout the software development cycle.

The of testing is to check whether the software matches expected requirements and ensure error-free software.

To test software, the team write test cases.

### Test cases
it is written to verify the functionality of the software application and insure requirements has been satisfied.

It contains:
- Inputs
- Steps
- Data
- Expected output

It should be written after requirements are finalised.

### Types of software testing

- Functional Testing
- Non-Functional Testing
- Regression Testing.

#### Functional testing:
- Black Box testing (without looking to the source code or internal structure), just input and output.
- Manually or using tools
- To be sure the application usable and accessible.

#### Non-functional testing:
to test the system attributes like:
- Performance
- Security
- Scalability
- Availability
to see if the SUTs (software under test) behavior is performing properly.

should answer:
- How does the application behave under stress?
- What happens when many users log in at the same time?
- Are instructions consistent with behavior?
- How does the application behave under different OSs?
- How does the application handle disaster recovery?
- How secure is the application?

#### Regression Testing
Confirms changes don't break the already existing functionality.


## Testing Levels
- Unit
- Integration 
- System
- Acceptance


### Unit testing
To test a module of code for functionality. usually at the function level.

Performed by the software developer or engineer during the build phase.

Eliminate errors before integration with other modules.

### Integration testing
Identify errors introduced when 2 or more modules are combined.

It is type of black-box test (input-output)

Performed by engineer after combine modules into the larger application

### System Testing
After integration testing to evaluate system compliance to specified requirements.

It validate the system as a fully complete software product.

Functional and Non-functional.
And it should be on staging environment, which should be similar to the production environment.

### Acceptance Testing
It is formal testing with respect to user needs, requirements and business processes.

It determines whether a system satisfies the needs of the users, customers, and other stakeholders.

Usually done by the customer or the stakeholders during the maintenance stage of the SDLC.