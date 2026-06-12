# System Analysis & Design — Test 1
## Questions and Answers Study Guide

---

## SECTION 1: SYSTEM ANALYSIS & DESIGN OVERVIEW

### Question 1: Define System
**Q: What is a system?**

A: A system is a collection of interrelated components (parts) that work together to achieve a common objective or goal. Example: A banking system has hardware, software, people, and processes working together to manage bank operations.

---

### Question 2: Define System Analysis
**Q: What is System Analysis?**

A: System Analysis is the process of examining an existing or proposed system to understand the problems, requirements, and possible solutions. It answers the question: "What is the problem?" System analysts study how the current system works and what users need.

---

### Question 3: Define System Design
**Q: What is System Design?**

A: System Design is the process of planning how to build a new system based on the requirements identified during analysis. It answers the question: "How will we build it?" Designers create blueprints and specifications for the system.

---

### Question 4: Difference Between Analysis and Design
**Q: What is the key difference between System Analysis and System Design?**

A: 
- **System Analysis**: Focuses on understanding the PROBLEM and gathering REQUIREMENTS. (What is needed?)
- **System Design**: Focuses on creating the SOLUTION and planning HOW to build it. (How will it be built?)

Analysis = "What?" | Design = "How?"

---

### Question 5: What are the main roles in System Development?
**Q: Name and explain at least 4 key roles in system development.**

A:
1. **System Analyst** — Studies user needs, identifies problems, and proposes solutions. Bridge between users and developers.
2. **Stakeholder** — Any person affected by the system (users, managers, executives, customers).
3. **System User (End User)** — The person who uses the system daily (data entry clerk, customer, etc.).
4. **Developer/Programmer** — Writes code and implements the system based on design specifications.
5. **Project Manager** — Oversees the project timeline, budget, and team coordination.

---

### Question 6: Types of Systems
**Q: Explain the difference between Open and Closed systems, and Formal and Informal systems.**

A:

**Open vs Closed Systems:**
- **Open System** — Interacts with its external environment. Example: A business system that receives data from suppliers and sends data to customers.
- **Closed System** — Does not interact with its external environment. It operates in isolation. Example: A standalone calculator with no internet.

**Formal vs Informal Systems:**
- **Formal System** — Has documented rules, procedures, and structure. Example: A banking system with written policies.
- **Informal System** — No documented procedures; relies on customs and traditions. Example: An unwritten office tradition.

---

### Question 7: Components of a System
**Q: List and explain the 7 main components of a system.**

A:
1. **Input** — Data or resources that enter the system.
2. **Process** — The operations/work performed on the input.
3. **Output** — The result or product of the process.
4. **Feedback** — Information about output quality that helps improve the system.
5. **Control** — Mechanisms that manage and regulate the system's operation.
6. **Boundary** — The line that separates the system from its environment.
7. **Environment** — Everything outside the system that can affect it.

**Basic Flow**: Input → Process → Output, with Feedback returning to improve future processes.

---

### Question 8: Characteristics of a Good System
**Q: What characteristics should a well-designed system have?**

A:
1. **Reliability** — Works correctly and consistently.
2. **Accuracy** — Produces correct results.
3. **Efficiency** — Uses resources optimally (time, money, effort).
4. **Security** — Protects data from unauthorized access.
5. **Scalability** — Can grow or adapt to future needs.
6. **Usability** — Easy for users to understand and operate.
7. **Maintainability** — Easy to update and fix.

---

## SECTION 2: SYSTEM DEVELOPMENT LIFE CYCLE (SDLC)

### Question 9: Define SDLC
**Q: What is the System Development Life Cycle (SDLC)?**

A: The SDLC is a structured process that guides the creation, planning, development, testing, and maintenance of information systems. It provides a framework to ensure systems are built efficiently, reliably, and meet user needs. It typically has 7 phases: Planning, Analysis, Design, Implementation, Testing, Deployment, and Maintenance.

---

### Question 10: The 7 Phases of SDLC
**Q: List and explain the 7 phases of SDLC in order.**

A:

**1. Planning (Upangaji)**
- Define project objectives, scope, timeline, budget, and resources.
- Conduct a feasibility study to determine if the project is viable.
- Identify stakeholders and risks.

**2. System Analysis (Uchambuzi)**
- Gather requirements from users and stakeholders.
- Study the current system and identify problems.
- Methods: Interviews, questionnaires, observation, document review.
- Output: Requirements specification document.

**3. System Design (Muundo)**
- Create detailed plans for the new system.
- Decide on architecture, database structure, user interface.
- Two types: Logical Design (what it will do) and Physical Design (how it will do it).

