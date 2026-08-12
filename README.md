# Software Testing and Automation — Complete Study Guide
### Consolidated from Module 1, 2 & 3 | Parul University | Yadagiri Rama Deepak

---

## Table of Contents

**Module 1 — Introduction to Software Testing**
1. What is Software Testing
2. Verification & Validation (V&V)
3. Market Scenario & Importance of V&V
4. Career Opportunities
5. Why Should We Test Software
6. Independent V&V (IV&V)
7. Phases of Software Testing (STLC)
8. Software Development Process Models
9. Introduction to Selenium
10. Application Testing vs Product Testing

**Module 2 — Software Testing Techniques**
11. Static vs Dynamic Testing
12. White Box vs Black Box Testing
13. User Interface Testing Overview
14. Form-Level Validation & Inter-Form Dependencies
15. Field-Level Validation & Inter-Field Dependencies
16. Error Message Validation
17. UI Testing — Form, Field & Dependency Checks
18. Common UI Testing Checks & Tools
19. Automated Test Execution with Selenium (How It Works)

**Module 3 — Software Testing Levels & Types**
20. Types of Software Testing (Manual vs Automation Overview)
21. Functional vs Non-Functional Testing
22. Regression Testing
23. Testing Levels: Unit → Integration → System → UAT
24. Performance & Load Testing
25. Acceptance Testing
26. Localization Testing
27. Topics Named But Not Detailed in Source Slides

**Quick-Revision Cheat Sheet** (at the end)

---

# MODULE 1 — INTRODUCTION TO SOFTWARE TESTING

## 1. What is Software Testing?

Software Testing is the process of **evaluating a system to detect defects**. It ensures:
- **Quality**
- **Reliability**
- **Performance**
- **Security**

> Testing answers one core question: **"Does the software meet user expectations?"**

---

## 2. Verification & Validation (V&V)

These are the two pillars of quality assurance, and they answer two *different* questions:

| Aspect | Verification | Validation |
|---|---|---|
| Question answered | "Are we building the product **right**?" | "Are we building the **right** product?" |
| Nature | Static process | Dynamic process |
| Method | Reviews & inspections | Execution of code |
| Code execution | Not required | Required |
| Timing | Done early (docs, design, code review) | Done after development |
| Checks | Work products (docs, design, code) meet specifications | Final software meets **user needs** |

**Why both matter:** Using Verification *and* Validation together ensures the product is accurate, reliable, and genuinely user-friendly — verification alone can produce a spec-compliant product that still doesn't solve the user's real problem.

---

## 3. Market Scenario & Importance

The global software testing market is growing rapidly, driven by:
- **Cloud computing**
- **Mobile applications**
- **AI & IoT systems**

This is pushing the industry toward:
- **Automation testing**
- **Continuous testing (CI/CD)**
- **AI-assisted testing**

---

## 4. Career Opportunities in Software Testing

**Common roles:**
- Manual Test Engineer
- Automation Test Engineer
- QA Analyst
- Performance Tester
- Security Tester
- Test Architect
- DevOps Test Engineer

**Skills required:**
- SDLC & STLC knowledge
- Familiarity with testing tools
- Programming basics
- Analytical thinking

---

## 5. Why Should We Test Software?

Testing exists to:
- Find defects **before release**
- Avoid business losses
- Ensure user satisfaction
- Improve software quality
- Verify requirements compliance

> **Key fact to remember:** Fixing a defect *after release* costs **10x more** than fixing it during development. This is the economic argument for testing early and often.

---

## 6. Independent Verification & Validation (IV&V)

IV&V means testing is performed by a team that is **independent** of the development team.

**Benefits:**
- Ensures unbiased assessment
- Improves objectivity (no "too close to the code" blind spots)

**Typically used in:**
- Safety-critical systems
- Banking & healthcare applications (domains where an undetected bug has serious real-world consequences)

---

## 7. Phases of Software Testing (STLC)

The Software Testing Life Cycle has six sequential phases:

1. **Requirement Analysis** — understand what needs to be tested
2. **Test Planning** — define scope, strategy, resources, schedule
3. **Test Case Design** — write the actual test cases
4. **Test Environment Setup** — prepare hardware/software/data needed for execution
5. **Test Execution** — run the tests, log defects
6. **Test Closure** — evaluate results, document learnings, close the cycle

---

## 8. Software Development Process Models

These models describe *how* a software project moves from requirements to delivery — and each has direct implications for when and how testing happens.

