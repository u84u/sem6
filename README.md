# Software Engineering

---

## Practical 1: Study and Comparison of Software Process Models

### Q1: What is a Software Process Model?
A structured framework that defines how software is planned, developed, tested, and maintained. It organizes development activities into phases to improve efficiency, quality, and risk management.

### Q2: What are the phases of the Waterfall Model?
Requirements → Design → Implementation → Testing → Deployment → Maintenance. Each phase must complete before the next begins — it's strictly linear.

### Q3: What are the advantages of the Waterfall Model?
Simple and easy to understand, well-defined stages with clear documentation, and suitable for small projects with stable, fixed requirements.

### Q4: What are the disadvantages of the Waterfall Model?
No feedback loops between phases, poor handling of requirement changes, and testing happens late — bugs found late are expensive to fix.

### Q5: When should you use the Waterfall Model?
For well-defined projects with fixed requirements that won't change, such as payroll systems or simple utility applications.

### Q6: What is the Incremental Model?
Software is built and delivered in small increments, where each increment adds more functionality. Users get working modules early rather than waiting for the complete system.

### Q7: What are the advantages of the Incremental Model?
Early delivery of working modules, flexibility to accommodate requirement changes between increments, and easier risk management since problems are caught early.

### Q8: What are the disadvantages of the Incremental Model?
Requires good upfront planning and the system architecture must be designed to support incremental development from the start.

### Q9: When should you use the Incremental Model?
For medium-sized projects where requirements are partially clear and can be delivered in stages.

### Q10: What is the Spiral Model?
Combines iterative development with systematic risk analysis. Each spiral cycle includes four phases: planning, risk evaluation, development, and review.

### Q11: What are the advantages of the Spiral Model?
Best model for high-risk projects, provides frequent customer feedback at each cycle, and is both flexible and scalable.

### Q12: What are the disadvantages of the Spiral Model?
Expensive and complex to implement, and requires expertise in risk management to be effective.

### Q13: When should you use the Spiral Model?
For large, critical, and complex systems like aerospace or defense projects where risk management is essential.

### Q14: What is the Agile Model?
An iterative, customer-centric approach with short development cycles called sprints. It focuses on collaboration, adaptability, and rapid delivery of working software.

### Q15: What are the advantages of the Agile Model?
Highly flexible and adaptive to changes, continuous customer feedback throughout development, and working software is delivered frequently.

### Q16: What are the disadvantages of the Agile Model?
Requires an experienced team, documentation may be minimal, and it's difficult to manage for large distributed teams.

### Q17: When should you use the Agile Model?
For projects with frequently changing requirements, start-ups, and fast-evolving applications.

### Q18: What is the V-Model (Verification & Validation Model)?
An extension of Waterfall that emphasizes testing at each development stage. Every development phase has a corresponding testing phase planned in parallel.

### Q19: What are the advantages of the V-Model?
Testing is planned early in the lifecycle, highly structured and disciplined approach, and suitable for safety-critical systems.

### Q20: What are the disadvantages of the V-Model?
Rigid and not flexible to changes, and requirement changes are costly once development begins.

### Q21: When should you use the V-Model?
For medical devices, embedded systems, and other safety-critical applications where thorough testing is mandatory.

### Q22: Which models are best for stable requirements?
Waterfall and V-Model are ideal for stable and safety-critical environments where requirements are well-understood upfront.

### Q23: Which models are best for evolving requirements?
Incremental and Agile work well when requirements evolve during development.

### Q24: Which model is best for risk management?
The Spiral Model is best when risk management is the primary concern.

---

## Practical 2: Preparation of SRS Document

### Q1: What is an SRS document?
A Software Requirement Specification describes all functional and non-functional requirements, system features, constraints, and overall system behavior. It serves as a baseline for design, development, and testing.

### Q2: Who uses the SRS document?
Developers, testers, project managers, and stakeholders — it acts as a common reference and contract between all parties.