**4. Implementation (Utekelezaji)**
- Purchase hardware and software.
- Write and test code.
- Set up the system environment.
- Programmers do the actual coding.

**5. Testing (Majaribio)**
- Check if the system works correctly.
- Types: Unit testing → Integration testing → System testing → User Acceptance Testing (UAT).
- Find and fix bugs before deployment.

**6. Deployment (Uwekaji)**
- Install the system in the real environment.
- Train users on how to use the system.
- Transfer data from old system if applicable.
- Conversion methods: Parallel, Direct cutover, Phased, Pilot.

**7. Maintenance (Utunzaji)**
- Fix bugs discovered after deployment.
- Make improvements and add new features.
- Provide user support and updates.
- Continues throughout the system's life.

---

### Question 11: Feasibility Study
**Q: What is a feasibility study and what are its 5 types?**

A: A feasibility study is an analysis conducted during the planning phase to determine whether a project is viable and should proceed.

**The 5 Types of Feasibility:**

1. **Technical Feasibility** — Is the required technology available? Do we have the skills and tools to build it?

2. **Economic Feasibility** — Is the cost justified? Will the benefits outweigh the costs? Good ROI (Return on Investment)?

3. **Operational Feasibility** — Can users operate and maintain this system? Will they accept it?

4. **Legal Feasibility** — Does the system comply with laws and regulations? Are there legal risks?

5. **Schedule Feasibility** — Can the project be completed within the required timeframe? Are deadlines realistic?

---

### Question 12: What is a Requirements Specification?
**Q: Explain what a requirements specification document is and why it's important.**

A: A requirements specification (or requirements document) is a detailed description of what the system must do. It is created after the analysis phase and before design begins.

**Content:**
- Functional requirements (what the system must do)
- Non-functional requirements (performance, security, usability)
- User roles and permissions
- Data requirements
- System constraints

**Why Important:**
- Provides a clear blueprint for designers and developers
- Prevents miscommunication between users and developers
- Serves as a contract between the client and development team
- Used to verify that the final system meets all requirements

---

### Question 13: Data Gathering Methods in System Analysis
**Q: List and explain 4 methods of gathering requirements during system analysis.**

A:

1. **Interviews** — Meeting directly with users and stakeholders to ask questions about their needs and current processes. Advantage: Detailed, personal information. Disadvantage: Time-consuming.

2. **Questionnaires** — Written surveys sent to many users to gather information. Advantage: Can reach many people. Disadvantage: May have low response rate, less detail.

3. **Observation** — Watching how users currently work and what problems they face. Advantage: See actual workflow. Disadvantage: People may behave differently when observed.

4. **Document Review** — Examining existing documents, manuals, and reports to understand current systems. Advantage: Factual, historical data. Disadvantage: Documents may be outdated.

Other methods: Focus groups, prototyping, case studies.

---

## SECTION 3: SDLC MODELS

### Question 14: Waterfall Model
**Q: Describe the Waterfall model. What are its advantages and disadvantages?**

A: The Waterfall model is a sequential SDLC approach where each phase must be completed before the next begins. You move from one phase downward to the next, like water falling.

**Phases Flow**: Planning → Analysis → Design → Implementation → Testing → Deployment → Maintenance

**Advantages:**
- Simple and easy to understand
- Clear documentation at each stage
- Easy to manage and track progress
- Works well for small projects with clear requirements

**Disadvantages:**
- Inflexible — difficult to make changes once a phase is complete
- Problems discovered late in testing are expensive to fix
- Users don't see the system until the end
- Not ideal for large or complex projects
- Long time before delivering any working version

**Best for:** Projects with clear, stable requirements that won't change.

---

### Question 15: Iterative/Incremental Model
**Q: What is the Iterative/Incremental model?**

A: The Iterative/Incremental model builds the system in small pieces (increments). Each increment is a working part of the system that is completed, tested, and released.

**How it works:**
- Divide the system into small modules or features
- Develop and test each increment separately
- Release increments gradually
- Each iteration adds new features or improves existing ones
- Users get working software early and often

**Advantages:**
- Flexible — easier to make changes
- Early delivery of working software
- Faster feedback from users
- Risks identified earlier
- Users see progress and can provide input

**Disadvantages:**
- Requires careful planning and management
- More complex to coordinate
- Can be costly if not managed well

**Best for:** Projects where requirements may change or where early delivery is important.

---

### Question 16: Spiral Model
**Q: Explain the Spiral model and when it's used.**

