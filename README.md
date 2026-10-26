# Software Testing and Automation
## Final-Semester Examination Study Guide

**Based on the six modules in `PPT_1-6.zip`**  
**Style:** simple explanations, exam-ready definitions, step-by-step processes, comparison tables, examples, and revision questions.

---

## How to use this guide

Read each topic until you can explain it in your own words. For an exam answer, use this simple structure:

1. **Definition:** Explain what the term means.
2. **Purpose:** State why testers use it.
3. **Steps or types:** Explain the process or list the main categories.
4. **Example:** Connect it to a login page, shopping cart, booking system, or another familiar application.
5. **Advantages and limitations:** Include these when the question asks for discussion or evaluation.

For a short 2-mark answer, give a clear definition and one key point. For a 5-mark answer, add the purpose, important features, and an example. For a long answer, include a heading, definition, process or diagram, detailed explanation, advantages, limitations, and a conclusion. Match the length to the question and the marks available.

**Source note:** The material below follows the six module PDFs included in the ZIP. Some topics appear only in the module outline, without a detailed explanation in the slides. The guide identifies those gaps instead of inventing course-specific details. Numerical targets and cost estimates quoted from the slides represent the lecture examples, not universal rules for every project.

# Module 1: Introduction to Software Testing and Automation

## 1.1 What is software testing?

**Software testing** is the process of evaluating software to find defects and check whether the system meets its requirements and user expectations. Testing helps teams assess software quality, reliability, performance, and security.

A simple example is a login page. A tester checks whether a registered user can sign in with the correct password, whether the page rejects an incorrect password, and whether it displays a useful error message instead of crashing.

### Why do we test software?

Software testing helps a team:

- Find defects before the product reaches users.
- Reduce business losses caused by incorrect or unreliable software.
- Improve software quality and user satisfaction.
- Check whether the software follows its requirements.
- Build confidence that the product works under the conditions the team expects.

The slides stress that defects generally cost more to fix when they escape into production. One slide estimates that a production fix may cost around ten times as much as a fix during development; another module gives a more detailed cost model that rises to 100 times in production. Treat these as lecture illustrations of the same principle: **find and fix defects early**.

## 1.2 Verification and validation (V&V)

Verification and validation are related, but they ask different questions.

### Verification

**Verification asks: “Are we building the product right?”** It checks whether documents, designs, code, and other work products follow the specified requirements. The slides describe verification as a **static process**, because reviewers can examine work without running the software.

Examples include reviewing a requirements document, inspecting a design, or reviewing code for errors.

### Validation

**Validation asks: “Are we building the right product?”** It checks whether the finished software meets the user's needs. The slides describe validation as a **dynamic process**, because testers execute the software and observe its behaviour.

For a payment app, verification might check that the design follows the stated payment rules. Validation might run a payment scenario and confirm that the correct account receives the money.

| Verification | Validation |
|---|---|
| Checks work products against specifications | Checks whether the product meets user needs |
| Usually static | Usually dynamic |
| Can use reviews and inspections | Requires executing the software in the slide's description |
| Can begin early in development | Often checks the working product against real needs |
| Question: “Are we building it right?” | Question: “Are we building the right product?” |

**Exam tip:** Memorize the two questions first. They provide an easy way to explain the difference.

## 1.3 Independent Verification and Validation (IV&V)

**Independent Verification and Validation (IV&V)** means a separate, independent team evaluates the software. The team provides an assessment that does not rely entirely on the developers' own judgment.

The slides identify these benefits:

- It improves objectivity.
- It reduces the chance that the team overlooks defects because it is too close to its own work.
- It supports independent assessment of product quality.

The slides list safety-critical systems, banking applications, and healthcare applications as places where IV&V can be useful.

## 1.4 Software testing market and career paths

The slides describe rising demand for testing as cloud computing, mobile applications, AI systems, and Internet of Things (IoT) systems grow. They also identify automation testing, continuous testing through CI/CD, and AI-assisted testing as important directions.

The listed career roles are:

- **Manual Test Engineer:** Executes test cases without automation scripts.
- **Automation Test Engineer:** Writes and maintains scripts that execute tests automatically.
- **QA Analyst:** Reviews requirements, plans testing, and assesses quality.
- **Performance Tester:** Studies speed, stability, and behaviour under workload.
- **Security Tester:** Looks for security weaknesses.
- **Test Architect:** Designs the overall testing approach and supporting structure.
- **DevOps Test Engineer:** Connects testing with build, deployment, and delivery workflows.

The slides identify SDLC and STLC knowledge, familiarity with testing tools, programming basics, and analytical thinking as useful skills.

## 1.5 Software Testing Life Cycle (STLC)

The **Software Testing Life Cycle (STLC)** describes the main phases that organize testing work.

1. **Requirement analysis:** Study the requirements and identify what the team must test. Ask questions when a requirement is missing or unclear.
2. **Test planning:** Decide the testing scope, approach, people, tools, schedule, risks, and completion criteria.
3. **Test case design:** Write test conditions, test data, steps, and expected results.
4. **Test environment setup:** Prepare the hardware, software, browser, database, accounts, and data needed for testing.
5. **Test execution:** Run the test cases, compare actual results with expected results, record pass/fail status, and report defects.
6. **Test closure:** Review the results, prepare the test summary, record remaining risks, and document lessons learned.

**Memory sequence:** Requirements → Plan → Design → Environment → Execute → Close.

## 1.6 Software development process models

A **software process model** organizes how a team plans, builds, tests, and releases software. The slides name Waterfall, V-Model, Incremental, RAD, Agile, Iterative, Spiral, and Prototype models. The slides explain some models in detail and only name Agile and Spiral in the overview list.

### Waterfall model

The **Waterfall model** divides development into sequential phases. Each phase depends on the output of the previous phase. A team normally completes one phase before moving to the next.

**Example from the slides:** An online banking system.

**Main limitation:** It is difficult to accommodate change requests once the team has moved through earlier phases. This can make Waterfall less flexible when requirements change.

**Exam-ready explanation:** Waterfall is a linear, sequential development model in which each phase follows the previous one. It provides a clear sequence of work, but late requirement changes can be difficult to handle.

### V-Model

The **V-Model**, also called the Verification and Validation model, connects each development phase with a related testing phase. Its central idea is to plan testing alongside development instead of leaving all testing until the end.

The slides describe requirements gathering and analysis, design, implementation, testing, deployment, and maintenance. The key testing idea is that development decisions should have corresponding checks that establish whether those decisions meet specifications and user needs.

**Advantages listed in the slides:**

- Clear and disciplined phases.
- Simple to understand and use.
- Useful for smaller projects with clear requirements.
- Encourages verification and validation activities early in the life cycle.

**Limitations listed in the slides:**

- Not well suited to complex or object-oriented projects, according to the lecture notes.
- Not suitable when requirements are unclear or likely to change frequently.
- Can be time-consuming.

### Incremental model

The **Incremental model** delivers the system in small working parts. The team first releases a basic version, then adds features through successive versions until the product meets its requirements.

Each increment passes through activities such as requirements, design, coding, and testing. A later release extends the previous release rather than replacing the whole idea with a completely new product.

**Advantages listed in the slides:**

- The team can prepare an initial working version quickly.
- Customers can see progress and gain a clearer idea of the product.
- The team can implement changes more easily than in a strictly sequential approach.
- Repeated increments help the team identify and manage risks.

**Limitations listed in the slides:**

- The process requires good planning and a capable team.
- Repeated iterations can increase cost.

### Iterative model

The **Iterative model** develops and improves the system through repeated cycles. A team does not have to define every detail of the final requirements before starting. It builds an initial version, tests it, reviews the result, and improves the next version.

The slides illustrate a cycle of requirements gathering, design, implementation, testing, deployment, review, and improvement. The cycle repeats until the product meets the project's goals.

**Limitation noted in the slides for the iterative waterfall approach:** It can be difficult to incorporate change requests, and the slide says risk handling is not supported. Keep this limitation attached to the model wording used by the lecture rather than applying it to every possible iterative method.

### Rapid Application Development (RAD)

**RAD** emphasizes quick development cycles and rapid delivery of working software. It uses prototypes and user feedback to refine the product and aims to respond to changing needs.

The slides list four phases:

1. **Requirements planning:** Collect and refine requirements through methods such as brainstorming, task analysis, forms analysis, and user scenarios.
2. **User description:** Gather user feedback, review the collected information, and define relevant data and features.
3. **Construction:** Refine prototypes and turn the data and process models into a working product, using development tools.
4. **Cutover:** Test the connections between modules, carry out acceptance testing, and prepare the system for use.

### Evolutionary process model

The slides describe the evolutionary model as combining **iterative and incremental** ideas. The project is split into manageable parts. Each part adds functionality and creates an opportunity for testing, feedback, and refinement.

### Prototype model

A **prototype** is an early model of a product that helps users and developers clarify what the finished system should do. The slides present this model as useful when the exact inputs, outputs, or requirements are not yet clear.

The phases shown are:

1. **Communication:** The client and developer discuss the project's main objective.
2. **Quick design:** Create a simple design focused on visible features and input/output behaviour.
3. **Modelling the quick design:** Develop the initial working representation so the team can understand the basic requirements.
4. **Construction of prototype:** Build a prototype for the customer to evaluate.
5. **Deployment, delivery, and feedback:** Collect the customer's feedback and repeat changes until the client is satisfied. The final product then uses the approved prototype as a basis.

### Process-model comparison

| Model | Main idea in the slides | Main point to remember |
|---|---|---|
| Waterfall | Complete phases in sequence | Late changes are difficult |
| V-Model | Link development phases with testing phases | Plan verification and validation early |
| Incremental | Deliver functionality in small releases | Each release adds to the product |
| Iterative | Improve the product through repeated cycles | Feedback guides each improvement |
| RAD | Use rapid cycles and prototypes | Quick delivery and user feedback |
| Evolutionary | Combine iterative and incremental ideas | Build, test, learn, and refine in parts |
| Prototype | Build an early model to clarify requirements | Customer feedback helps define the final system |

**Coverage note:** The slides name Agile and Spiral models in the list of process models, but the provided slide text does not give a detailed explanation of either one.

## 1.7 Application testing and product testing

### Application testing

**Application testing** focuses on a specific software application created for a customer or business. The goal is to confirm that the application meets its functional and non-functional requirements and to find defects before release.

Characteristics from the slides:

- Often tests customized software.
- Has a limited scope focused on one application.
- Uses customer-specific requirements.
- The slides describe testing as ending after deployment and acceptance.

Examples include a college ERP system, hospital management system, banking web application, and mobile app.

The listed test types are functional testing, integration testing, system testing, user acceptance testing, and regression testing.

### Product testing

**Product testing** evaluates a software product intended for many customers or the open market. It checks whether the product is stable, reliable, scalable, and ready for a broad range of users and environments.

Characteristics from the slides:

- Tests generic software for many users.
- Has a broader scope than one customized application.
- Responds to market-driven requirements.
- Continues after release as the vendor delivers patches and new versions.

Examples include operating systems, browsers, antivirus programs, and accounting software.

The slides list functional, compatibility, performance, security, usability, and beta testing.

| Application testing | Product testing |
|---|---|
| Focuses on a specific application | Focuses on a product for many customers |
| Often uses customer-specific requirements | Uses broader, market-driven requirements |
| Example: hospital management system | Example: browser or antivirus product |
| Scope centres on the application | Scope includes different users and environments |
| Slides associate it with deployment and acceptance | Slides describe testing continuing through patches and versions |

## 1.8 Introduction to Selenium

The slides describe **Selenium** as an open-source framework for automating web applications. It supports several programming languages, including Java, C#, Python, and Ruby, and appears in functional and regression testing workflows.