### Q3: What is the "Purpose" section of an SRS?
It describes why the SRS document exists — to define the requirements for the system and specify who will use the document.

### Q4: What is the "Scope" section of an SRS?
It defines what the system will do and for whom. For example, OFOS allows customers to browse restaurants, place orders, make payments, and track delivery.

### Q5: What goes in the "Definitions, Acronyms & Abbreviations" section?
A glossary of terms used in the document — e.g., OFOS (Online Food Ordering System), UI (User Interface), DBMS (Database Management System), OTP (One-Time Password).

### Q6: What is "Product Perspective" in SRS?
It describes how the system fits into the larger context — whether it's standalone or part of a larger system, and its main components (Customer Interface, Restaurant Dashboard, Admin Panel, Centralized Database).

### Q7: What are "Product Functions"?
A list of all major features the system provides — e.g., User Registration & Login, Browse Restaurants & Menus, Add Items to Cart, Place Order, Payment, Order Tracking, Restaurant Menu Management, Admin Management.

### Q8: What are "User Classes and Characteristics"?
Different types of users who will interact with the system — e.g., Customers (casual users), Restaurant Owners (business users), Delivery Persons (operational users), and Admins (system managers).

### Q9: What is "Operating Environment"?
The technical platform the system runs on — Web browser / Android / iOS, backend in Java/Python/PHP/Node.js, database in MySQL/PostgreSQL, OS: Windows/Linux.

### Q10: What are "Design and Implementation Constraints"?
Limitations the system must work within — must follow online payment security standards, requires internet connection, and must use responsive UI design.

### Q11: What are "Assumptions and Dependencies"?
Conditions assumed to be true — users have valid mobile/email, restaurants provide correct pricing, and payment gateway is available.

### Q12: What are Functional Requirements?
Specific behaviors the system must perform — e.g., "User shall register using email/mobile and password" (F1.1), "System shall validate credentials during login" (F1.2).

### Q13: What are Non-Functional Requirements (NFRs)?
Quality attributes describing how the system should perform — including performance, security, reliability, usability, and scalability.

### Q14: What are Performance Requirements?
System should handle 1000+ concurrent users and response time must be under 3 seconds.

### Q15: What are Security Requirements?
Data encryption for passwords, secure payment integration, and role-based access control to ensure only authorized users access specific features.

### Q16: What are Reliability Requirements?
System uptime must be 99% and backup/recovery must be supported to prevent data loss.

### Q17: What are Usability Requirements?
Easy-to-use UI for both customers and restaurants — the interface should be intuitive and require minimal training.

### Q18: What are Scalability Requirements?
The system should support adding more restaurants and users without performance degradation.

### Q19: What are External Interface Requirements?
Descriptions of how the system interacts with users (UI requirements), hardware (mobile devices, payment gateway devices), and software (database, payment gateway APIs, SMS/Email APIs).

### Q20: What is a Use Case Table?
A structured description of a system interaction including use case ID, name, actors, description, preconditions, main flow, alternate flows, exceptions, and postconditions.

### Q21: What is a Data Flow Diagram (DFD)?
A diagram showing how data flows through the system. Level 0 (context diagram) shows the system as a single process. Level 1 breaks it into modules like User Module, Restaurant Module, Order Processing, and Payment Processing.

### Q22: What are "Other Requirements" in SRS?
Future considerations like integration with coupons, offers, wallet systems, and multi-language interface support.

---

## Practical 3: Structured vs. Object-Oriented Analysis

### Q1: What is Structured Analysis?
A process-centric approach that focuses on how data flows through the system. It uses DFDs (Data Flow Diagrams) and ER Diagrams to model system behavior.

### Q2: What are the key components of Structured Analysis?
Processes (User Management, Browse Restaurants, Cart & Order, Payment Processing), Data Stores (Users, Restaurants, Orders, Payments), and data flow between them.

### Q3: What is Object-Oriented Analysis (OOA)?
An object-centric approach that models real-world entities as classes with attributes, methods, and relationships using UML diagrams.