A: The Spiral model combines Waterfall and Iterative approaches. It is risk-driven and goes through multiple cycles (spirals). Each spiral has 4 phases: Planning, Risk Analysis, Engineering, and Evaluation.

**How it works:**
- Each spiral is a complete iteration
- Spiral 1 (innermost) = initial planning and prototype
- Spiral 2 = more detailed design and prototype
- Spiral 3 = full implementation and testing
- Each spiral adds more functionality
- Risk assessment happens in every spiral

**Advantages:**
- Risk-focused approach reduces project failures
- Works well for large, complex projects
- Allows changes and adjustments
- Good documentation

**Disadvantages:**
- Expensive — requires experienced risk management
- Complex process
- Difficult for small projects
- Longer time to deliver

**Best for:** Large, complex projects with high risks (like government systems, aerospace).

---

### Question 17: Agile Model
**Q: What is the Agile model? How does it differ from Waterfall?**

A: The Agile model develops the system in short cycles called "sprints" (usually 1-4 weeks). It emphasizes flexibility, collaboration, and continuous improvement.

**Key Principles:**
- Individuals and interactions over processes and tools
- Working software over documentation
- Customer collaboration over contracts
- Responding to change over following a plan

**How it works:**
- Create a product backlog (list of features)
- Plan a sprint (short period, usually 2 weeks)
- Daily stand-up meetings
- Develop, test, and deliver working features in each sprint
- Get feedback and adjust

**Advantages:**
- Very flexible to changes
- Customer sees results frequently
- Rapid delivery of features
- Bugs found and fixed quickly
- Good team communication

**Disadvantages:**
- Requires active customer participation (may not always be available)
- Less documentation
- Difficult to estimate final cost and timeline
- Works best with small teams
- Can be chaotic if not managed well

**Comparison with Waterfall:**
| Feature | Waterfall | Agile |
|---------|-----------|-------|
| Flexibility | Low | High |
| Customer involvement | End only | Continuous |
| Timeline | Fixed | Adaptive |
| Documentation | Extensive | Minimal |
| Testing | End phase | Continuous |
| Risk | High (late discovery) | Low (early detection) |

---

### Question 18: V-Model (Verification & Validation)
**Q: What is the V-Model and how does it differ from Waterfall?**

A: The V-Model is similar to Waterfall but includes a testing phase for every development phase. It's called "V" because the phases go down one side and testing goes up the other side.

**How it works:**
- Left side (down): Requirements → Design → Implementation
- Right side (up): Testing corresponds to each left-side phase
- Unit Testing ↔ Implementation
- Integration Testing ↔ Design
- System Testing ↔ Requirements
- UAT (User Acceptance Testing) ↔ Requirements

**Advantages:**
- Testing begins early (reduces bugs)
- Clear relationship between development and testing
- Well-structured and organized
- Good for projects where quality is critical

**Disadvantages:**
- Inflexible (like Waterfall)
- Expensive to make changes late
- Users don't see system until late
- Not ideal for changing requirements

**Best for:** Systems that need high quality and rigorous testing (medical, aerospace, banking systems).

---

### Question 19: Comparison of All SDLC Models
**Q: Create a comparison table of the 5 SDLC models.**

A:

| Model | Flexibility | Complexity | Best For | Time to Delivery | Risk Level |
|-------|-------------|-----------|----------|------------------|-----------|
| **Waterfall** | Low | Low | Clear, stable requirements | Long | High |
| **Iterative** | Medium | Medium | Flexible requirements | Medium | Medium |
| **Spiral** | Medium | High | Large, complex, high-risk projects | Long | Low |
| **Agile** | High | High | Changing requirements, small teams | Short | Low |
| **V-Model** | Low | Medium | Quality-critical systems | Long | Medium |

---

## SECTION 4: PRACTICAL APPLICATION & SCENARIO QUESTIONS

### Question 20: Scenario — Choosing the Right SDLC Model
**Q: A bank wants to develop a new online banking system. Which SDLC model would you recommend and why?**

A: **Recommendation: Spiral Model or Agile Model**

**Reasons:**
- **Security concerns** (risk-focused) — Spiral model's risk analysis phase is critical for banking
- **Large complexity** — The system has many features (accounts, transfers, payments, etc.)
- **Regulatory requirements** — Must comply with banking laws
- **High stakes** — Failures could cost money and damage trust

**If using Spiral Model:**
- Each spiral focuses on a critical risk area (security, data integrity, fraud detection)
- Prototype to test high-risk features early
- Extensive documentation for compliance

**Alternative - Agile:**
- If the bank wants frequent updates and customer feedback
- Sprint by feature (accounts → transfers → payments)
- But may need more documentation for regulatory compliance