### 8.1 Waterfall Model
A **linear, sequential** breakdown of activities: Requirements → Design → Development → Testing → Deployment → Maintenance. Each phase depends fully on the deliverables of the one before it.
- **Example use case:** Online Banking system
- **Drawback:** Difficult to accommodate change requests once a phase is complete

### 8.2 V-Model (Verification and Validation Model)
Demonstrates the direct relationship between each **development** phase and its corresponding **testing** phase — the next phase only starts once the previous one is complete.

Development side → matching Testing side:
- Requirement Analysis ↔ Acceptance Testing
- System Design ↔ System Testing
- Architecture Design ↔ Integration Testing
- Module Design ↔ Unit Testing
- Coding (center of the "V")

**Definitions reinforced here:**
- *Verification* = checking the product is built right (bug-free, meets requirements) — examining the process
- *Validation* = checking the right product was built to meet user needs — examining the outcome

**Pros:**
- Highly disciplined, phases completed one at a time
- Good for small projects with clear requirements
- Simple to understand and use
- Focuses on V&V activities early in the life cycle

**Cons:**
- Not good for complex or object-oriented projects
- Not suitable when requirements are unclear or likely to change
- Time-consuming

### 8.3 Incremental Process Model
A simple working system with only a few basic features is built first and delivered. Successive **increments/versions** are then built and delivered until the full system is complete. Each iteration passes through requirements → design → coding → testing, and each release adds functionality onto the last. It combines the Waterfall model's structure with prototyping's iterative philosophy.

**Advantages:**
- Prepares working software fast
- Clients get a clear, early idea of the project
- Changes are easier to implement
- Better risk-handling support due to iterations

**Disadvantages:**
- Requires a good team and well-planned execution
- Continuous iterations increase overall cost

### 8.4 Iterative Model
Does **not** attempt to start with a full specification of requirements. It combines the sequential structure of Waterfall with the flexibility of iterative design.

**Cycle:** Requirements Gathering → Design → Implementation → Testing → Deployment → Review & Improvement → (repeat)

Each iteration builds on the last, allowing continuous improvement until the product satisfies business needs.

**Drawbacks (of the "Iterative Waterfall" variant):**
- Difficult to incorporate change requests
- Risk handling not well supported

### 8.5 Evolutionary Process Model
Essentially: **Iterative + Incremental = Evolutionary Model.**
The development process is broken into smaller, manageable iterations, and each iteration delivers a working subset of requirements — enabling continuous testing, feedback, and refinement.

### 8.6 RAD Model (Rapid Application Development)
Emphasizes **quick, iterative release cycles**, focusing on delivering working software in shorter timelines. Designed to flex around user feedback and changing requirements.

**Phases:**
1. **Requirements Planning** — brainstorming, task analysis, form analysis, user scenarios, FAST (Facilitated Application Development Technique); produces a structured plan for the critical data and how to process it
2. **User Description** — user feedback drives prototype building; data collected earlier is re-examined and validated
3. **Construction** — the prototype is refined and delivered using powerful automated tools; modifications/enhancements happen here
4. **Cutover** — interfaces between independently-built modules (often built by separate teams in parallel) are tested thoroughly, followed by user acceptance testing

### 8.7 Prototype Model
Used when input/output requirement details **cannot be fully identified upfront** — a working program is built quickly to clarify them.

**Phases:**
1. **Communication** — client and developer meet to discuss the main objective
2. **Quick Design** — implement key visible aspects (input/output format); focus is on what the user *sees*, not the deep internal plan
3. **Modelling Quick Design** — a clearer build-state emerges; developer better understands basic requirements
4. **Construction of Prototype** — customer evaluates the prototype
5. **Deployment, Delivery, Feedback** — if the client is unsatisfied, the developer revises and repeats until satisfaction is reached; final product is then built from the accepted prototype

---

## 9. Introduction to Selenium

**Selenium** is a popular **open-source software testing framework** used for automating web applications.

- Widely used for **functional testing, regression testing, and performance testing**
- Supports multiple programming languages: **Java, C#, Python, Ruby**
- This broad language support makes it accessible to a wide range of developers

---

## 10. Application Testing vs Product Testing

### Application Testing
Focuses on testing **a specific software application** built to meet a particular customer or business's requirements.

**Purpose:**
- Ensure the app meets functional & non-functional requirements
- Detect defects before release
- Verify usability, performance, and security

**Key characteristics:**
- Built for **customized software**
- Limited scope — one application
- Customer-specific requirements
- Testing ends after deployment and acceptance

**Examples:** College ERP system, Hospital Management System, Banking web application, Mobile apps

**Common test types applied:** Functional, Integration, System, User Acceptance (UAT), Regression