### Q4: What are the key components of OOA?
Objects/Classes (Customer, Restaurant, Menu, Item, Order, Payment, Admin), their interactions, responsibilities, behavior, and relationships.

### Q5: What is the fundamental difference between Structured and OOA?
Structured Analysis answers "what the system does" (process-centric), while OOA answers "what the system is and how it behaves" (object-centric).

### Q6: Why is OOA preferred for modern systems?
It models real-world entities (Customer, Restaurant, Delivery) and their interactions, making maintenance, scalability, and enhancements easier than process-centric approaches.

### Q7: What is a DFD (Data Flow Diagram)?
A diagram showing the flow of information through a system — how data moves from external entities through processes to data stores.

### Q8: What is an ER Diagram?
An Entity-Relationship Diagram showing data entities, their attributes, and relationships between them — used primarily in database design.

### Q9: How does data flow in the OFOS structured analysis?
Customer → System → Restaurant → Delivery → Admin — showing the sequential flow of information through the system.

### Q10: How do objects interact in the OFOS OOA?
Customer places Order → triggers Payment → Restaurant updates Order → Delivery updates Status — showing object-to-object interactions.

---

## Practical 4: Project Planning and Estimation (W5HH & COCOMO)

### Q1: What is the W5HH principle?
A project planning framework that answers: Who (team), What (objectives), When (timeline), Where (location/platform), Why (justification), How (methodology), and How Much (budget/effort).

### Q2: What does "Who" in W5HH identify?
The team members and their roles — frontend developers, backend developers, database developers, project manager, and testers.

### Q3: What does "What" in W5HH identify?
The project objectives and deliverables — e.g., design and implement a system for customers to order food online.

### Q4: What does "When" in W5HH identify?
The project timeline and milestones — typically represented as a Gantt chart showing weekly tasks and sprint iterations.

### Q5: What does "Where" in W5HH identify?
The deployment platform and development environment — web, mobile, cloud servers, and development tools used.

### Q6: What does "How" in W5HH identify?
The methodology and approach — e.g., Agile with weekly sprints, using specific technologies and frameworks.

### Q7: What does "How Much" in W5HH identify?
The budget, effort, and resource requirements — including team size, development time, and cost estimation.

### Q8: What is the COCOMO model?
Constructive Cost Model — estimates software effort, time, and cost based on project size measured in KLOC (thousands of lines of code).

### Q9: What are the three COCOMO project types?
Organic (small team, well-understood application), Semi-detached (medium team, mixed experience), and Embedded (tight constraints, complex systems).

### Q10: What is the Basic COCOMO formula for effort?
Effort (Person-Months) = a × (KLOC)^b. For Organic projects: a = 2.4, b = 1.05.

### Q11: What is the Basic COCOMO formula for development time?
Time (Months) = c × (Effort)^d. For Organic projects: c = 2.5, d = 0.38.

### Q12: How do you estimate project size in KLOC?
By summing up lines of code for each component — e.g., Frontend: 2000 LOC + Backend: 3000 LOC + Database scripts: 500 LOC = 5500 LOC = 5.5 KLOC.

### Q13: How is team size estimated from COCOMO?
Team Size = Effort / Development Time. For 14.33 PM effort over 6.85 months ≈ 2.1, rounded to 3 people. Recommended: 3–5 members.

### Q14: What is a Gantt Chart?
A visual timeline showing project tasks, their durations, start/end dates, and dependencies — useful for scheduling and tracking progress across weeks or months.

### Q15: What is the difference between Basic, Intermediate, and Detailed COCOMO?
Basic uses only KLOC for estimation. Intermediate adds cost drivers (complexity, reliability, experience). Detailed adds phase-sensitive multipliers for each development phase.

---

## Practical 5: Risk Management and Quality Planning

### Q1: What is Risk Management in software engineering?
The process of identifying, analyzing, and mitigating risks throughout the software development lifecycle to minimize project failures, delays, and cost overruns.