A basic Selenium test follows this pattern:

1. Write a test script that describes user actions.
2. Start a browser using WebDriver.
3. Locate page elements such as fields and buttons.
4. Perform actions such as typing and clicking.
5. Compare the actual result with the expected result.

The slides in Module 1 mention Selenium in connection with performance testing, while later modules distinguish browser automation with Selenium from load/performance testing with JMeter. See the source note near the end of this guide.

### Module 1 revision questions

1. Define software testing and state five reasons for testing.
2. Explain verification and validation with an example.
3. What is Independent Verification and Validation? Why is it useful?
4. List and explain the six phases of STLC.
5. Explain the Waterfall model with one advantage and one limitation.
6. Explain the V-Model and list its advantages and limitations.
7. Compare the Incremental and Iterative models.
8. Explain the phases of RAD.
9. Explain the Prototype model and its feedback cycle.
10. Differentiate application testing from product testing.

---

# Module 2: Software Testing Techniques and User Interface Testing

## 2.1 Static testing

**Static testing** finds defects without executing the software. A tester or reviewer examines requirements, design documents, code, or other work products. The slides emphasize that teams can use static testing early in development and reduce the cost of fixing errors.

Examples from the ideas in the slides include reviewing a requirements document for unclear wording and examining code without running it.

**Main purpose:** Catch problems early, before they move into later development or testing stages.

## 2.2 Dynamic testing

**Dynamic testing** evaluates software by executing its code. The tester supplies inputs and checks the system's actual behaviour.

The slides connect dynamic testing with:

- **Positive testing:** Provide valid inputs that the requirements say the system should accept.
- **Negative testing:** Provide invalid or disallowed inputs and check that the system handles them correctly.

For example, entering a valid email address in a registration form is a positive test. Entering an invalid email address and checking that the system rejects it with a clear message is a negative test.

| Static testing | Dynamic testing |
|---|---|
| Does not execute the code | Executes the software |
| Examines requirements, design, or code | Checks behaviour using inputs and observed outputs |
| Can identify issues early | Reveals problems that appear during execution |
| Helps reduce later correction cost | Checks whether the running application behaves correctly |

## 2.3 Black-box testing

**Black-box testing** checks a system against its requirements without needing to understand its internal code. The tester supplies inputs and checks outputs or visible behaviour.

The tester asks questions such as: “If the user enters a valid password, does login succeed?” and “If the user enters an invalid password, does the system reject it correctly?”

The slides describe the tester as analyzing the software against requirements, identifying defects, and reporting them to the development team.

## 2.4 White-box testing

**White-box testing** examines the internal working structure of the system. The slides also call it clear-box, glass-box, structural, or open-box testing.

The tester considers the internal code or structure, rather than treating the software as a closed box. The slides list these advantages:

- It can begin at early development stages.
- It can reveal hidden defects.
- It can help with code optimization.

### Black-box vs white-box testing

| Black-box testing | White-box testing |
|---|---|
| Focuses on requirements, inputs, and outputs | Focuses on internal code and structure |
| Does not require knowledge of the internal code | Requires knowledge of the internal implementation |
| Example: submit a login form and inspect the result | Example: inspect the code path handling login failure |
| Checks externally visible behaviour | Checks internal paths and implementation behaviour |

## 2.5 User Interface (UI) testing

**UI testing** checks the software through its graphical user interface (GUI). It verifies that forms, input fields, controls, messages, and interactions behave as expected.

The slides divide UI testing into form testing, field testing, and dependency testing.

### Form-level validation

**Form validation** checks whether the data submitted through a form is accurate, complete, consistent, and consistent with predefined rules. When a form contains invalid data, the system should reject the submission or ask the user to correct the problem.

Form validation matters for three reasons:

1. **Data accuracy:** The application receives complete and correctly formatted information.
2. **Security:** Validation helps prevent harmful or unexpected inputs from passing through the form. It is only one part of security, not a replacement for other security controls.
3. **User experience:** Clear feedback tells the user what needs correction and avoids unnecessary frustration.

The slides identify two approaches:

- **Before submission / inline validation:** The page checks the input while the user fills in the form, such as after the user leaves a field.
- **After submission validation:** The system checks the form when the user submits it and reports invalid or missing information.

### Inter-form dependencies

**Inter-form dependencies** describe a relationship between different forms or between steps of a larger workflow. The provided slides mention this topic in the outline and discuss dependent behaviour more fully under inter-field dependencies. They do not provide a detailed standalone treatment of inter-form dependency testing.

### Field-level validation

**Field-level validation** applies rules to a single input field. It checks whether the field's value follows the required type, format, range, and other rules.

Important checks listed in the slides include:

- **Data type and format:** An email field should accept valid email formats; a date field should accept valid dates.
- **Required vs optional:** Required fields must contain values, while optional fields may remain empty.
- **Range checks:** A numeric value must fall within the permitted range.
- **Allowed characters:** The field should accept permitted characters and reject disallowed ones.
- **Length checks:** A field may require a minimum or maximum number of characters.
- **Default values and placeholders:** They should display the intended guidance or initial value.
- **Read-only and disabled fields:** They should behave as specified.
- **Focus, tab order, and cursor behaviour:** Keyboard navigation should work sensibly.
- **Boundary values:** Test values near the limits of a permitted range.

The slides recommend giving immediate feedback, often when the user leaves a field, rather than always waiting for the final submission.

### Inter-field dependencies

**Inter-field dependencies** control how the value or selection in one field affects another field. They guide users toward valid combinations of data.

Examples from the slides:

- Selecting an insurance type controls the available insurance subtype options.
- A “Reason for Leaving” field appears only when the employment status is “Inactive.”
- Selecting “Country = India” enables the State dropdown.
- Selecting “Credit Card” as the payment method reveals card-detail fields.
- The Submit button remains disabled until the user accepts the terms and conditions.

Tests should check that dependent fields appear, disappear, become enabled or disabled, become required, and update correctly. If a user changes a parent field, the system should clear or update dependent values when necessary.

### Error-message validation

An error message should explain the problem clearly enough for the user to correct it. A generic error may confirm that validation failed but still leave the user unsure about what to do next.

The slides discuss custom error messages for regular-expression validation and script-based single-field or multi-field validation.

**Example from the slides:** If a customer number must contain seven digits followed by two letters, a useful message says that the number must follow the “7 digits followed by 2 letters” format and asks the user to try again.

A useful error message should:

- Identify which field has a problem.
- Explain the expected format or rule.
- Avoid vague wording when a specific explanation is possible.
- Appear close enough to the field that the user can connect the message with the error.
- Avoid exposing sensitive internal details.

## 2.6 UI test checklist

### Form testing

Check that:

- Required fields are clearly marked.
- Valid data submits successfully.
- Missing or invalid values produce appropriate errors.
- Reset and Clear buttons work.
- The Enter key submits the form where appropriate.
- Refresh and Back navigation do not create unexpected behaviour.
- Form controls align and display correctly.

Examples include registration, login, and feedback forms.

### Field testing

Check field types, minimum and maximum lengths, permitted characters, default values, placeholders, read-only and disabled states, focus behaviour, tab order, and boundary values.

### Dependency testing

Check enable/disable rules, conditional visibility, parent-child dropdowns, conditional validation, and UI changes driven by data or API responses.

### Common UI checks

The slides also list consistency in fonts, colours, and labels; responsiveness on desktop, tablet, and mobile; cross-browser compatibility; accessibility; keyboard navigation; and clear error-message placement.

The tools named in this area include manual UI testing, Selenium, Cypress, Playwright, Percy, and Applitools.

## 2.7 Basic automated test execution with Selenium

Selenium automates browser interactions, including clicking buttons, entering text, choosing dropdown options, and submitting forms.

A simple workflow:

1. Write a test script in a supported language such as Java, Python, or C#.
2. Use WebDriver to start a browser.
3. Find elements using locators such as ID, Name, XPath, or CSS Selector.
4. Perform user actions.
5. Use assertions to compare actual behaviour against expected behaviour. For example, verify that a successful login displays a dashboard page.

### Module 2 revision questions

1. Define static testing and dynamic testing. Compare them.
2. Explain black-box testing and white-box testing.
3. What is form validation? Explain its importance.
4. Differentiate inline validation from validation after submission.
5. Explain field-level validation with examples.
6. What are inter-field dependencies? Give three examples.
7. What makes an error message useful?
8. Write a UI testing checklist for a registration form.
9. Describe the basic workflow of automated testing with Selenium.

---

# Module 3: Software Testing Levels and Types

## 3.1 Manual testing

**Manual testing** means that a tester executes the test steps by hand without using automation tools to perform them.

The slides identify these strengths:

- It gives direct visual feedback and can reveal layout, design, text, and user-experience problems.
- It can be cost-effective for small or short testing tasks because it does not require a dedicated automation setup.
- It does not require programming knowledge for basic execution.
- It can adapt quickly to frequent or unexpected changes.

Manual testing still requires careful planning, clear test cases where appropriate, accurate observations, and reliable defect reports.

## 3.2 Automation testing

**Automation testing** uses scripts and tools to execute test cases. It is especially useful for repetitive and time-consuming tasks and can improve efficiency, consistency, and test coverage.

Examples include rerunning a login test after every code change or checking the same workflow in multiple browsers.

### Manual vs automated testing

| Manual testing | Automation testing |
|---|---|
| A person performs the steps | A script or tool performs the steps |
| Useful for exploratory, usability, and ad hoc checks | Useful for repetitive tests, regression, and data-driven tests |
| Usually has lower initial setup cost | Requires initial script development and setup |
| Can adapt easily to an unplanned change | Scripts require maintenance when the application changes |
| Execution speed depends on the tester | Can rerun many tests quickly and repeatedly |
| Human judgment helps assess look and feel | Automated visual tools can compare images, but need setup and suitable checks |

Automation does not replace all manual testing. It reduces repetitive work so testers can spend more time investigating unusual behaviour, usability, and new risks.

## 3.3 Functional testing

**Functional testing** checks whether the application's features work according to specified requirements. It supplies inputs and verifies the expected outputs without needing to understand the internal code.

Examples:

- A valid username and password open the dashboard.
- An invalid password produces the expected error.
- A shopping cart adds the selected product and updates the cart count.
- A payment operation follows the required business rules.

The focus is on **what the application does**.

## 3.4 Non-functional testing

**Non-functional testing** evaluates how well the application operates. The slides list performance, usability, and reliability, and discuss how the system behaves under different loads and conditions.

The focus is on characteristics such as speed, stability, efficiency, scalability, and user experience, rather than only whether a feature produces the correct result.

### Functional vs non-functional testing

| Functional testing | Non-functional testing |
|---|---|
| Checks features and business rules | Checks quality characteristics and operating behaviour |
| Example: valid login succeeds | Example: login completes within an acceptable response time |
| Focuses on required outputs and actions | Focuses on speed, reliability, usability, or stability |

## 3.5 Regression testing

**Regression testing** checks that new code, a bug fix, or an enhancement has not broken features that worked previously.

Why it matters: a developer may correct one problem but accidentally affect another feature. Regression tests help catch such side effects before release.

Examples:

- After changing the login page, rerun login, password reset, and session-related tests.
- After modifying checkout, test the cart, price calculation, payment, order confirmation, and cancellation paths that the change may affect.

The slides classify regression testing as a type of black-box testing and identify it as a key candidate for automation because teams may need to repeat it after many changes.

## 3.6 Testing levels

Testing levels describe **how much of the system the team tests at a time** and how far it has progressed toward a complete product.

### Unit testing