### Product Testing
Focuses on testing **a software product** built for **multiple customers or the open market**.

**Purpose:**
- Ensure the product is stable, reliable, scalable, and market-ready
- Validate features across different environments and users

**Key characteristics:**
- Generic software
- Broad scope
- Market-driven requirements
- **Continuous** testing even after release (patches, new versions)

**Examples:** Operating systems, Browsers, Antivirus software, Accounting software (e.g., Tally)

**Common test types applied:** Functional, Compatibility, Performance, Security, Usability, Beta Testing

---

# MODULE 2 — SOFTWARE TESTING TECHNIQUES

## 11. Static vs Dynamic Testing

| | Static Testing | Dynamic Testing |
|---|---|---|
| Definition | Finds defects **without executing** the code | Tests the **dynamic behavior** by actually executing the code |
| Purpose | Catch errors early in the development cycle, reducing fix costs | Test the app with dynamic inputs — some allowed (**positive testing**), some disallowed (**negative testing**) |
| Example activities | Reviews, inspections, walkthroughs | Running the application, executing test cases |

---

## 12. White Box vs Black Box Testing

### Black Box Testing
The tester analyzes the software **against requirements only** — treating the internal code as an opaque "black box." Input goes in, output is checked, and defects/bugs are sent back to the development team without reference to how the code works internally.

```
Input → [ Black Box ] → Output
```

### White Box Testing
Also known as **clear box / glass box / structural / open box testing**. It analyzes the **inner functioning** of the system — the code, logic paths, and structure are visible and examined directly.

```
Input → [ White Box: internal logic visible ] → Output
```

**Advantages of White Box Testing:**
- Can be performed at the initial stages of development
- Allows discovery of hidden defects
- Helps with code optimization

---

## 13. User Interface (UI) Testing — Overview

UI testing is a technique used to identify defects in a product/software **through its Graphical User Interface (GUI)** — i.e., testing how a real user would interact with the screen.

---

## 14. Form-Level Validation & Inter-Form Dependencies

**Form validation** ensures data submitted through web forms is **accurate, consistent, and conforms to predefined rules**. If requirements aren't met, the form data is rejected — not accepted or stored.

It acts as the **first line of defense** for a business against:
- Erroneous data entry
- Malicious users injecting harmful code/viruses through forms
- Spam

**Three fundamental aspects form validation covers:**
1. **Data Accuracy** — ensures collected data is accurate and complete (important for data-driven business decisions)
2. **Security** — prevents malicious users from submitting harmful data or code, protecting the site and its users from attacks
3. **User Experience** — prevents submission of error-filled forms and tells users exactly what needs fixing, saving time and frustration

**Ways of performing form validation:**
1. **Before Submission (Inline Validation)** — checks happen as the user types/moves between fields
2. **After Submission Validation** — checks happen once the "submit" action is triggered

---

## 15. Field-Level Validation & Inter-Field Dependencies

### Field-Level Validation
Rules applied directly to a **single field** to ensure data matches required formats, ranges, or types:
- **Data Type & Format:** e.g., checking a valid email, phone number, or date
- **Required vs. Optional:** ensuring mandatory fields are filled
- **Range Checks:** validating numeric values fall within an expected range
- **Instant Feedback:** commonly performed "on blur" (when the user leaves the field) for immediate, user-friendly feedback rather than waiting for full form submission

### Inter-Field Dependencies (Dependent Behavior)
Rules that govern how fields **interact with each other**:
- **Controlling/Dependent Picklists:** a primary field (e.g., "Insurance Type") determines the available options in a dependent field (e.g., "Subtype")
- **Visibility and Read-Only:** a field becomes visible or mandatory only if another field has a specific value (e.g., "Reason for Leaving" appears only if "Status" = "Inactive")
- **Dynamic Updating:** clearing or updating a second field automatically when the first field changes

**Quick example set:**
- Email field → accepts only valid email format
- Age field → accepts numbers within a defined range

---

## 16. Error Message Validation

Error messages provide crucial information to the user — vague default messages should be customized to give as much actionable detail as possible.

**Validation methods that allow custom messages:**
- Regular Expression Validation
- Single Field Script Validation
- Multi-field Script Validation

**Example of why customization matters:**
- Default message: *"Field item does not match any of the given expressions."* → gives no specific guidance
- Better, customized message (for a customer number requiring 7 digits + 2 letters):
  *"The Customer Number entered does not meet the required format of 7 digits followed by 2 letters. Please try again."*

The improved message describes **both the problem and the solution**, so the user knows exactly how to fix their input.

---

## 17. UI Testing — Form, Field & Dependency Checks