---

### Question 21: Scenario — Project Planning
**Q: You are a system analyst. A small business wants a simple inventory management system. What activities would you do in the Planning phase?**

A:

1. **Define Project Objectives** — What exactly does the business want to achieve? (Track stock, reduce waste, faster ordering)

2. **Scope Definition** — What will be included? What won't be included? (Will it have sales reporting? Will it integrate with accounting?)

3. **Resource Identification** — What do we need?
   - Personnel (analysts, developers, testers)
   - Hardware (computers, servers)
   - Software (database, programming tools)
   - Budget and timeline

4. **Feasibility Study** — Is the project viable?
   - Technical: Is the technology available? (Yes, standard database tools)
   - Economic: Will benefits justify costs? (ROI in 2 years?)
   - Operational: Can staff learn to use it? (Yes, simple system)
   - Legal: Any licensing issues? (Check software licenses)
   - Schedule: Can we finish in 3 months? (Yes, simple scope)

5. **Risk Identification** — What could go wrong?
   - Staff resistance to new system
   - Data migration problems
   - Integration with existing systems

6. **Stakeholder Analysis** — Who is involved?
   - Business owner (pays for it)
   - Store managers (use it daily)
   - Accountant (gets reports)
   - IT staff (maintains it)

---

### Question 22: Testing Types
**Q: Explain the 4 levels of testing in SDLC.**

A:

1. **Unit Testing** — Developers test individual pieces of code (functions, modules) to ensure each works correctly in isolation.
   - Who: Programmers
   - When: During implementation
   - Example: Test the "calculate stock value" function

2. **Integration Testing** — Test how different modules work together when combined.
   - Who: QA testers
   - When: After unit testing
   - Example: Test that inventory system integrates with sales system

3. **System Testing** — Test the entire system as a complete unit to ensure all requirements are met.
   - Who: QA team
   - When: After integration testing
   - Example: Test the whole inventory system with realistic data

4. **User Acceptance Testing (UAT)** — Users test the system in a real-world scenario to confirm it meets their needs.
   - Who: End users, business people
   - When: Before deployment
   - Example: Store managers use the system for a week to verify it works as promised

---

### Question 23: Conversion Strategies
**Q: What are the 4 main conversion strategies when deploying a new system?**

A:

1. **Parallel Conversion** — Run old and new systems together for a period.
   - Pros: Safe, can compare results, easy to revert if problems
   - Cons: Expensive (running 2 systems), requires double work
   - Best for: Critical systems where downtime is unacceptable

2. **Direct Cutover (Big Bang)** — Stop old system, immediately start using new system.
   - Pros: Quick, one-time transition, no overlap
   - Cons: Risky, if problems occur, no easy backup, can disrupt operations
   - Best for: Small projects, systems with less critical data

3. **Phased Conversion** — Deploy system in stages/departments over time.
   - Pros: Spreads risk, allows learning from early phases, less disruptive
   - Cons: Takes longer, some inconsistency between departments
   - Best for: Large organizations with multiple departments

4. **Pilot Conversion** — Deploy to one small group (one office, one department) first, then full rollout.
   - Pros: Test in real environment before full deployment, reduces risk
   - Cons: Takes longer, must maintain both systems during pilot
   - Best for: Organizations that want to test with limited risk

---

## SECTION 5: SHORT ANSWER QUESTIONS

### Question 24
**Q: What is the main difference between logical design and physical design?**

A: **Logical Design** — describes WHAT the system will do (functions, features, business processes) without worrying about HOW it will be implemented.

**Physical Design** — describes HOW the system will do it (specific technology, hardware, software, databases, network architecture).

---

### Question 25
**Q: Why is documentation important in SDLC?**

A: Documentation is important because it:
- Creates a record of decisions and specifications
- Helps new team members understand the system
- Serves as a reference for future maintenance
- Provides evidence of compliance with requirements
- Reduces misunderstanding between stakeholders
- Helps with debugging and troubleshooting

---

### Question 26
**Q: What is a prototype and when is it used?**

A: A prototype is a working model or sample of the system built quickly to demonstrate ideas or test concepts. It's not the final system but helps users visualize what the final product will look like.

**When used:**
- During analysis to clarify user requirements
- During design to test ideas before full development
- In Spiral model to validate risks
- To get early user feedback

---

### Question 27
**Q: What does "scalability" mean in system design?**

A: Scalability means the system can grow and handle increased load (more users, more data, more transactions) without major redesign or replacement. A scalable system works well today and can expand tomorrow.

Example: A system designed for 100 users should be able to handle 1,000 users with just hardware upgrades, not total redesign.