**Unit testing** tests a small, individual part of the application, such as a function, method, or component. Developers commonly perform it. Tests usually isolate one unit from the rest of the system.

Example: Test a discount-calculation function with several prices and discount values.

### Integration testing

**Integration testing** checks whether different components work correctly together. It helps find problems in the way modules exchange data or call one another.

Example: The checkout service creates an order, the payment service confirms payment, and the inventory service decreases stock. Integration testing checks that the modules communicate correctly.

### System testing

**System testing** checks the fully integrated application as a whole. It evaluates overall functionality, performance, and compliance with the stated requirements. The slides place it after integration testing and before acceptance testing.

Example: Test a complete online shopping flow from login through checkout and order confirmation.

### User Acceptance Testing (UAT)

**User Acceptance Testing (UAT)** checks whether the system meets business requirements and is ready for deployment. Customers or intended users validate the product in realistic scenarios.

The slides list these benefits:

- The team receives direct feedback from users.
- Users can explain additional or unclear requirements.
- User participation increases confidence in the product.

### Comparison of testing levels

| Level | Main focus | Typical performer in the slides | Example |
|---|---|---|---|
| Unit | One small unit in isolation | Usually developers | Discount function returns the correct value |
| Integration | Communication between components | Testing/development team | Payment confirmation updates the order correctly |
| System | The complete integrated application | Test team | Full shopping workflow behaves correctly |
| UAT | Business needs and readiness for use | Customers or users | A user confirms that a business process works as expected |

**Memory sequence:** Unit → Integration → System → Acceptance.

## 3.7 Performance testing

**Performance testing** checks whether the application behaves properly under its expected workload. The slides describe it as examining sensitivity, responsiveness, stability, speed, load capacity, and other performance characteristics under a particular workload.

Performance testing helps a team identify performance problems, observe them, and decide what to improve.

## 3.8 Load testing

**Load testing** checks whether an application can handle the expected number of concurrent users or transactions without unacceptable performance degradation.

For example, a ticket-booking website may need to support many users trying to book tickets at the same time. The team tests the expected workload to see whether the site continues to respond correctly.

The slides classify load testing as a type of performance testing and as part of non-functional testing.

## 3.9 Acceptance testing

The slides have a separate acceptance-testing slide in addition to the UAT slide. They define acceptance testing as checking, often with customer involvement, whether the delivered product performs the required tasks. It helps identify user needs and increases customer confidence.

For exam answers, explain the idea once, then mention UAT as the user-focused acceptance stage described earlier. Avoid treating the two slides as unrelated concepts unless the exam question defines a distinction.

## 3.10 Other testing types named in the slides

The Module 3 outline names several additional types. Some receive only a short definition in the supplied slides; others appear in the outline without a detailed explanation.

### Localization testing

**Localization testing** checks the quality of a product version prepared for a specific culture or locale. The slides say it applies to the localized version of the product and list lower overall testing cost, lower support cost, shorter testing time, flexibility, and scalability as benefits.

Example: Test a localized version to ensure its displayed text and locale-specific information match that version's requirements.

### Security testing

Security testing appears in the module outline, and Module 6 classifies security defects as vulnerabilities that can allow unauthorized access. The slides give examples such as one user being able to view another user's order history, SQL injection risk, hardcoded passwords, and cross-site scripting (XSS). They name penetration testing in connection with security defects but do not provide a full security-testing procedure in Module 3.

### Internationalization testing

Internationalization testing appears in the Module 3 outline, but the slides provide a definition for localization testing rather than a separate detailed definition for internationalization testing. The provided material does not explain the distinction in detail.

### Usability testing

Usability testing appears in the outline. Module 6 describes a usability defect as a feature that works but confuses users, such as a “Next” button that looks disabled even though it is clickable. A detailed usability-testing procedure does not appear in the supplied Module 3 slides.

### Exploratory testing

The slides describe exploratory testing as **unscripted testing in which the tester explores freely**. They suggest it for new features and unclear requirements. It uses tester observation and investigation rather than relying only on a fixed set of steps.

### Compatibility testing

Compatibility testing appears in the outline, and Module 6 gives the example of checkout working in Chrome but failing in Safari. It checks whether the software works across relevant browsers, devices, operating systems, or environments. The supplied slides do not give a detailed compatibility-testing process.

### Role-based access testing and mobility testing

Both topics appear in the Module 3 outline. The provided slides do not explain their procedures in detail. The guide therefore does not add a course-specific workflow for either topic.

### Module 3 revision questions

1. Differentiate manual testing from automation testing.
2. Explain functional, non-functional, and regression testing with examples.
3. Explain unit, integration, system, and acceptance testing in sequence.
4. Differentiate performance testing and load testing.
5. What is UAT? State its advantages.
6. Define localization testing and state its benefits.
7. Explain exploratory testing using the slide's description.
8. Give examples of security, usability, and compatibility defects from the lecture material.

---

# Module 4: Testing Process, Test Design, Defect Management, and CI/CD

## 4.1 Test strategy vs test plan

A **test strategy** is a high-level document that defines the overall testing approach. The slides say a QA Manager or Test Director creates it for an organization or program, and the organization may update it periodically. Example: “Automate all regression tests using Selenium and Jenkins.”

A **test plan** describes how testing will work for one project or release. It covers the scope, schedule, resources, risks, and other project-specific details. The slides associate it with a Test Lead or Test Manager and refer to IEEE 829.

| Test strategy | Test plan |
|---|---|
| High-level testing approach | Detailed plan for a particular project or release |
| Organization or program scope | Single project/release scope |
| Created by QA Manager/Test Director in the slides | Created by Test Lead/Test Manager in the slides |
| Example: regression automation policy | Example: number of test cases, testers, and duration for a sprint |

## 4.2 Test plan components (IEEE 829 list in the slides)

The slides list 13 sections:

1. **Test Plan Identifier:** Unique ID, version, and date.
2. **Introduction:** Purpose and project overview.
3. **Test Items:** Components that the team will test.
4. **Features to Be Tested:** Features inside the testing scope.
5. **Features Not to Be Tested:** Excluded features and the reason for exclusion.
6. **Test Approach:** Manual or automated approach, tools, and techniques.
7. **Pass/Fail Criteria:** Conditions that determine whether a test passes.
8. **Entry and Exit Criteria:** Conditions for starting and stopping testing.
9. **Test Deliverables:** Reports, logs, defect lists, and other outputs.
10. **Test Environment:** Hardware, operating system, browsers, databases, and configuration.
11. **Schedule:** Timeline and milestones.
12. **Risks and Contingencies:** Possible problems and plans to reduce their impact.
13. **Responsibilities:** Who performs each activity.

## 4.3 Entry, exit, suspension, and resumption criteria

**Entry criteria** define the conditions that must be met before a test phase begins. The slides list a build deployed to the QA environment, successful smoke tests, prepared test data, a configured environment, and reviewed/approved test cases.

**Exit criteria** define the conditions that must be met before the team finishes the phase. The example criteria in the slides are:

- At least 95% of test cases executed.
- A pass rate that meets the agreed threshold, such as 95%.
- No open Critical or High severity defects.
- Stakeholder sign-off on the Test Summary Report.

**Suspension criteria** identify when the team should pause testing. The slides give an example: more than 30% of critical tests fail.

**Resumption criteria** identify when testing can restart. The slides say to resume after the team deploys a new stable build.

These percentages are examples from the slide deck. A real project should use the thresholds agreed in its own test plan.

## 4.4 Understanding requirements before testing

Requirements analysis is not just reading a document and immediately writing tests. A tester should identify unclear, missing, or conflicting requirements before designing test cases.

The slides recommend:

1. Read the SRS (Software Requirements Specification) or BRD (Business Requirements Document).
2. Identify unclear, missing, or conflicting statements.
3. Write down every question and doubt.
4. Hold a review with relevant business analysts, developers, and project managers.
5. Obtain approval for the clarified requirements.

The slides state that many defects begin in the requirements phase and that a defect found in production costs far more to fix. The practical lesson is to resolve uncertainty early.

## 4.5 Ambiguity reviews

An **ambiguity review** is a structured review of requirements to find wording that is unclear, incomplete, open to multiple interpretations, or contradictory.

Ambiguity reviews matter because unclear requirements can lead to incorrect test cases, incorrect implementation, and expensive rework.

### Types of ambiguity

#### 1. Lexical ambiguity

A word or phrase has more than one possible meaning.

Example: “The system should respond fast.” Does “fast” mean 100 milliseconds, one second, or ten seconds?

**How to fix it:** Replace vague words with measurable definitions.

#### 2. Syntactic ambiguity

The sentence structure allows more than one interpretation.

Example: “Test login with admin and user module.” Does the requirement mean testing the two modules together or separately?

**How to fix it:** Rewrite the sentence using bullets, numbered conditions, and clear relationships between actions.

#### 3. Semantic ambiguity

The words are understandable, but the requirement lacks enough context.

Example: “The system shall notify the user.” The requirement does not specify whether the system should use email, SMS, push notifications, or all three.

**How to fix it:** Ask “How?”, “When?”, “What content?”, and “Which channel?”

#### 4. Incomplete requirements

The requirement does not describe important scenarios, especially error cases.

Example: “Users can reset their password.” The requirement does not say what happens when the email address does not exist or the account is locked.

**How to fix it:** Ask “What if...?” for each requirement, including failures, invalid inputs, timeouts, and unusual conditions.

### Example: order confirmation

The slides use the requirement “After placing an order, the user shall receive a confirmation.” A tester should ask:

- Which channel delivers the confirmation: email, SMS, push, or more than one?
- What should the message contain?
- Should it appear after payment, after order creation, or after the restaurant accepts?
- What happens if the user disables notifications?
- What happens if the restaurant takes too long to accept?

One vague statement can therefore lead to several precise requirements and better test cases.

## 4.6 Test cases

A **test case** is a documented set of conditions and steps used to check a particular behaviour. The slides list inputs, execution steps, preconditions, expected results, and postconditions as its components.

### Properties of a good test case

- **Atomic:** Tests one main thing at a time.
- **Repeatable:** Produces a consistent result when the conditions are the same.
- **Independent:** Does not rely unnecessarily on another test.
- **Traceable:** Links to a requirement or user story.
- **Clear:** Another tester can execute it without needing the author's explanation.

### Test case template

| Field | Purpose or example from the slides |
|---|---|
| Test Case ID | Unique identifier, such as `TC_LOGIN_007` |
| Title | Verify login with an invalid password |
| Module | Authentication |
| Linked Requirement | Requirement or user story under test |
| Priority | Example: High |
| Preconditions | Registered user, browser open, login page displayed |
| Test Steps | Enter valid email, enter wrong password, click Login |
| Test Data | Email and incorrect password |
| Expected Result | Specific invalid-password message appears |
| Actual Result | Filled in during execution |
| Status | Pass, Fail, or Blocked |
| Defect ID | Link to a defect if the test fails |

### Test case design techniques

#### Equivalence Partitioning (EP)

**Equivalence Partitioning** divides possible inputs into groups expected to behave in the same way. The tester selects representative values from each group instead of testing every possible value.

Example from the slides: If a field accepts ages from 18 through 60:

| Partition | Example value | Expected result |
|---|---:|---|
| Below minimum | 15 | Reject |
| Valid range | 35 | Accept |
| Above maximum | 65 | Reject |
| Non-numeric input | `abc` | Reject |

The purpose is to reduce the number of tests while still covering different classes of input.

#### Boundary Value Analysis (BVA)

**Boundary Value Analysis** concentrates on values at and around the edge of a valid range, because errors often occur at limits.

Example from the slides: If a password must contain 8 to 16 characters:

| Length | Position | Expected result |
|---:|---|---|
| 7 | Just below minimum | Fail |
| 8 | Minimum valid boundary | Pass |
| 16 | Maximum valid boundary | Pass |
| 17 | Just above maximum | Fail |

#### Decision table testing

A **decision table** lists combinations of conditions and the expected action for each combination. Use it when business rules depend on several conditions.

Example: A purchase discount might depend on membership status and order amount. A decision table helps ensure the team checks every relevant combination that the requirement defines.

The slides name this technique but do not provide a full decision table example.

#### State transition testing

**State transition testing** checks how a system moves from one state to another after an event or action.

Example: An order may move through states such as Placed, Confirmed, Preparing, Dispatched, and Delivered. Tests should check both permitted transitions and transitions that the system should reject.

The slides recommend this technique for workflows and order status, but do not provide a complete transition diagram.

#### Use-case or scenario testing

**Use-case testing** checks an end-to-end user journey. The tester follows a complete scenario rather than only one isolated field or button. The slides associate it with acceptance testing.

### Positive, negative, and edge cases

- **Positive test:** Uses valid inputs the system should accept. Example: a valid email and password produce a successful login.
- **Negative test:** Uses invalid inputs the system should reject gracefully. Example: a wrong password produces a clear message instead of a crash.
- **Edge case:** Tests an extreme or boundary value. Example: a password with exactly 16 characters when 16 is the maximum.

The slides give a rule of thumb: for each positive test, write at least two negative tests. This is guidance from the lecture, not a fixed rule for every test design.

## 4.7 Test execution process

The slides set out nine steps:

1. Confirm that entry criteria have been met.
2. Execute tests in priority order: Critical, High, Medium, then Low.
3. Record the actual result of every test case.
4. Compare actual results with expected results and mark Pass or Fail.
5. For a failed test, capture evidence such as screenshots, logs, or video.
6. Log the defect in a tracking tool such as JIRA or Azure DevOps.
7. Update the execution report daily.
8. Retest fixed defects and run regression tests for affected areas.
9. When exit criteria are met, prepare the Test Summary Report and obtain sign-off.

## 4.8 Types of test execution

| Test type | Meaning in the slides | When to use it |
|---|---|---|
| Smoke testing | A short check of critical paths on a new build | Before starting full testing, to confirm basic stability |
| Sanity testing | A focused check of a specific area after a fix | After a developer provides a fix |
| Full regression testing | Run the complete regression suite | Before a major release or after significant changes |
| Retesting | Repeat the failed test after the defect has been fixed | To verify the specific correction |
| Exploratory testing | Tester explores without following only a fixed script | New features or vague requirements |

**Smoke vs sanity vs retesting:** Smoke testing asks whether the build is stable enough for more testing. Sanity testing checks a particular affected area. Retesting repeats a previously failed test to confirm a specific defect fix.

## 4.9 Defect management: basic idea

**Defect management** is the organized process of identifying, logging, classifying, assigning, resolving, verifying, and closing defects. Each defect should be visible in a tracking system, assigned to an owner, fixed and verified, and formally closed with evidence.

The slides define a defect life cycle and include statuses such as New, Assigned, Open, Fixed, Ready for Retest, In Retest, Verified/Closed, Reopened, Deferred, Rejected, Cannot Reproduce, Duplicate, and On Hold. Module 6 explains these terms in greater depth.

## 4.10 Testing and reporting tools

The slides group tools by purpose.

| Tool | Purpose given in the slides |
|---|---|
| JIRA | Defect tracking and sprint management |
| TestRail | Test case management and execution tracking |
| Zephyr for JIRA | Test management inside JIRA |
| HP ALM / Quality Center | Enterprise test management and compliance reporting |
| Azure DevOps | Test/defect management integrated with repositories and pipelines |
| Selenium WebDriver | Browser UI automation |
| Appium | Mobile automation for iOS and Android |
| Postman / Newman | API testing |
| JMeter | Load and performance testing |
| SonarQube | Code analysis for bugs, vulnerabilities, code smells, and coverage |
| ESLint | JavaScript syntax and coding-practice checks |
| Pylint | Python quality checks, including unused variables and style-related issues |
| Checkstyle | Java coding-standard checks |
| Allure Reports | HTML reports with screenshots, steps, and trend information |
| Extent Reports | HTML reports and charts for test suites |

## 4.11 Test data management

**Test data** means the inputs used while executing test cases. Good test data helps a team test valid behaviour, invalid behaviour, edge cases, and realistic usage.

### Types of test data

- **Positive data:** Valid inputs that the system should accept.
- **Negative data:** Invalid inputs that the system should reject.
- **Boundary data:** Values at the edge of a permitted range.
- **Special characters:** Inputs such as apostrophes or markup-like strings that can reveal handling problems or security risks.
- **Empty or null data:** Missing values in fields that may require input.
- **Volume data:** Large datasets used for performance-related tests.
- **Production-like data:** Realistic data that has been anonymized or masked.

### Test data challenges and solutions

| Challenge | Solution shown in the slides |
|---|---|
| Data privacy | Mask sensitive names, card numbers, and identity details |
| Stale data | Refresh the data before each testing cycle |
| Tests depending on shared data | Use separate datasets and avoid shared mutable state |
| Different Dev/QA/UAT environments | Maintain separate datasets for each environment |
| Database state pollution | Use teardown scripts to reset the database to a known state |
| Need for realistic volume | Use data-generation tools such as Faker |

The slides also list manual data creation, Faker, anonymized production data, SQL seed scripts, and Excel/CSV files as data sources.

## 4.12 Selenium in CI/CD

**Continuous Integration (CI)** means each code commit triggers an automated build and tests. **Continuous Delivery (CD)** means the code can proceed through the delivery process after required checks pass. The slides place Selenium in the automated UI-regression layer.

A Selenium CI/CD workflow follows this sequence:

1. A developer pushes code to GitHub or another Git repository.
2. A CI server such as Jenkins or GitHub Actions detects the push.
3. The pipeline builds the application and runs unit tests.
4. If the build passes, the pipeline runs the Selenium smoke suite.
5. Selenium Grid can distribute tests across browsers such as Chrome, Firefox, and Edge.
6. Failed tests capture evidence such as screenshots, video, and stack traces.
7. The pipeline generates a report, such as an Allure HTML report.
8. The team receives a notification through Slack or email.
9. The team can block a merge when a critical test fails.
10. If all required checks pass, the code moves to the next environment.

### Execution layers shown in the slides

| Suite | Approximate size shown | Trigger shown | Purpose |
|---|---:|---|---|
| Smoke suite | 30–50 critical-path tests | Every commit | Quick build validation |
| Sanity suite | 150–200 feature tests | Each feature merge | Focused check of the changed area |
| Full regression | 1,500–3,000 tests | Nightly | Broad check for regressions |
| Performance suite | JMeter load tests | Weekly or before release | Check performance under workload |

These sizes and durations are examples from the lecture slides rather than required values for every project.

### Selenium Grid and parallel execution

The slides describe a **Hub** that receives test requests and routes them to available **Nodes**. Nodes run browser instances and execute tests. Parallel execution allows different tests to run simultaneously across different browser and operating-system combinations.

The slides mention Selenium Grid modes in version 4: Standalone, Hub-Node, and Distributed. They also name BrowserStack, LambdaTest, and Sauce Labs as cloud options.

### CI/CD best practices from the slides

- Use the Page Object Model to centralize page locators.
- Prefer explicit waits over fixed sleeps.
- Capture screenshots when tests fail.
- Run headless Chrome when a visible browser is unnecessary in CI.
- Tag tests by priority, such as smoke and regression.
- Use parallel execution for larger test suites.
- Keep test data in external files such as Excel or JSON rather than hardcoding every value.
- Clean up browser sessions after test execution.
- Investigate flaky tests instead of accepting inconsistent results.

### Module 4 revision questions

1. Differentiate test strategy and test plan.
2. List and explain the 13 test-plan components shown in the slides.
3. Explain entry, exit, suspension, and resumption criteria.
4. Define ambiguity review and explain its four types.
5. What is a test case? Explain the properties of a good test case.
6. Explain Equivalence Partitioning and Boundary Value Analysis with the age/password examples.
7. Explain decision table, state transition, and use-case testing.
8. Differentiate smoke testing, sanity testing, retesting, and regression testing.
9. Explain the steps of test execution.
10. What is test data management? Explain its challenges and solutions.
11. Explain how Selenium fits into a CI/CD pipeline.
12. Explain the role of a Hub and Nodes in Selenium Grid.

---

# Module 5: Test Automation and Selenium Optimization

## 5.1 What is test automation?

**Test automation** uses software tools to run pre-written test scripts, compare actual results with expected results, and create reports without requiring a person to perform every action during execution.

The key idea is simple: write a test once and run it repeatedly. Automation helps teams repeat the same tests quickly and consistently. It does not remove the need for manual testing; instead, it reduces repetitive work so testers can investigate new or unusual behaviours.

## 5.2 Manual vs automated testing

The slides compare testing methods across several dimensions:

| Dimension | Manual testing | Automated testing |
|---|---|---|
| Speed | A person performs actions one at a time | A tool can execute many steps rapidly |
| Consistency | Human fatigue or distraction can affect execution | The script repeats the same programmed steps |
| Initial cost | Lower for a small task | Higher because scripts and setup take time |
| Long-term effort | Repeated execution consumes tester time | Repeated runs can reduce effort after setup |
| Good use cases | Exploratory, usability, ad hoc work | Regression, data-driven, cross-browser work |
| Continuous execution | Depends on people being available | Can run during scheduled CI/CD jobs |
| Maintenance | No script maintenance | Scripts need updates when the application changes |

## 5.3 What should and should not be automated?

### Good candidates for automation

The slides recommend automating:

- Regression suites that must run after code changes.
- Smoke tests that quickly check a new build.
- Data-driven tests that repeat one workflow with many sets of input data.
- Cross-browser checks across Chrome, Firefox, Edge, and other supported browsers.
- Load/performance tests using appropriate tools.
- API tests that validate backend services.
- Repetitive form submissions such as login, checkout, and registration.

### Poor candidates for automation

The slides advise against automating:

- Exploratory testing that depends on human curiosity and intuition.
- Usability tests that require observing real users.
- One-time or rarely repeated tests when automation costs more than manual execution.
- Interfaces that change constantly, causing scripts to break frequently.
- Features with requirements that have not stabilized.

The decision rule is practical: automate a test when repeated execution, consistency, and saved time justify the cost of writing and maintaining the script.

## 5.4 Benefits of automation

The slides list these benefits:

1. **Speed:** Large suites can run much faster than manual execution.
2. **Early defect detection:** Tests can run after each code change.
3. **Broader coverage:** A team can test more datasets and browser/operating-system combinations.
4. **Repeatability:** The same steps run consistently each time.
5. **Continuous testing:** Scheduled runs can happen without a tester waiting at the computer.
6. **Regression safety:** Automated tests help detect when new code breaks existing behaviour.
7. **Reporting:** Tools can generate reports and metrics for the team.

### The test pyramid example

The slides use a test-pyramid example in which most tests sit at the unit level, fewer sit at the integration level, and the smallest proportion are end-to-end UI tests. The example shows 70% unit tests, 20% integration tests, and 10% end-to-end tests. Developers write unit tests; developers and QA share integration testing; QA engineers handle end-to-end tests such as those using Selenium.

**Main lesson:** A suite should not rely only on slow end-to-end UI tests. Lower-level tests form a larger, faster base, while end-to-end tests check complete user journeys.

The slides also give example claims about high deployment frequency and defect detection at Netflix. Treat the company-specific figures as examples used by the lecture, not as claims that every organization follows the exact same process.