### 17.1 Form Testing
Validates **complete forms** used for user input.

**What to test:**
- All mandatory fields clearly marked (*)
- Correct submission with valid data
- Error messages for invalid/missing inputs
- Reset/Clear button functionality
- Form submission via keyboard (Enter key)
- Form behavior on refresh/back navigation
- Proper alignment and layout of form elements

**Examples:** Registration form, Login form, Feedback form

### 17.2 Field Testing
Focuses on **individual input elements** inside a form.

**What to test:**
- Field type validation (text, number, email, password, date)
- Minimum and maximum length
- Allowed / disallowed characters
- Default values and placeholders
- Read-only and disabled fields
- Field focus, tab order, cursor behavior
- Boundary value testing

### 17.3 Dependency Testing
Ensures correct behavior when **one UI element depends on another**.

**What to test:**
- Enable/disable behavior based on selection
- Dynamic field visibility (show/hide)
- Dropdown dependencies (parent–child)
- Conditional validation rules
- API/data-driven UI changes

**Examples:**
- Selecting Country = India enables the State dropdown
- Choosing Payment = Credit Card reveals card-detail fields
- "Submit" button only enables after accepting Terms & Conditions

---

## 18. Common UI Testing Checks & Tools

**Checks to always include in a UI test pass:**
- Consistency in fonts, colors, labels
- Responsiveness (desktop, tablet, mobile)
- Cross-browser compatibility
- Accessibility (labels, contrast, keyboard navigation)
- Error message clarity and placement

**Tools commonly used:**
- Manual UI Testing
- Automation: **Selenium, Cypress, Playwright**
- Visual Testing: **Percy, Applitools**

---

## 19. Automated Test Execution with Selenium

**What Selenium does:** automates browser interactions — clicking buttons, entering text, selecting dropdowns, submitting forms — across different browsers.

### The Basic Flow of Automated Test Execution

Instead of manually testing a web app, Selenium executes **test scripts** that automatically perform actions and verify results.

1. **Write Test Script** — using languages like Java, Python, or C#; each test step represents a real user action
2. **WebDriver Launches Browser** — Selenium WebDriver opens Chrome, Firefox, Edge, etc.
3. **Locate UI Elements** — by ID, Name, XPath, CSS Selector, etc.
4. **Perform Actions** — enter text, click buttons, select values
5. **Validation (Assertions)** — check expected output vs actual output (e.g., verifying a "login successful" message appears)
6. **Test Result** — pass/fail is recorded

---

# MODULE 3 — SOFTWARE TESTING LEVELS & TYPES

## 20. Types of Software Testing — Manual vs Automation

At the top level, software testing splits into two families:

```
                Types of Software Testing
                /                        \
         Manual Testing            Automation Testing
        /      |       \
   White Box Black Box  Grey Box
              /        \
      Functional     Non-Functional
       Testing          Testing
      /    |    \            \
   Unit  Integ  System    Performance / Usability / Compatibility
         /   \                  /    |      \        \
   Incremental Non-Incr.     Load  Stress  Scalability Stability
     /    \
  Top-down Bottom-up
```

### 20.1 Manual Testing
Test cases are executed **manually by testers, without automation tools**.

**Strengths:**
- Accurate visual feedback — good at catching UI/UX issues like layout, design, and text problems
- Cost-effective — no need for expensive tools or advanced technical skill
- No coding required — beginner-friendly
- Flexible for changes — easily adapts to frequent or unplanned application changes

### 20.2 Automation Testing
Test cases are executed **using scripts and automation tools**. Best suited for repetitive, time-consuming tasks — improves efficiency, accuracy, and test coverage.

---

## 21. Functional vs Non-Functional Testing

### Functional Testing
A type of **black box testing** that verifies whether the application works according to specified requirements — by providing inputs and validating the expected outputs.
- Focuses on testing features and functions
- Validates input/output behavior of the system
- Doesn't require knowledge of internal code
- Ensures the application meets **business requirements**

### Non-Functional Testing
A type of **black box testing** that evaluates performance, usability, reliability, and other non-functional qualities.
- Focuses on performance, usability, reliability
- Checks system behavior under load and stress
- Improves user experience and system efficiency
- Ensures stability and scalability

---

## 22. Regression Testing

A type of **black box testing** that ensures **new code changes or updates do not break existing functionality**. Performed after modifications, to verify previously working features still work correctly.

- Ensures existing features work after code changes
- Performed after bug fixes, updates, or enhancements
- Helps detect unintended side effects
- Maintains overall stability and reliability

---