---

### Question 28
**Q: What is the main goal of system maintenance?**

A: The main goal of system maintenance is to keep the system running smoothly after deployment by:
- Fixing bugs found by users (corrective maintenance)
- Making improvements (adaptive maintenance)
- Adding new features (perfective maintenance)
- Preventing problems (preventive maintenance)
- Providing user support

---

## SECTION 6: ESSAY QUESTIONS

### Question 29
**Q: Compare and contrast the Waterfall and Agile SDLC models. Which would you choose for a government project and why?**

A: 

**Waterfall Model:**
- Sequential approach, one phase at a time
- Extensive documentation
- Fixed requirements and timeline
- Users see system only at the end
- Good for projects with clear, stable needs
- Inflexible to changes

**Agile Model:**
- Iterative approach, development in sprints
- Minimal documentation
- Flexible and adaptive to changes
- Users involved throughout and see progress
- Good for projects with evolving requirements
- Requires active customer participation

**For a Government Project — Waterfall is Better:**

Reasons:
1. **Compliance Requirements** — Government projects need extensive documentation for audits and regulations. Agile's minimal documentation won't meet these needs.

2. **Legal Contracts** — Government contracts require detailed specifications upfront. Waterfall provides this clarity.

3. **Budget Predictability** — Government budgets are fixed. Waterfall's fixed scope helps with cost estimation.

4. **Change Control** — Government projects have strict change control processes. Waterfall's rigid approach fits better.

5. **Clear Requirements** — Government requirements are usually well-defined before the project starts.

However, a **hybrid approach** might work best — use Waterfall's structure but build in some flexibility for necessary changes through a formal change control process.

---

### Question 30
**Q: Explain how a system analyst would approach gathering requirements for a new customer management system for a retail company. Include the methods you would use and potential challenges.**

A:

**Approach to Requirements Gathering:**

**1. Stakeholder Identification**
- Sales managers
- Customer service staff
- Store owners
- IT staff
- Finance team
- Marketing department

**2. Methods of Gathering Requirements**

**a) Interviews**
- Conduct one-on-one interviews with key users (sales manager, customer service)
- Questions: What are current problems? What features do you need? How do you use customer data now?
- Advantage: Detailed feedback
- Challenge: Time-consuming, individual biases

**b) Questionnaires**
- Send surveys to all store staff
- Advantage: Reaches many people
- Challenge: Low response rate, may not capture all needs

**c) Observation**
- Watch customer service staff work for a day
- See how they currently manage customer data
- Advantage: See actual workflow
- Challenge: People work differently when being watched

**d) Group Workshops**
- Bring together representatives from different departments
- Discuss pain points and desired features together
- Advantage: Different perspectives shared, collaborative
- Challenge: Group dynamics may dominate (some voices louder than others)

**e) Document Review**
- Review current customer forms, processes, reports
- Understand existing customer database structure
- Advantage: Factual information
- Challenge: Documents may be outdated

**3. Potential Challenges**

**a) Conflicting Requirements**
- Sales wants quick customer lookup; IT wants secure access controls
- Solution: Negotiate and find balance

**b) Unclear Needs**
- Users don't know exactly what they want
- Solution: Use prototypes to clarify

**c) User Resistance**
- Staff may resist change
- Solution: Involve them early, show benefits

**d) Scope Creep**
- Users keep adding "nice to have" features
- Solution: Define clear boundaries on what's in scope

**e) Hidden Requirements**
- Some needs not mentioned in interviews
- Solution: Validate requirements with users regularly

**4. Deliverable**
After gathering, create a **Requirements Specification Document** that clearly lists:
- Functional requirements (what system must do)
- Non-functional requirements (performance, security)
- User roles and permissions
- Data requirements
- System constraints

---

## QUICK REVIEW CHECKLIST

Before your test, make sure you can answer YES to all:

- [ ] I can explain the difference between System Analysis and System Design
- [ ] I can list and describe all 7 SDLC phases in order
- [ ] I can explain what a feasibility study is and list its 5 types
- [ ] I know the characteristics and best uses of Waterfall, Iterative, Spiral, Agile, and V-Model
- [ ] I understand the advantages and disadvantages of each SDLC model
- [ ] I can explain the 4 levels of testing
- [ ] I know the 4 conversion strategies for deployment
- [ ] I can identify when to use each SDLC model based on project characteristics
- [ ] I understand the components of a system
- [ ] I know the roles of different people in system development

---

**Good Luck on Your Test Tomorrow! 🎯**

Remember: Test is on **Friday, June 12, 2026**. You've got this!