## 5.5 Selenium suite overview

The slides describe Selenium as an open-source, vendor-neutral framework for browser automation, supporting Java, Python, C#, JavaScript, and Ruby.

### Selenium IDE

Selenium IDE is a record-and-playback browser tool. The slides describe it as point-and-click and not requiring code for basic recording.

### Selenium WebDriver

WebDriver controls browsers programmatically through code. The slides identify it as the industry-standard component for scripted browser automation.

### Selenium Grid

Grid distributes tests across multiple machines and browser instances so the team can run tests in parallel.

### Selenium RC

The slides identify Selenium RC as a legacy component that has been deprecated since 2016 and is no longer used in the described active Selenium suite.

## 5.6 Selenium WebDriver architecture

The slide deck explains WebDriver using four layers:

1. **Test script:** Code written in Python, Java, C#, or another supported language.
2. **Selenium WebDriver API:** The language interface through which the script sends browser commands.
3. **Browser driver:** A component such as ChromeDriver, GeckoDriver, or EdgeDriver that connects the automation request to the selected browser.
4. **Browser:** The actual browser instance that performs the action.

### How a click command travels

The slides explain the flow using `button.click()`:

1. The test script asks WebDriver to click a button.
2. WebDriver sends a command through its communication layer.
3. The browser driver receives and interprets the command.
4. The browser performs the click.
5. The command result returns to the test script.

The slides use HTTP/WebDriver communication and Chrome DevTools Protocol in the example. For an exam, focus on the four layers and the direction of the command flow.

## 5.7 Browser drivers

The slides list these examples:

| Browser | Driver named in the slides |
|---|---|
| Google Chrome | ChromeDriver |
| Mozilla Firefox | GeckoDriver |
| Microsoft Edge | EdgeDriver |
| Safari | SafariDriver |

The slides warn that ChromeDriver and Chrome versions must be compatible. A version mismatch can produce a “session not created” error. They mention WebDriverManager for Java and `webdriver-manager` for Python as ways to manage driver versions.

## 5.8 Selenium Grid

**Selenium Grid** runs browser tests in parallel across multiple machines or browser instances.

Its two core components are:

- **Hub:** Receives test requests and routes them to available nodes.
- **Node:** Runs browser instances and executes assigned tests.

The slides list three Grid 4 modes:

- **Standalone:** Hub and Node run on the same machine.
- **Hub-Node:** The Hub and one or more Nodes run separately.
- **Distributed:** Grid components run separately for larger deployments.

The lecture compares Grid 3 and Grid 4 by architecture, node registration, protocol, monitoring, Docker support, and configuration. Grid 4 adds more deployment modes, automatic node registration, a richer console, Docker support, and more flexible configuration in the presentation.

### Grid example from the slides

The Myntra example describes one Hub and four Nodes containing Chrome, Firefox, and Edge sessions, for a total of 16 parallel sessions. The deck gives a test suite of 2,400 tests that took eight hours serially and 35 minutes with Grid parallel execution. This is an illustrative example of how parallel execution can reduce total wall-clock time.

## 5.9 Locators

A **locator** tells Selenium how to find a particular web element so the script can interact with it.

The slides list eight built-in strategies:

1. `By.ID`
2. `By.NAME`
3. `By.CLASS_NAME`
4. `By.TAG_NAME`
5. `By.LINK_TEXT`
6. `By.PARTIAL_LINK_TEXT`
7. `By.XPATH`
8. `By.CSS_SELECTOR`

The deck's general rule is to prefer a stable, specific locator, with ID as the first choice where available. It gives this simplified priority: ID, then Name, then CSS Selector, then XPath. It also warns that class names may be repeated and auto-generated class names may change.

### ID locator

Use an element's HTML `id` attribute. The slides call it the best choice when a meaningful, stable ID exists.

```python
driver.find_element(By.ID, "username").send_keys("testuser@mail.com")
```

### Name locator

Use an element's HTML `name` attribute. This is common in form fields. Check uniqueness because multiple elements, such as radio buttons, may share a name.

```python
driver.find_element(By.NAME, "searchQuery").send_keys("Selenium WebDriver")
```

### CSS Selector

CSS selectors identify elements by ID, class, attributes, or relationships in the document tree.

| Pattern | Meaning | Example |
|---|---|---|
| `#elementId` | Element with this ID | `#loginBtn` |
| `.className` | Element with this class | `.error-message` |
| `tag[attr="value"]` | Element matching an attribute | `input[type='submit']` |
| `tag[attr*="text"]` | Attribute contains text | `a[href*='checkout']` |
| `parent > child` | Direct child | `form#loginForm > button` |
| `ancestor descendant` | Descendant anywhere below an ancestor | `div.card input` |

Examples:

```python
driver.find_element(By.CSS_SELECTOR, "#submit-btn")
driver.find_element(By.CSS_SELECTOR, ".error-text")
driver.find_element(By.CSS_SELECTOR, "input[type='email']")
```

### XPath

XPath navigates the document tree and can identify elements using attributes, text, siblings, parents, or position.

- **Absolute XPath** starts at the root, commonly with `/html/...`. The slides say to avoid it because a change anywhere along the path can break the locator.
- **Relative XPath** commonly starts with `//` and searches for a matching element without depending on every ancestor from the root. The slides prefer it.

Examples from the slides:

```python
# Match an input by ID
 driver.find_element(By.XPATH, '//input[@id="username"]')

# Match a button by visible text
 driver.find_element(By.XPATH, '//button[text()="Login"]')

# Match an element whose text contains a phrase
 driver.find_element(By.XPATH, '//button[contains(text(), "Add")]')
```

**Best-practice notes from the slides:** Avoid absolute XPath and auto-generated class names. Prefer meaningful IDs, stable attributes, or `data-testid` attributes when the application provides them.

## 5.10 WebDriver navigation and element actions

### Navigation commands

| Python command | Purpose |
|---|---|
| `driver.get(url)` | Open a URL |
| `driver.current_url` | Read the current URL |
| `driver.title` | Read the page title |
| `driver.back()` | Navigate backward |
| `driver.forward()` | Navigate forward |
| `driver.refresh()` | Reload the page |
| `driver.close()` | Close the current window |
| `driver.quit()` | Close all browser windows and end the driver session |
| `driver.maximize_window()` | Maximize the window |

### Web element commands

| Command/property | Purpose |
|---|---|
| `.click()` | Click a button, link, checkbox, or other clickable element |
| `.send_keys(text)` | Type text into an input field |
| `.clear()` | Clear existing text in a field |
| `.text` | Read visible text in Python |
| `.get_attribute("attr")` | Read an HTML attribute, such as `href` or `src` |
| `.is_displayed()` | Check whether an element is visible |
| `.is_enabled()` | Check whether an element is enabled |
| `.is_selected()` | Check whether a checkbox or similar control is selected |

## 5.11 Handling dropdowns

The slides use Selenium's `Select` class for HTML dropdowns.

```python
from selenium.webdriver.support.ui import Select

select = Select(driver.find_element(By.ID, "country"))
select.select_by_visible_text("India")
```

The selection methods listed in the slides are:

- `select_by_visible_text("India")`: Select using the displayed text.
- `select_by_value("IN")`: Select using the option's value attribute.
- `select_by_index(0)`: Select by index position.

Other listed methods include `options`, `first_selected_option`, and `deselect_all()` for multi-select dropdowns.

## 5.12 Selenium waits

Web pages often load elements asynchronously. If Selenium tries to interact with an element before it exists or becomes ready, the test may fail. Waits let the script wait for the condition it needs.

### Types of waits

- **Implicit wait:** Applies to element-finding calls globally. The slides advise using it with caution.
- **Explicit wait:** Waits for a specific element or condition. The slides recommend this approach.
- **Fluent wait:** Adds custom polling intervals and the ability to ignore selected exceptions. The slides describe it as an advanced option.

The slides strongly discourage fixed delays such as `time.sleep(5)` because they always wait for the chosen duration, even if the page is ready earlier. They can also fail when the page takes longer than expected.

### Important ExpectedConditions

| Condition | What it waits for |
|---|---|
| `visibility_of_element_located` | The element exists in the DOM and is visible |
| `element_to_be_clickable` | The element is visible and enabled |
| `presence_of_element_located` | The element exists in the DOM, even if invisible |
| `text_to_be_present_in_element` | An element contains specific text |
| `url_contains` | The current URL contains a given substring |
| `invisibility_of_element_located` | An element is hidden or removed, such as a loading spinner |
| `alert_is_present` | A JavaScript alert or confirmation dialog appears |

Example:

```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By

wait = WebDriverWait(driver, 10)
button = wait.until(EC.element_to_be_clickable((By.ID, "loginBtn")))
button.click()
```

## 5.13 Alerts, frames, and windows

### JavaScript alerts

The slides list these actions:

- `driver.switch_to.alert`: Switch to the alert.
- `alert.text`: Read the alert's text.
- `alert.accept()`: Accept the alert, similar to clicking OK.
- `alert.dismiss()`: Dismiss the alert, similar to clicking Cancel.
- `alert.send_keys("input")`: Enter text in a prompt alert.

### iFrames

An iFrame contains a separate embedded browsing context. Selenium must switch into it before interacting with elements inside it.

```python
driver.switch_to.frame("iframeId")
# Interact with elements in the frame.
driver.switch_to.default_content()
```

The slides also show switching by index, such as `driver.switch_to.frame(0)`.

### Multiple windows and tabs

- `driver.window_handles` lists open window handles.
- `driver.current_window_handle` identifies the current window.
- `driver.switch_to.window(handle)` switches to a specific window.

## 5.14 Example: simple Selenium login test

The following example follows the login workflow shown in the slides. The URL, IDs, credentials, and page title are example values and would need to match the application under test.

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC


driver = webdriver.Chrome()
try:
    driver.maximize_window()
    driver.get("https://myapp.com/login")
    wait = WebDriverWait(driver, 10)

    wait.until(
        EC.element_to_be_clickable((By.ID, "email"))
    ).send_keys("admin@test.com")

    driver.find_element(By.ID, "password").send_keys("Admin@123")
    driver.find_element(By.ID, "loginBtn").click()

    wait.until(EC.url_contains("dashboard"))
    assert "Dashboard" in driver.title
finally:
    driver.quit()
```

### Explain the script in an exam

1. Import WebDriver, locator support, and wait support.
2. Start Chrome and open the login page.
3. Wait until the email field becomes clickable.
4. Enter the email and password.
5. Click the login button.
6. Wait until the URL contains `dashboard`.
7. Assert that the page title includes `Dashboard`.
8. Close the browser session with `driver.quit()`.

An assertion compares the actual value with the expected condition. If the condition does not hold, the test reports a failure.

## 5.15 Data-driven testing (DDT)

**Data-driven testing** separates the test logic from the test data. One script runs repeatedly with different input values and expected results.

**Core rule from the slides:** `1 test script + N data rows = N test cases`.

Without data-driven testing, a team might create many nearly identical scripts for different login combinations. With DDT, the team keeps one script and adds rows to a data file. If the login workflow changes, the team can update one script instead of many copies.

### Common data sources

The slides list Excel, CSV, JSON, XML, databases, `pytest`'s `@parametrize`, and TestNG's `@DataProvider`.

### Excel example structure

| Username | Password | Expected result |
|---|---|---|
| `admin@test.com` | `Admin@123` | Dashboard |
| `user@test.com` | `User@456` | Dashboard |
| `wrong@test.com` | `WrongPass` | Invalid Login |
| `admin@test.com` | Empty | Invalid Login |

The slides show `openpyxl` loading an Excel file and looping through its rows. Each row supplies the username, password, and expected result for a test run.

### `pytest` parameterization example

```python
import pytest