## 23. Testing Levels: Unit → Integration → System → UAT

These four levels form a natural progression — from the smallest piece of code up to the full, user-facing product.

### 23.1 Unit Testing
Tests **individual units or components** in isolation. Typically done by developers, usually automated, and designed to test specific functions/methods. It's the **lowest level** of testing in the development process.

### 23.2 Integration Testing
Tests **how different units/components interact with each other**, identifying and resolving issues that arise when units are combined. Done **after unit testing, before functional/system testing** — verifies the units genuinely work together as intended.

### 23.3 System Testing
Performed on the **fully integrated software system** to evaluate overall functionality, performance, and compliance with specified requirements. Conducted **after integration testing, before acceptance testing** — uses the components already verified in integration testing to confirm the system as a whole is correct and ready for delivery.

### 23.4 User Acceptance Testing (UAT)
Ensures the software meets **business requirements** and is ready for **deployment**, by validating functionality in a real-world environment.

**Advantages:**
- Surfaces further requirements directly from users (since users are directly involved)
- Supports automated test execution
- Builds client confidence and satisfaction (they're directly part of testing)
- Easier for users to describe their actual requirements when testing hands-on

---

## 24. Performance & Load Testing

### Performance Testing
Ensures software applications **perform properly under expected workload**. Determines system performance in terms of **sensitivity, reactivity, and stability** under a particular workload.

**Advantages:**
- Confirms speed, load capability, accuracy, and other performance qualities
- Identifies, monitors, and resolves performance issues as they occur

### Load Testing (a sub-type of Performance Testing)
Ensures the application can handle the **expected number of concurrent users or transactions** without performance degradation.

> **Note:** Load Testing is typically classified as a type of Performance Testing, and by extension also falls under the broader category of Non-Functional Testing.

---

## 25. Acceptance Testing

Performed **by the customers** to check whether delivered products perform the desired tasks as stated in the requirements. **Object-Oriented Testing** is used for discussing test plans and executing projects in this context.

**Advantages:**
- Surfaces further user requirements directly (users are directly involved)
- Supports automated test execution
- Builds client confidence — they're directly part of the testing process

---

## 26. Localization Testing

A type of software testing performed to **verify the quality of a product for a specific culture or locale**. It is performed only on the **local/regional version** of the product.

**Advantages:**
- Reduces overall testing cost
- Reduces overall support cost
- Reduces testing time
- Adds flexibility and scalability to the testing process

---

## 27. Topics Named But Not Detailed in the Source Slides

Module 3's title slide lists a broader syllabus than the content slides actually cover. The following were named in the module outline but **did not have dedicated content slides** in the uploaded PDF, so they aren't detailed above — flagging this so you know to source them separately if needed for exam prep:

- Overview of Security Testing
- Usability Testing
- Exploratory Testing
- Compatibility Testing
- Role-Based Access Testing
- Mobility Testing
- Automation support for regression testing using Selenium (beyond the general Selenium flow covered in Module 2)

---

# QUICK-REVISION CHEAT SHEET

**V&V in one line:** Verification = right *process* (static, no execution). Validation = right *product* (dynamic, executes code).

**Testing pyramid (bottom → top):** Unit → Integration → System → UAT

**Black Box vs White Box:** Black box = requirements-driven, no code knowledge needed. White box = internal logic visible, finds hidden defects, enables code optimization.

**Static vs Dynamic:** Static = no execution (reviews). Dynamic = execution (positive + negative testing).

**Process models memory hooks:**
- Waterfall → strictly linear, hard to change
- V-Model → each dev phase mirrored by a test phase
- Incremental → ship small, add features release by release
- Iterative → repeat full cycles, refining each time
- Evolutionary → Iterative + Incremental combined
- RAD → speed-focused, prototype-heavy, parallel team modules
- Prototype → build fast when requirements are unclear, refine via client feedback loops

**Functional vs Non-Functional:** Functional = *what* it does (features). Non-functional = *how well* it does it (speed, usability, reliability).

**Regression testing trigger:** any code change → re-verify nothing else broke.

**Performance testing family:** Performance (umbrella) → Load, Stress, Scalability, Stability (sub-types).

**Selenium in one line:** Open-source, multi-language (Java/C#/Python/Ruby) browser automation framework — write script → WebDriver launches browser → locate elements → perform actions → assert results.

**Form vs Field validation:** Form validation = whole-submission rules (accuracy, security, UX). Field validation = single-field rules (type, format, range), often triggered "on blur."

**10x Rule:** A defect fixed after release costs roughly 10x more than the same defect fixed during development — the core economic reason testing exists.