### Q2: What is Risk Identification?
The process of finding potential risks that could affect the project — including technical risks, schedule risks, resource risks, requirement risks, and security risks.

### Q3: What is Risk Analysis?
Evaluating each identified risk by assessing its probability (likelihood of occurrence) and impact (severity of consequences) to prioritize mitigation efforts.

### Q4: What is Risk Mitigation?
Developing strategies to reduce the probability or impact of identified risks — e.g., using proven technology to reduce technical risk, or adding buffer time to reduce schedule risk.

### Q5: What is a Risk Register?
A document that tracks all identified risks, their probability, impact, mitigation strategies, current status, and assigned risk owners.

### Q6: What is Risk Monitoring?
Continuously tracking risks throughout the project — maintaining the Risk Register, conducting weekly risk review meetings, and assigning risk owners for each critical risk.

### Q7: What is Quality Planning?
Defining the quality standards, objectives, and activities to ensure the software meets functional and non-functional requirements, is reliable, maintainable, and satisfies end-users.

### Q8: What are Quality Objectives?
Specific, measurable quality goals — e.g., zero critical bugs at release, 99% uptime, response time under 3 seconds, and 100% test case coverage for critical modules.

### Q9: What is Quality Assurance (QA)?
Process-focused activities that prevent defects — including code reviews, process audits, following coding standards, and using version control practices.

### Q10: What is Quality Control (QC)?
Product-focused activities that detect defects — including testing (unit, integration, system), inspections, and verifying the final product meets requirements.

### Q11: What is the difference between QA and QC?
QA is proactive and process-oriented (preventing defects). QC is reactive and product-oriented (finding defects in the finished product).

### Q12: What tools are used for Quality Assurance?
GitHub/GitLab (version control), Selenium/JUnit/Postman (testing), Jira/Trello (project management), OWASP ZAP/Burp Suite (security testing), Apache JMeter (performance testing).

### Q13: What are Quality Standards and Metrics?
Measurable criteria to assess quality — code coverage percentage, defect density, mean time to failure, customer satisfaction scores, and compliance with coding standards.

---

## Practical 6: Use Case Modeling and Diagrams

### Q1: What is a Use Case?
A description of how an actor interacts with the system to achieve a specific goal, including the main flow of events, alternate flows, and exceptions.

### Q2: What is an Actor in UML?
An external entity (person, system, or device) that interacts with the system. In OFOS: Customer, Restaurant Staff, Delivery Person, and Admin.

### Q3: What are the components of a Use Case Description?
Use Case ID, name, actors, description, preconditions, main flow (normal path), alternate flows (variations), exceptions (error conditions), and postconditions (system state after completion).

### Q4: What is a Use Case Diagram?
A UML diagram showing actors (stick figures), use cases (ovals), and their relationships — providing a visual overview of all system functionality from the user's perspective.

### Q5: What is the «include» relationship?
A mandatory relationship where one use case always includes another. E.g., "Place Order" always includes "Payment" — the included use case is required for the base use case to complete.

### Q6: What is the «extend» relationship?
An optional relationship where one use case may extend another under certain conditions. E.g., "Apply Coupon" extends "Place Order" — it only happens if the user chooses to apply a coupon.

### Q7: What are preconditions in a use case?
Conditions that must be true before the use case can begin — e.g., "User must be logged in" before placing an order.

### Q8: What are postconditions in a use case?
The state of the system after the use case completes successfully — e.g., "Order is created and sent to restaurant" after placing an order.

### Q9: What is the main flow in a use case?
The normal, expected sequence of steps — the "happy path" where everything goes as planned without errors or exceptions.

### Q10: What are alternate flows in a use case?
Variations of the main flow that handle different but valid scenarios — e.g., user chooses Cash on Delivery instead of online payment.

### Q11: What are exceptions in a use case?
Error conditions or unexpected events — e.g., payment gateway failure, restaurant rejects order, or user enters invalid data.