@pytest.mark.parametrize("username, password, expected", [
    ("admin@test.com", "Admin@123", "Dashboard"),
    ("user@test.com", "User@456", "Dashboard"),
    ("wrong@test.com", "WrongPass", "Invalid Login"),
    ("admin@test.com", "", "Invalid Login"),
])
def test_login(username, password, expected):
    # Open the page, enter the values, submit, and check the result.
    # Each parameter row becomes a separate test case.
    pass
```

This shows the idea of parameterization, not a complete runnable test. A real test must create and clean up its browser, interact with the application, and assert the expected result.

### JSON example

The slides show test data stored as JSON objects with `username`, `password`, and `expected` fields. Python's `json` library reads the file, after which the script loops through the objects.

The deck recommends JSON when data needs to sit naturally alongside APIs or remain in version control, and when a CI server should not depend on Excel being installed.

## 5.16 Page Object Model (POM)

The **Page Object Model (POM)** is a design pattern that represents each web page as a separate class. The class stores locators and methods for the actions that a user can perform on that page.

The test script calls page methods rather than repeating locator details throughout the test suite.

### Why use POM?

Without POM, locators and repeated actions can appear in many test files. If the UI changes, the team may need to update many places. With POM, the page class centralizes the locators and common actions, making the tests easier to read and maintain.

The slides describe this difference as updating many test files without POM versus updating one place with POM.

### POM structure shown in the slides

A `LoginPage` class stores locators for the email field, password field, login button, and error message. It exposes a method such as `login(email, password)` that carries out the common login actions. A test calls that method and then checks the resulting page.

```python
class LoginPage:
    EMAIL_FIELD = (By.ID, "email")
    PASSWORD_FIELD = (By.ID, "password")
    LOGIN_BUTTON = (By.ID, "loginBtn")
    ERROR_MSG = (By.CSS_SELECTOR, ".error-alert")

    def __init__(self, driver):
        self.driver = driver

    def login(self, email, password):
        self.driver.find_element(*self.EMAIL_FIELD).send_keys(email)
        self.driver.find_element(*self.PASSWORD_FIELD).send_keys(password)
        self.driver.find_element(*self.LOGIN_BUTTON).click()
