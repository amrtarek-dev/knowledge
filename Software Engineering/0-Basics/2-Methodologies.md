
- Waterfall
- V-Model
- Agile methodology
- big bang model
- spiral model
- Rapid model
- Prototyping model


The most common 3 methods:
- Waterfall
- V-Shape model
- Agile methods
There are many ways to approach software development.

## Waterfall model

It is a sequential method of software development where the output of one phase is the input for the next phase of the cycle.

``` markdown
-| Plan (Requirements)
--| Design
---| Development
----| Testing
-----| Deployment
------| Maintenance
```

It is not flexible, if there is a new requirements you will start the model from beginning.

- Easier to estimate budget and allocate resources
- lacks flexibility and change is hard to accommodate.
## V-Model

The V-shape model is named as such because the phases form the shape of a V.

The phases going down the left of the V are called `verification` then going up the right side of the v `validation`

There are 4 stages that occur on each side of the V.
``` markdown
-| Plan            -----> Acceptance Testing
--| System Design  ----> System Testing
---| Architecture Design ---> Interation Testing
----| module Design  --> Unit Testing 
-------| Coding | ------
```

``` markdown
Developer's Life Cycle.  Tester's Life Cycle
-| Business Req. Specs -----> Acceptance Testing
--| System Req. Specs  ----> System Integration Testing
---| High Level Design ---> Component Testing
----| Low Level Design --> Unit Testing 
-----| Coding | ----
```

- Test plans designed upfront saves development and testing time.
- Rigid, and does not accommodate changing requirements.
## Agile Methodology

It is called an iterative approach to development, it is aligns with the SDLC but each phase is short.

Teams work in cycles, or sprints which usually one to four weeks long.
Unit testing happens in each sprint to minimize the risk of failure.

At the end of each sprint, a chunk of working code is released at a meeting called the "sprint demo" where stakeholders can see the new functionality and provide feedback.


``` markdown
.          -> | Plan |->| Design |
             /                    \
 | Feedback |                      | Develop |
             \                    /
              | Deploy |<-| Test |
```

``` markdown
.       -> | Plan |->| Design |
           /                   \
 | Review |                     | Develop |
           \                   /
 Launch <- | Deploy |<-| Test |
```

It works in sprints which always start with plaining for the new requirements, then design, develop, test, deploy the small feature, then takes the new features in prints until launching.

After several sprint cycles, a minimum viable product (MVP) is developed so stakeholders can provide feedback on the basic feature set.

- Changing requirements handled easily, feedback incorporated regularly.
- Budgeting and resource allocation is challenging, because the project scope not clearly defined.

### 4 Core values of Agile development
they outlined in what called `Agile manifesto`
- Individuals and interactions over process and tools.
- Working software over comprehensive documentation.
- Customer collaboration over contract negotiation.
- Responding to change over following a plan.

> Waterfall and V-Shape model are sequential