### Q12: How many actors are in the OFOS system?
Four — Customer (browses, orders, tracks), Restaurant Staff (accepts/rejects orders, manages menu), Delivery Person (updates order status), and Admin (manages users/restaurants, generates reports).

---

## Practical 7: Design UML Diagrams (Class, Sequence, Activity)

### Q1: What is a Class Diagram?
A UML diagram showing the static structure of a system — classes, their attributes, methods, and relationships (association, inheritance, aggregation, composition, dependency).

### Q2: What are the components of a class in UML?
Three sections: class name (top), attributes/properties (middle), and methods/operations (bottom). E.g., User class has attributes (username, password) and methods (login(), logout()).

### Q3: What is Association in a Class Diagram?
A relationship between two classes indicating they are connected. E.g., User is associated with Account — a user has an account.

### Q4: What is Dependency in a Class Diagram?
A "uses" relationship where one class depends on another. E.g., Login class depends on User class to validate credentials.

### Q5: What is a Sequence Diagram?
A UML diagram showing how objects interact over time through messages. It illustrates the order of operations in a specific scenario using lifelines and message arrows.

### Q6: What are lifelines in a Sequence Diagram?
Vertical dashed lines representing each object's existence over time. Messages flow horizontally between lifelines showing the sequence of interactions.

### Q7: What is the login sequence in the OFOS example?
User → Login: enterCredentials() → Login → Database: authenticateUser() → Database → Login: authenticationResult → Login → User: displayDashboard() or displayError().

### Q8: What is an Activity Diagram?
A UML diagram showing the flow of activities or steps in a process, including start/end nodes, activities, decision points (diamonds), and flow arrows.

### Q9: What is the login activity flow?
Start → Enter Username & Password → Decision: Are credentials valid? → Yes → Redirect to Dashboard → End. No → Display Error → End.

### Q10: What are decision nodes in an Activity Diagram?
Diamond-shaped symbols representing branching points where the flow splits based on a condition — e.g., "Are credentials valid?" with Yes/No paths.

### Q11: What is the difference between Class, Sequence, and Activity diagrams?
Class diagrams show static structure (what the system is). Sequence diagrams show dynamic interactions over time (how objects communicate). Activity diagrams show process flow (how work gets done).

---

## Practical 8: Software Testing – Test Case Design and Verification

### Q1: What is Black Box Testing?
Testing that focuses on inputs and expected outputs without considering internal code structure. It tests what the system does from the user's perspective.

### Q2: What is White Box Testing?
Testing that examines internal code logic, branches, conditions, and paths. It tests how the system works internally by verifying all code paths are executed.

### Q3: What should a test case include?
Test case ID, description, input data, expected output, actual output (filled after execution), and pass/fail status.

### Q4: What is Equivalence Partitioning?
A Black Box technique that divides input data into valid and invalid partitions, then tests one representative value from each partition to reduce the number of test cases.

### Q5: What is Boundary Value Analysis?
A Black Box technique that tests values at the boundaries of input ranges (minimum, maximum, just below, just above) since errors often occur at edges.

### Q6: What is Statement Coverage in White Box Testing?
A metric measuring what percentage of code statements have been executed during testing. 100% statement coverage means every line of code has been run at least once.

### Q7: What is Branch Coverage in White Box Testing?
A metric ensuring every branch (if/else, switch case) in the code has been executed at least once — both true and false paths must be tested.

### Q8: What is the difference between Black Box and White Box testing?
Black Box focuses on expected behavior regardless of code paths (external testing). White Box focuses on testing all possible branches and paths in the code (internal testing).

### Q9: What is the login module test scenario in Practical 8?
User enters username and password. If credentials are correct, access is granted. If empty or invalid, appropriate error messages are displayed.

### Q10: What are common Black Box test cases for login?
Valid credentials (should succeed), empty username (should error), empty password (should error), invalid credentials (should error), SQL injection attempt (should reject), special characters in input (should handle safely).