```

A test can then call `LoginPage(driver).login(...)` and verify the dashboard or an error message. The example focuses on structure; a complete project would also manage setup, waits, error handling, and teardown.

## 5.17 Automation anti-patterns

The slides list common mistakes and better alternatives:

| Anti-pattern | Problem | Better practice from the slides |
|---|---|---|
| Fixed `time.sleep()` delays | Wastes time and can still be too short | Use explicit waits and ExpectedConditions |
| Absolute XPath | Breaks when the page structure changes | Use stable relative XPath or CSS selectors |
| No screenshot on failure | Makes CI failures harder to investigate | Capture failure evidence |
| Serial execution of large suites | Takes too long | Use Selenium Grid or parallel test execution |
| Hardcoded test data in scripts | Makes adding cases and maintenance difficult | Use Excel, JSON, or another external source |
| No browser cleanup | Tests can interfere with one another | Always close the driver/session in teardown or `finally` |
| Obfuscated auto-generated class names | May change between builds | Prefer stable IDs, attributes, or `data-testid` values |

### Module 5 revision questions

1. Define test automation and explain its benefits.
2. Compare manual and automated testing.
3. What should and should not be automated? Explain why.
4. Explain the four layers of Selenium WebDriver architecture.
5. Differentiate Selenium IDE, WebDriver, and Grid.
6. Explain the roles of Hub and Node in Selenium Grid.
7. Define locators and explain ID, Name, CSS Selector, and XPath with examples.
8. Explain the difference between absolute and relative XPath.
9. Explain WebDriver navigation and element-interaction commands.
10. Differentiate implicit, explicit, and fluent waits.
11. Explain how Selenium handles alerts, frames, and multiple windows.
12. Explain data-driven testing and describe Excel, JSON, or parameterization approaches.
13. What is Page Object Model? Explain its advantages.
14. List common automation anti-patterns and their alternatives.

---

# Module 6: Software Quality, Defect Management, Reporting, and Metrics

## 6.1 What is software quality?

**Software quality** describes how well a software product meets stated and implied needs when users operate it under specified conditions.

The slides explain two dimensions:

- **Functional quality:** Does the software do what the user needs? This includes correctness, completeness, and accuracy of features.
- **Structural quality:** Is the software built well? The slides connect this dimension with maintainability, security, performance, and reliability.

The module names ISO/IEC 25010, also called the SQuaRE model, and lists eight quality characteristics.

## 6.2 The eight quality characteristics in ISO 25010, as listed in the slides

| Characteristic | Simple explanation | Example from the slides |
|---|---|---|
| Functional suitability | The system provides the required functions | An ATM dispenses cash correctly and updates the balance |
| Performance efficiency | Response time, throughput, and resource use are appropriate | Search results return in under half a second in the example |
| Compatibility | The system works with other systems and relevant environments | The application works in Chrome, Firefox, and Safari |
| Usability | Users can use the system easily and feel satisfied | A first-time user books an order without help |
| Reliability | The system continues to work correctly over time | WhatsApp availability is used as an illustration in the slides |
| Security | The system protects data against unauthorized access | Online banking uses encryption and two-factor authentication |
| Maintainability | Developers can modify, update, and fix the system without excessive difficulty | A developer adds a payment method in a short period |
| Portability | The system works across supported environments | An app runs across several Android versions |

For exams, learn the eight names and be able to explain each in plain language. The examples above follow the slide deck.

## 6.3 Quality Assurance (QA) vs Quality Control (QC)

**Quality Assurance (QA)** focuses on the process used to prevent defects. It is proactive and operates throughout the life cycle. Activities include audits, reviews, standards, and training.

**Quality Control (QC)** focuses on finding defects in the product. It is more reactive and includes testing, inspection, and defect reporting.

| Quality Assurance (QA) | Quality Control (QC) |
|---|---|
| Focuses on process | Focuses on product |
| Works to prevent defects | Works to find and remove defects |
| Proactive | More reactive |
| Applies throughout the life cycle | Often checks the developed product before release in the slides |
| Example: review requirements before coding | Example: run test cases against the application |
| The slides describe responsibility as shared across the team | The slides place primary responsibility with the QA/Test team |

**Memory tip:** QA improves the process to stop defects being created. QC checks the product to find defects that exist.

## 6.4 Error, fault, defect, and failure

The slides teach the chain **Error → Fault → Defect → Failure**. These terms describe different stages in a problem's path from a human mistake to incorrect live behaviour.

- **Error:** A human mistake made by a developer, analyst, or designer. Example: someone misreads “credit” as “debit” in a payment requirement.
- **Fault (bug):** An incorrect item in code or a document that results from the error. Example: the code subtracts an amount from the receiver's balance when it should add it.
- **Defect:** The incorrect behaviour becomes observable during testing. Example: a test shows that the receiver's balance decreases rather than increases.
- **Failure:** The system shows incorrect behaviour in the live production environment. Example: a customer sees the wrong account balance and contacts the bank.

The source sometimes uses “defect” more broadly in other slides. For the specific chain above, keep the four stages distinct as the module teaches them.

### Why early detection matters

A fault that survives code review and testing can reach users, where it may cost much more to diagnose and correct. The slides give the example of requirements fixes costing 1× and production fixes costing 100×.

## 6.5 Case study: Ariane 5 rocket

The slides use the 1996 Ariane 5 launch failure as an example of a defect escaping earlier checks.

- **Error:** An engineer assumed that a horizontal velocity value would always fit into a 16-bit variable, based on the earlier Ariane 4 context.
- **Fault:** The code did not handle overflow when converting a larger value to the smaller representation.
- **Testing gap:** The relevant flight profile had not been tested.
- **Failure:** The flight computer failed shortly after launch. The backup computer ran the same faulty code, and the rocket self-destructed.

**Lesson from the slides:** Review should catch mistaken assumptions, and testing should cover the scenarios in which those assumptions may not hold.

## 6.6 Where defects originate

The slides state that defects can start during any SDLC phase. They provide the following fix-cost multipliers:

| Phase | Example defect origin | Cost multiplier shown |
|---|---|---:|
| Requirements | Ambiguous, missing, or incorrect assumptions | 1× |
| System design | Wrong architecture or missing module interactions | 5× |
| Detailed design | Incorrect module specifications or missing error handling | 10× |
| Coding | Logic errors, off-by-one errors, null pointers, or wrong APIs | 15× |
| Unit testing | Environment issues or incorrect test data | 20× |
| Integration testing | Interface mismatch between modules | 30× |
| System testing | Performance issues or environment differences | 40× |
| Production | Defects that escaped earlier checks | 100× |

These multipliers come from the slides and serve to show the rising cost of late discovery.

### Root causes and prevention

| Root cause | Example in the slides | Prevention approach in the slides |
|---|---|---|
| Requirement problems | Ambiguous specifications and missing edge cases | Structured requirement reviews |
| Design flaws | Poor module design or missing error handling | Architecture reviews |
| Coding mistakes | Logic errors, hardcoded values, wrong algorithms | Code reviews and pair programming |
| Environment issues | Works on a development machine but fails in production | Containerization, such as Docker |
| Data problems | Unexpected formats, null values, special characters | Robust test data with edge cases |
| Third-party integration | API changes or incompatible versions | Contract testing and API mocking |
| Communication gaps | Developers and testers interpret requirements differently | Definition of Done and shared criteria |
| Time pressure | Teams take shortcuts or skip tests | Risk-based testing and management support |

## 6.7 Case study: IRCTC overload

The slides describe a case in which the Tatkal booking website crashed because the requirements did not state a clear load requirement. The design expected around 5,000 concurrent users, while the example describes 10–15 lakh users arriving at roughly the same time.

The slides list these improvements:

- Add a specific performance requirement for concurrent users.
- Make JMeter load testing mandatory before peak seasons.
- Add CDN, caching, and horizontal scaling to the architecture.
- Introduce a queue-based booking system.

**Lesson:** A vague requirement such as “the site should handle ticket bookings” is not enough. The requirement should describe the expected workload and the system's behaviour under it.

## 6.8 Defect taxonomy

A **defect taxonomy** is a systematic way to classify defects. Classification makes it easier to communicate, prioritize fixes, identify recurring problems, and produce useful quality reports.

The slides use three main dimensions:

1. Severity.
2. Priority.
3. Defect type.

### Classification by severity

**Severity** measures the technical impact of a defect on the system. The slides say the tester sets severity.

| Severity | Meaning in the slides | Example | Response described in the slides |
|---|---|---|---|
| Critical / Blocker | System is unusable and there is no workaround | Payment gateway fails and no orders can be placed | Fix within hours |
| High / Major | A core feature is broken, but a workaround exists | Coupon code never applies the discount | Fix within 24 hours |
| Medium / Moderate | A feature partially works and a reasonable workaround exists | Search results work but sort incorrectly | Fix in the current sprint |
| Low / Minor | Cosmetic issue with no functional impact | Hover colour differs from the expected colour | Fix in a later sprint |

### Classification by priority

**Priority** measures the business urgency of fixing a defect. The slides assign this decision to the Project Manager or Product Owner.

Severity and priority are related, but they are **not the same thing** and the slides emphasize that they can vary independently.

| Combination | Example from the slides | Meaning |
|---|---|---|
| High severity + high priority | Login fails for every user | Serious technical impact and urgent business need |
| High severity + low priority | Admin XML export crashes, but very few people use it | Serious technical impact, lower immediate business urgency |
| Low severity + high priority | CEO photo caption contains a spelling error on the homepage | Small technical issue, but important to the business or brand |
| Low severity + low priority | Slightly incorrect FAQ footer colour | Minor impact and low urgency |

**Exam tip:** State who assigns each one: tester assigns severity; Project Manager/Product Owner assigns priority according to the slides.

### Classification by defect type

The slides identify these categories:

- **Functional:** A feature does not behave as specified, such as login rejecting valid credentials.
- **Performance:** The system is slow or uses too many resources, such as a product page that takes 12 seconds to load.
- **Security:** A vulnerability permits unauthorized access, such as one user viewing another user's order history.
- **UI/Cosmetic:** The interface has visual problems, such as text overflowing a button on mobile.
- **Compatibility:** A feature works in one browser but not another.
- **Data:** The system stores, retrieves, or displays incorrect values.
- **Usability:** A feature works but confuses the user.
- **Integration:** Two modules do not work together correctly.
- **Regression:** Previously working functionality breaks after a code change.
- **Documentation:** Help text or error messages contain incorrect information.

## 6.9 Defect life cycle

The **defect life cycle** is the sequence of states a defect passes through from discovery to closure. The slides emphasize that each status should have an owner, state changes should have comments and evidence, and every defect should receive appropriate action within the agreed process.

### Normal flow

**New → Assigned → Open → Fixed → Ready for Retest → In Retest → Verified/Closed**

| Status | Meaning | Typical owner in the slides |
|---|---|---|
| New | Tester records the defect | Tester |
| Assigned | Test lead assigns the defect to a developer | Test Lead |
| Open | Developer investigates and works on the fix | Developer |
| Fixed | Developer applies the fix and deploys it to QA | Developer |
| Ready for Retest | The fix is waiting for tester verification | Developer/DevOps |
| In Retest | Tester checks the fix | Tester |
| Verified/Closed | Tester confirms the defect is fixed and closes it | Tester |
| Reopened | The fix was incorrect, so the issue returns to active work | Tester |
| Deferred | Business postpones the fix to a later release | Project Manager |
| Rejected | Team decides the behaviour is not a defect | Developer and Lead in the slides |
| Cannot Reproduce | Tester cannot reproduce the reported issue | Tester |
| Duplicate | Another defect already records the same issue | Test Lead |
| On Hold | Progress waits for an external dependency | Project Manager in the slides |

### Exception paths

- **Fix is incorrect:** In Retest → Reopened → Open → Fixed → Retest again.
- **Not a defect:** Assigned → Rejected.
- **Fix postponed:** Open → Deferred.
- **Already reported:** New → Duplicate, linked to the existing report.
- **Cannot reproduce:** New → Cannot Reproduce.
- **External dependency blocks progress:** Open → On Hold → Open when the dependency is resolved.

### Example: order-tracking bug

The slides show an example in which a tester reports an order stuck at “Preparing.” The test lead assigns the issue, a developer finds that a WebSocket update drops on a particular Android version, the developer deploys a fix to QA, the tester verifies it, attaches evidence, and closes the defect.

## 6.10 Defect management process and triage

The slides present a seven-step defect management process:

1. **Discovery:** A tester finds the problem during execution or review.
2. **Logging:** The tester records the issue in a tracking tool.
3. **Classification:** The team classifies its severity, priority, type, and module.
4. **Assignment:** The test lead assigns it to the appropriate developer.
5. **Fixing:** The developer investigates, corrects the issue, and deploys the fix to QA.
6. **Verification:** The tester retests the fix and runs regression checks on affected areas.
7. **Closure:** The team closes the defect when the fix works, or reopens it if the problem remains.

### Defect triage meeting

A **defect triage meeting** is a regular meeting in which relevant team members review newly reported defects and decide what to do next.

The slides list these questions:

- Is this a real defect or intended behaviour?
- What severity and priority should it receive?
- Who should fix it?
- Does it block the sprint or release?
- Should the team postpone it to a later release?

The attendees named in the slides are the Test Lead, Development Lead, Project Manager, and Business Analyst. The slides suggest daily meetings during active testing sprints and twice-daily meetings near a release deadline.

## 6.11 Defect tracking tools

The slides list these defect-management tools:

| Tool | Role described in the slides |
|---|---|
| JIRA | Defect tracking, workflow automation, dashboards, and Agile boards |
| Bugzilla | Open-source issue tracking with notifications |
| Azure DevOps | Integration with repositories and CI/CD pipelines |
| MantisBT | Issue tracking and time tracking |
| GitHub Issues | Links issues with code commits and pull requests |
| HP ALM / Quality Center | Enterprise traceability, compliance, and reporting |

## 6.12 Preparing a defect report

A **defect report** describes a problem clearly enough for a developer to reproduce it, understand it, and fix it, even without being present when the tester found it.

The slides emphasize this principle: **the steps to reproduce are the most important field**. Without clear steps, developers may not be able to recreate the problem and may waste time asking follow-up questions.

### Properties of a good defect report

- **Clear:** Every field uses unambiguous wording.
- **Complete:** The report includes all required details.
- **Concise:** It contains facts without unnecessary text.
- **Reproducible:** Another person can follow the steps and see the same behaviour.
- **Evidence-based:** It includes useful screenshots, videos, logs, or other evidence.

### Mandatory information and template fields

| Field | What it should contain |
|---|---|
| Defect ID | Unique ID, often generated by the tracking tool |
| Title/Summary | One concise line explaining where, what, and impact |
| Module/Feature | The affected part of the application |
| Linked requirement | Requirement or user story that the behaviour violates |
| Severity | Technical impact |
| Priority | Business urgency |
| Defect type | Functional, performance, UI, security, compatibility, or other category |
| Environment | Operating system, browser, device, application version, and build |
| Reported by/date | Tester and report date |
| Steps to reproduce | Numbered, atomic actions beginning from a known state |
| Expected result | What should happen according to the requirement |
| Actual result | What happened, described factually |
| Reproducibility | How consistently the tester can reproduce the issue |
| Workaround | Temporary alternative, if one exists |
| Attachments | Screenshots, video, logs, and other evidence |

### Good vs bad defect titles

The slides recommend this title pattern:

**[Component] [Action] [fails/crashes] when [condition] on [platform]**

Examples:

- Weak: “Button not working.”
- Strong: “Add to Cart button does not respond on iPhone 14 running iOS 17.”
- Weak: “Login issue.”
- Strong: “Login fails silently with valid credentials when VPN is active.”
- Weak: “Error on payment.”
- Strong: “UPI payment fails with `TXN_TIMEOUT` for amounts above ₹10,000.”

A good title helps the developer understand the issue before opening the full report.

### Advantages of good defect reports

The slides list faster fixes, fewer clarification conversations, more accurate project tracking, better root-cause analysis, better defect prevention, stronger legal/compliance records, a searchable knowledge base, stakeholder confidence, and the ability to turn closed defects into regression tests.

## 6.13 Defect prevention

**Defect prevention** uses proactive steps to reduce the chance of introducing defects. The slides use a cost model of Prevention ($1) < Internal Failure ($10) < External Failure ($100) to illustrate why it is usually cheaper to prevent issues early than to correct them after release.

### Techniques listed in the slides

| Technique | Phase | How it helps |
|---|---|---|
| Requirements reviews | Requirements | Catch unclear or incomplete requirements early |
| Ambiguity-review checklists | Requirements | Find vague statements and missing cases systematically |
| Design reviews | Design | Identify architecture and interaction problems before coding |
| Code reviews | Development | Find logic errors, security weaknesses, and bad practices |
| Pair programming | Development | One developer writes code while another reviews continuously |
| Static code analysis | Development | Tools inspect source code without executing it |
| Test-Driven Development (TDD) | Development | Tests written before code help define expected behaviour |
| Coding standards | Development | Consistent conventions reduce avoidable errors |
| Defect Causal Analysis (DCA) | After defects occur | Identify root causes and prevent them from returning |
| Definition of Done (DoD) | Sprint | Clear completion criteria stop unfinished work from being labelled done |
| Automated regression tests | CI/CD | Catch previously fixed defects when changes reintroduce them |

## 6.14 Five Whys analysis

**Five Whys** is a root-cause analysis technique. The team asks “Why?” repeatedly until it reaches the underlying reason instead of stopping at the visible symptom.

The slides use a delivery-status example:

1. **Why did the order show “Delivered”?** The delivery agent marked it as delivered in the app.
2. **Why could the agent mark it delivered without completing delivery?** GPS verification was bypassed during poor connectivity.
3. **Why did poor connectivity bypass GPS verification?** A five-second timeout silently passed when verification failed.
4. **Why did the timeout silently pass?** A developer assumed connectivity problems would be temporary.
5. **Why was failure behaviour not defined?** The requirements did not explain what should happen when GPS verification failed.

**Root cause in the slides:** A missing requirement for GPS-verification failure handling.

**Prevention action:** Add a requirement-review checklist item that asks what the system should do when GPS is unavailable.

## 6.15 Static code analysis: SonarQube

The slides define **SonarQube** as a tool that analyzes source code for possible bugs, security vulnerabilities, and code-quality problems without executing the code.

The slide lists these categories:

- **Bugs:** Code likely to produce incorrect behaviour, such as a null-pointer dereference or unclosed resource.
- **Vulnerabilities:** Security weaknesses such as SQL injection risk, hardcoded passwords, or XSS.
- **Code smells:** Maintainability problems, such as overly long methods or duplicated code.
- **Coverage:** How much code unit tests cover.
- **Duplications:** Copy-pasted code that should be reviewed or refactored.
- **Technical debt:** An estimate of the effort needed to fix accumulated code-quality problems.

The slides give an example of a quality gate that blocks a merge when code coverage falls below a threshold. Treat the particular threshold as the lecture example, not a universal requirement.

## 6.16 Test metrics and measurements

**Test metrics** are numerical measures used to evaluate testing progress, product quality, process efficiency, and release readiness. They give the team evidence rather than relying only on opinions.

The slides emphasize that metrics become more useful when the team follows trends over time. A single data point rarely explains the full quality picture.

### Important formulas

| Metric | Formula in the slides | Target or interpretation shown |
|---|---|---|
| Test coverage | (Tests executed ÷ Total planned tests) × 100 | At least 95% |
| Requirement coverage | (Requirements with test cases ÷ Total requirements) × 100 | 100% |
| Test pass rate | (Tests passed ÷ Tests executed) × 100 | At least 95% |
| Test fail rate | (Tests failed ÷ Tests executed) × 100 | Less than 5% |
| Defect density | Defects found ÷ size in KLOC | Decreasing trend |
| Defect Removal Efficiency (DRE) | (Pre-release defects ÷ Total defects) × 100 | At least 95% |
| Defect leakage | (Post-release defects ÷ Total defects) × 100 | Less than 5% |
| Mean Time to Detect (MTTD) | Average time from defect introduction to detection | Decreasing trend |
| Mean Time to Resolve (MTTR) | Average time from detection to closure | Decreasing trend |
| Defect rejection rate | (Rejected defects ÷ Total logged defects) × 100 | Less than 10% |
| Automation coverage | (Automated tests ÷ Total regression tests) × 100 | At least 80% |

**KLOC** means thousand lines of code. The table reproduces the definitions and targets shown in the lecture slides.

### Defect Removal Efficiency (DRE)

DRE measures the percentage of all discovered defects that the team finds before release.

**Formula:**

`DRE = (Pre-release defects ÷ Total defects) × 100`

The slides divide DRE into these broad ranges:

- Below 85%: poor quality process, with many bugs reaching users.
- 85%–94%: industry average in the lecture table.
- 95%–99%: excellent quality process.
- 100%: theoretical perfection, which the slides say is not realistic.

The slide example has 950 defects found before release and 50 found after release, for a total of 1,000. It calculates DRE as `(950 ÷ 1,000) × 100 = 95%`, which the slides classify as excellent. The team should still analyze the 50 post-release defects to find patterns and determine whether its earlier testing could have caught them.

### Defect leakage

Defect leakage measures the proportion of defects found after release:

`Defect leakage = (Post-release defects ÷ Total defects) × 100`

The slides set a target below 5%. A lower leakage rate indicates that a smaller proportion of the defects reach users, although the team should also consider defect severity and impact.

## 6.17 Test Summary Report

A **Test Summary Report** describes the testing completed and helps stakeholders decide whether the product is ready for release.

The slides list these sections:

- Project name, release version, and testing cycle.
- Planned, executed, passed, failed, and blocked test counts.
- Pass rate.
- Defect counts by severity.
- Major open defects.
- Requirement coverage.
- DRE.
- Quality risks.
- Go/No-Go recommendation.
- Status of exit criteria.

### Important source inconsistency

The slides show an example with 492 tests executed and 467 passed, then report a pass rate of 94.9%. Elsewhere on the same example, the exit-criteria line labels “pass rate ≥ 95%” as met. Those two statements do not agree: a reported 94.9% is below a 95% threshold. In an exam, explain that a report must compare the actual metric with the threshold accurately and must not mark an unmet criterion as met.

## 6.18 Automation tools and defect reporting

The slides explain that automation can improve how quickly teams detect, document, track, and prevent defects.

| Tool | Contribution described in the slides |
|---|---|
| Selenium WebDriver | Detects UI defects and compares actual and expected behaviour |
| Allure Reports | Adds step-by-step logs, screenshots, videos, environment details, and trends |
| JIRA + Zephyr | Can link failures to tickets or create defect records from test results |
| SonarQube | Finds potential code defects and vulnerabilities before runtime testing |
| Postman / Newman | Tests APIs and records requests and responses |
| JMeter | Detects performance issues using workload tests |
| Applitools / Percy | Compare screenshots to find visual changes |
| Slack / Teams webhooks | Notify the team when a test fails |

### Allure report capabilities listed in the slides

- Failure screenshots.
- Step-by-step logs.
- Test-history trends.
- Categories that separate product bugs, automation bugs, and environment issues.
- Links to existing defect tickets.
- Environment details such as browser, operating system, and application version.
- Timeline views that help identify slow tests and parallel-execution bottlenecks.
- Identification of flaky tests with inconsistent pass/fail results.

## 6.19 Automated defect workflow example

The slides provide a workflow in which a developer pushes a change, a CI tool runs code analysis and unit tests, Selenium detects a failure, evidence is captured, Slack notifies the team, a JIRA defect is created, the developer inspects the report, fixes the root cause, and reruns the tests. The pipeline approves the merge after the tests pass.

**Main lesson:** Automation is most useful when it connects execution, evidence, reporting, ownership, correction, and regression testing into one clear process.

### Module 6 revision questions

1. Define software quality. Explain the eight ISO 25010 characteristics listed in the slides.
2. Differentiate QA and QC.
3. Explain the Error → Fault → Defect → Failure chain with a banking example.
4. Explain the Ariane 5 case study and its lesson for testing.
5. Explain where defects originate and how their correction cost changes across the SDLC.
6. Define defect taxonomy and explain severity, priority, and defect type.
7. Differentiate severity from priority using all four combinations.
8. Explain the normal defect life cycle and its exception paths.
9. What is defect triage? List its decisions and attendees.
10. Explain the fields and properties of a good defect report.
11. Explain defect prevention techniques and the Five Whys method.
12. What does SonarQube detect?
13. Define test metrics and write the formulas for pass rate, DRE, defect leakage, and automation coverage.
14. What does a Test Summary Report contain? Why must the report compare results with exit criteria accurately?

---

# Cross-Module Comparison and Quick Revision

## A. Testing concepts that are easy to confuse

| Concepts | Difference to remember |
|---|---|
| Verification vs validation | Verification checks work products against specifications; validation checks whether the product meets user needs |
| Static vs dynamic testing | Static testing examines without running code; dynamic testing executes code |
| Black-box vs white-box testing | Black-box focuses on observable behaviour and requirements; white-box examines internal structure |
| Manual vs automation testing | Manual testing uses a person to execute actions; automation uses scripts and tools |
| Functional vs non-functional testing | Functional checks what the system does; non-functional checks how well it operates |
| Unit vs integration testing | Unit checks one component; integration checks interactions between components |
| System vs acceptance testing | System testing checks the integrated system; acceptance testing checks whether it meets users' or business needs |
| Smoke vs sanity testing | Smoke checks basic stability of a new build; sanity checks a focused area after a change |
| Retesting vs regression testing | Retesting confirms a specific fix; regression testing checks that existing features still work after changes |
| Test strategy vs test plan | Strategy defines the broad testing approach; plan defines the details for a project/release |
| Test case vs test data | A test case contains steps and expected results; test data supplies the values used in those steps |
| Severity vs priority | Severity measures technical impact; priority measures business urgency |
| QA vs QC | QA improves the process to prevent defects; QC tests the product to find defects |
| Error vs fault vs defect vs failure | Human mistake → incorrect artifact/code → observable incorrect behaviour during testing → live production failure |
| Absolute vs relative XPath | Absolute XPath follows a path from the root; relative XPath searches by a matching expression and is preferred in the slides |
| Implicit vs explicit wait | Implicit wait applies globally to element searches; explicit wait waits for a specific condition |
| Selenium vs JMeter | The slides mainly use Selenium for browser/UI automation and JMeter for load/performance testing |
| Data-driven testing vs POM | DDT separates test data from test logic; POM separates page locators/actions from test logic |

## B. Formulas to remember

| Metric | Formula |
|---|---|
| Test coverage | `(Tests executed ÷ Total planned tests) × 100` |
| Requirement coverage | `(Requirements with test cases ÷ Total requirements) × 100` |
| Pass rate | `(Tests passed ÷ Tests executed) × 100` |
| Fail rate | `(Tests failed ÷ Tests executed) × 100` |
| Defect density | `Defects found ÷ KLOC` |
| DRE | `(Pre-release defects ÷ Total defects) × 100` |
| Defect leakage | `(Post-release defects ÷ Total defects) × 100` |
| Defect rejection rate | `(Rejected defects ÷ Total logged defects) × 100` |
| Automation coverage | `(Automated tests ÷ Total regression tests) × 100` |

Remember: MTTD is the average time from defect introduction to detection. MTTR is the average time from detection to closure. The slides state that both should generally trend downward.

## C. Main process sequences

**STLC:** Requirements → Planning → Test Case Design → Environment Setup → Execution → Closure.

**Test execution:** Check entry criteria → Run tests by priority → Record actual results → Compare with expected results → Capture evidence on failure → Log defect → Update reports → Retest and run regression → Meet exit criteria and sign off.

**Defect life cycle:** New → Assigned → Open → Fixed → Ready for Retest → In Retest → Verified/Closed.

**Selenium architecture:** Test Script → WebDriver API → Browser Driver → Browser.

**Selenium CI/CD:** Push code → CI build and unit tests → Smoke suite → Grid/browser execution → Capture failure evidence → Generate report → Notify team → Block or approve merge.

**Defect prevention:** Review requirements → Review design → Review code → Use static analysis and coding standards → Test systematically → Analyze root causes → Add regression tests.

## D. Short-answer practice

Use these prompts to check whether you can explain the central terms without reading the guide.

1. What is software testing?
2. What are verification and validation?
3. What does STLC stand for?
4. What is the main limitation of the Waterfall model in the slides?
5. What does RAD stand for?
6. What is static testing?
7. What is black-box testing?
8. What is field-level validation?
9. What is regression testing?
10. What does UAT check?
11. What is a test strategy?
12. What are entry and exit criteria?
13. What is Equivalence Partitioning?
14. What is Boundary Value Analysis?
15. What is smoke testing?
16. What is a locator in Selenium?
17. What are the four WebDriver architecture layers?
18. What is Selenium Grid?
19. What does data-driven testing separate?
20. What is Page Object Model?
21. What are severity and priority?
22. What is the defect life cycle?
23. What is a good defect report's most important field?
24. What is defect prevention?
25. What does DRE measure?

## E. Long-answer practice

Prepare structured answers for these likely exam-style prompts:

1. Explain the purpose of software testing and distinguish verification from validation.
2. Explain the STLC phases and describe the output or purpose of each phase.
3. Compare Waterfall, V-Model, Incremental, Iterative, RAD, Evolutionary, and Prototype models based on the material in Module 1.
4. Explain static, dynamic, black-box, and white-box testing.
5. Describe UI testing for a registration form, including field validation, dependent fields, error messages, and overall form behaviour.
6. Compare manual and automated testing, including benefits, limitations, and suitable use cases.
7. Explain unit, integration, system, and acceptance testing, in sequence, with examples.
8. Explain test strategy, test plan, entry/exit criteria, ambiguity review, and test case design techniques.
9. Explain Equivalence Partitioning and Boundary Value Analysis using the examples in the slides.
10. Describe the test execution process and distinguish smoke, sanity, retesting, regression, and exploratory testing.
11. Explain Selenium WebDriver architecture, locators, browser drivers, and Grid.
12. Explain explicit waits, dropdown handling, alerts, iFrames, and windows in Selenium.
13. Explain data-driven testing and Page Object Model, including how each improves maintainability.
14. Explain the eight software quality characteristics listed in the ISO 25010 slide.
15. Explain the defect life cycle, defect triage, and preparation of a good defect report.
16. Explain defect severity versus priority with four examples.
17. Explain defect prevention, Five Whys analysis, and static code analysis.
18. Define and explain test coverage, pass rate, DRE, defect leakage, MTTD, MTTR, and automation coverage.
19. Explain how automation tools improve the defect management workflow.

## F. Source notes and coverage gaps

This guide follows the content in the supplied module PDFs. The source slides have a few gaps or inconsistencies that are worth recognizing:

1. **Agile and Spiral:** Module 1 lists these process models but the provided slide text does not explain them in detail. The guide does not add a full description beyond the list.
2. **Some Module 3 outline topics:** Internationalization testing, role-based access testing, and mobility testing appear in the outline but the slides do not provide detailed procedures. Security, usability, and compatibility receive only limited examples across the supplied modules.
3. **Selenium and performance testing:** Module 1 broadly mentions Selenium for performance testing. Modules 4 and 5 place browser/UI automation with Selenium and assign load/performance testing to JMeter. This guide makes that distinction explicit rather than concealing the inconsistency.
4. **Test Summary Report example:** The slide reports 94.9% pass rate but also labels a ≥95% pass-rate exit criterion as met. These claims conflict. A correct report must not mark a threshold as met when the actual metric falls below it.
5. **Numbers in examples:** Values such as 95% coverage, 80% automation coverage, defect-cost multipliers, and company-specific performance figures are presented as lecture examples or targets. A project should use criteria agreed for its own context.
6. **Source wording:** A few slides use overlapping terms such as error, fault, bug, and defect. For questions specifically about the error-to-failure chain, use the distinct stages explained in Module 6.

## Final revision strategy

Start with definitions and comparisons, because they appear throughout the six modules. Then learn the sequences: STLC, test execution, defect life cycle, Selenium architecture, and CI/CD workflow. Practise test-case design with the age and password examples, and practise defect metrics using the formulas. Finally, rehearse long answers aloud using definition → purpose → steps/types → example → advantages/limitations. If you can explain each comparison table without memorizing its exact wording, you have a strong foundation for the final examination.