---

## Practical 9: Software Testing Levels and Execution Report

### Q1: What is Unit Testing?
Testing individual components or functions in isolation. In the login module: testing validateUsername(), validatePassword(), and authenticateUser() separately.

### Q2: What is Integration Testing?
Testing interactions between integrated modules. In the login module: verifying the login module correctly communicates with the Database Module to fetch and match credentials.

### Q3: What is System Testing?
Testing the complete, integrated system to ensure it meets all requirements. In the login module: testing the full workflow including UI, backend authentication, and security checks like SQL injection prevention.

### Q4: What is Acceptance Testing?
Testing conducted by end users or stakeholders to verify the system meets business requirements and is ready for deployment. It confirms users can log in successfully and see user-friendly error messages.

### Q5: What is the difference between the four testing levels?
Unit tests individual functions. Integration tests module interactions. System tests the complete application. Acceptance tests from the user's business perspective.

### Q6: What is a Test Execution Report?
A document showing each test case's expected vs actual output, with pass/fail status after testing. It tracks testing progress and documents quality status.

### Q7: What information does a Test Execution Report contain?
Test case ID, description, expected output, actual output, status (Pass/Fail), and any remarks or defect references for failed tests.

### Q8: Why is the execution report important?
It provides evidence that testing was performed, shows which tests passed or failed, and helps track defect resolution before release.

---

## Practical 10: Demonstration of CASE Tools

### Q1: What are CASE Tools?
Computer-Aided Software Engineering tools that help developers model, design, and document software systems efficiently. Examples: StarUML, Visual Paradigm, Rational Rose, Enterprise Architect.

### Q2: What features do CASE tools provide?
UML diagram creation (Class, Sequence, Activity, etc.), code generation from UML models, documentation support (export diagrams and reports), and consistency checks to ensure model correctness.

### Q3: How do you create a new project in StarUML?
Open StarUML → File → New Project → UML → Choose UML 2.x model → Name the project (e.g., OnlineBankingSystem).

### Q4: How do you create a Class Diagram in StarUML?
Add a Class Diagram to the model → Create classes (User, Login, Account) → Add attributes and methods → Define relationships (Association between User and Account, Dependency between Login and User).

### Q5: How do you create a Sequence Diagram in StarUML?
Add a Sequence Diagram → Add participants (User, Login, Database) → Draw message arrows showing the flow: enterCredentials() → validateUser() → authenticateUser() → displayDashboard()/displayError().

### Q6: How do you create an Activity Diagram in StarUML?
Add an Activity Diagram → Define activities (Enter credentials → Validate → Authenticate) → Add decision nodes for valid/invalid credentials → Connect with flow arrows to success/error end nodes.

### Q7: What is code generation in CASE tools?
Automatically creating skeleton code from UML models. Select a class → Right-click → Generate Code → Choose language (Java, C#, Python). It generates class definitions with attributes and empty methods.

### Q8: How do you export diagrams from StarUML?
File → Export → Diagram as Image (PNG, SVG) for reports. You can also generate HTML or PDF reports for comprehensive project documentation.

### Q9: What are the deliverables for a CASE tool practical?
StarUML .mdj project file (editable), PNG/SVG diagrams (Class, Sequence, Activity), optionally generated skeleton code, and optionally HTML/PDF documentation.

### Q10: What are the benefits of using CASE tools?
Speeds up design with drag-and-drop UML modeling, maintains consistency between diagrams and code, supports team collaboration by sharing models, and is useful for educational, professional, and documentation purposes.

### Q11: What is the .mdj file format?
StarUML's project file format (Model Diagram JSON) — an editable file that stores all diagrams, classes, relationships, and model data that can be reopened and modified in StarUML.

### Q12: What is traceability in CASE tools?
Maintaining links between requirements, design diagrams, and implementation code — ensuring every requirement is covered by design and every design element is implemented in code.
