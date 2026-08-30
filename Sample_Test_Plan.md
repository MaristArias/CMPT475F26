# Sample Software Test Plan

## AccessPath: Accessible Campus Navigation

> **Purpose of this document:** This is a fictional example for CMPT 475. It demonstrates how a Capping team can plan, execute, and report software verification and product validation. Students should adapt the structure, depth, tools, and evidence to the risks of their own projects.

| Document field | Value |
|---|---|
| Project | AccessPath |
| Document type | Software Test Plan |
| Version | 1.0 |
| Status | Sample baseline |
| Test period | September 14–December 2, 2026 |
| Release under test | AccessPath MVP |
| Team | Sample Student Team |
| Last updated | August 30, 2026 |

## 1. Purpose

This plan defines how the AccessPath team will gather evidence that the system:

- Implements its approved functional requirements
- Satisfies important accessibility, security, privacy, performance, reliability, and maintainability requirements
- Supports representative users in planning suitable routes
- Handles invalid input, unavailable dependencies, insufficient data, and other failure conditions safely
- Is ready for the final release and demonstration

This document explains the testing strategy, responsibilities, environments, data, schedule, entry and exit criteria, defect process, test cases, and required evidence.

## 2. Related Documents

- [Sample Requirements Document](./Sample_Requirements.md)
- [Sample Project Plan](./Sample_Project_Plan.md)
- [Sample Use Case and Class Diagrams](./Sample_Use_Case_Class_diagram.md)

If these documents conflict, the team must resolve the conflict and update the affected baseline rather than silently choosing one interpretation.

## 3. System Under Test

AccessPath is a browser-based application that plans accessible walking routes across a university campus. The minimum viable product contains:

- A public route-planning web interface
- A route calculation service
- Campus graph and accessibility data
- Route details, warnings, explanations, and data-freshness information
- Public feedback submission
- Authenticated closure management
- Feedback review and administrative audit records
- Application programming interfaces
- Data import and validation tools
- Deployment, monitoring, backup, and recovery capabilities

## 4. Quality Objectives

| ID | Quality objective | Target evidence |
|---|---|---|
| QO.01 | Hard constraints are always respected | Every test in the approved route-validation set passes |
| QO.02 | Core workflows behave correctly | Mandatory unit, integration, API, and end-to-end tests pass |
| QO.03 | Representative users can plan routes | At least 85% task completion without assistance |
| QO.04 | Evaluated field routes are suitable | At least 90% completed without a known incompatible barrier |
| QO.05 | Core workflows are accessible | No unresolved critical WCAG 2.2 Level AA finding in tested scope |
| QO.06 | Privileged operations are protected | Authorization matrix passes; no unresolved critical security finding |
| QO.07 | The system meets performance targets | Required percentile targets pass under the documented workload |
| QO.08 | Failures are observable and recoverable | Monitoring, graceful-failure, backup, and restoration tests pass |
| QO.09 | Evidence is reproducible | Test code, data versions, commands, environment, and results are documented |

## 5. Test Principles

The team will follow these principles:

- Test important risks early rather than waiting for feature completion.
- Automate stable, repeatable checks that provide fast feedback.
- Use manual and human evaluation where automation cannot establish usability, accessibility, or real-world value.
- Test negative, boundary, permission, and failure cases—not only the expected path.
- Separate test data from production or personally identifiable data.
- Treat a test as evidence only when its environment, inputs, expected result, and actual result are recorded.
- Keep failed tests visible; do not disable or weaken a test merely to make the pipeline pass.
- Investigate test flakiness as a defect in the test or system.
- Prioritize testing according to impact and likelihood.

## 6. Scope

### 6.1 In scope

- Route request validation
- Hard constraints and route preferences
- Route selection and explanation
- No-route and insufficient-data behavior
- Active, scheduled, expired, and canceled closures
- Public feedback submission and review
- Authentication and role-based authorization
- Audit-event creation
- Campus data validation and import
- API contracts and error responses
- Public and administrative user interfaces
- Accessibility of core workflows
- Security and privacy controls
- Performance under the agreed evaluation workload
- Monitoring, dependency failure, backup, restoration, and deployment
- Compatibility with agreed desktop and mobile browsers
- Usability and field-route evaluation with representative participants

### 6.2 Out of scope

- Certification of compliance with building codes
- Guaranteeing that every real-world campus condition is current
- Native mobile application testing
- Indoor GPS or real-time positioning
- Emergency evacuation testing
- Production penetration testing against university infrastructure without written authorization
- Testing third-party identity or map providers beyond the behavior observable through AccessPath
- Browsers or assistive technologies outside the approved compatibility matrix
- Load levels beyond the project requirement of 100 concurrent route-planning users

Out-of-scope items may still create project risks and should be documented as limitations.

## 7. Test Strategy

### 7.1 Test levels

| Level | Purpose | Typical target | Execution |
|---|---|---|---|
| Static verification | Find issues without executing the system | Requirements, designs, source, configuration, dependencies | Every change or review gate |
| Unit testing | Verify isolated rules and calculations | Route constraints, closure timing, validation, authorization helpers | Every pull request |
| Component testing | Verify a service or module with controlled dependencies | Route engine, feedback service, data importer | Every pull request or nightly |
| Integration testing | Verify interactions among real components | API, database, identity adapter, route engine, audit logging | Every pull request and staging deployment |
| Contract testing | Verify stable interfaces between independently changing components | Frontend/backend API and external adapters | Every pull request |
| End-to-end testing | Verify complete workflows through the user interface | Public route planning and administration | Staging deployment and release candidate |
| System testing | Evaluate the deployed system as a whole | Security, performance, failure handling, recovery | Scheduled staging runs |
| Acceptance and validation | Determine whether the product is useful to intended users | Usability sessions and field-route trials | Evaluation phase |

### 7.2 Test types

The project will use:

- Functional and regression testing
- Boundary and equivalence-partition testing
- Property-based route-engine testing
- Data-quality and migration testing
- Accessibility testing
- Authentication and authorization testing
- Security and abuse-case testing
- Privacy verification
- Performance and load testing
- Reliability and dependency-failure testing
- Backup and restoration testing
- Browser and responsive-layout testing
- Usability and field-route validation
- Installation, deployment, and rollback testing

## 8. Risk-Based Priorities

| Priority | Failure example | Test response |
|---|---|---|
| P0 — Safety or trust critical | A stair-free request returns a route containing stairs | Test at unit, property, integration, and field levels; block release on failure |
| P0 — Security critical | A Visitor can create a closure or read protected contact data | Test every role and endpoint; block release on failure |
| P1 — Core product failure | Valid origin and destination cannot produce a known route | Automated regression plus end-to-end testing |
| P1 — Misleading result | Stale or unavailable data is shown as verified and current | Data-state and user-comprehension testing |
| P1 — Accessibility barrier | Keyboard or screen-reader user cannot complete route planning | Test throughout implementation and during audit |
| P2 — Operational degradation | Map tiles fail and text directions disappear | Dependency-failure testing before release candidate |
| P2 — Performance degradation | Route requests exceed the required response threshold | Benchmark continuously and load-test before release |
| P3 — Minor experience issue | Nonessential spacing or wording problem | Test during exploratory review; fix according to priority |

P0 and P1 tests receive priority when schedule or environment capacity is limited.

## 9. Test Environments

| Environment | Purpose | Configuration | Data |
|---|---|---|---|
| Local | Rapid development and debugging | Containerized or scripted local services | Small synthetic graph and test accounts |
| Continuous integration | Deterministic automated checks | Clean ephemeral environment per run | Seeded synthetic fixtures |
| Staging | Integration, end-to-end, accessibility, security, and performance testing | Production-like services with test identity adapter | Versioned representative campus dataset |
| Evaluation | Usability and field-route sessions | Release-like build with monitoring | Approved campus data and evaluation accounts |
| Production/pilot | Release verification and demonstration | Final approved configuration | Minimum approved production dataset |

### 9.1 Environment requirements

- Every environment must have a documented build or deployment procedure.
- Staging must use the same major runtime and database versions as production.
- Test accounts must represent Visitor, Editor, Administrator, disabled, expired, and unauthorized states.
- Test clocks or injectable time sources should be used for scheduled and expiring closure tests.
- External services should have documented simulators or test doubles for failure testing.
- Environment-specific secrets must be kept outside source control.
- Destructive tests must run only in an isolated environment containing disposable data.

## 10. Compatibility Matrix

The team will confirm the final browser versions at test time.

| Platform | Browser | Core workflow | Responsive layout | Keyboard | Screen reader |
|---|---|:---:|:---:|:---:|:---:|
| Windows | Current Chrome | Required | Required | Required | NVDA where available |
| Windows | Current Edge | Required | Required | Required | NVDA where available |
| macOS | Current Safari | Required | Required | Required | VoiceOver |
| macOS | Current Chrome | Required | Required | Required | Sampled |
| iOS | Current Safari | Required | Required | Sampled | VoiceOver |
| Android | Current Chrome | Required | Required | Sampled | TalkBack where available |

“Current” means the stable version available during the formal evaluation. Any unsupported combination must be disclosed.

## 11. Test Data Plan

### 11.1 Data sets

| Data set | Purpose | Contents |
|---|---|---|
| TD.01 Minimal graph | Unit and component tests | A few nodes containing stairs, ramp, elevator, and alternate paths |
| TD.02 Route decision graph | Property and integration tests | Competing routes designed to exercise every constraint and preference |
| TD.03 Closure timeline | Time-dependent tests | Draft, scheduled, active, expired, canceled, and open-ended closures |
| TD.04 Authorization matrix | Security tests | Visitor, Editor, Administrator, disabled user, expired session |
| TD.05 Invalid import set | Data validation tests | Missing endpoints, negative distances, conflicts, duplicates, malformed coordinates |
| TD.06 Representative campus set | Staging and evaluation | Approved campus routes, locations, assets, and verification times |
| TD.07 Performance graph | Benchmark and load tests | Dataset at or above expected pilot size |
| TD.08 Accessibility content set | Interface tests | Long names, warnings, errors, empty states, and status combinations |

### 11.2 Route-validation set

Each route-validation case will record:

- Case identifier
- Data-set version
- Origin and destination
- Constraints and preferences
- Active closure state
- Expected permitted and prohibited segments
- Expected outcome category
- Field-verification status where applicable
- Reviewer and review date

The validation set must include:

- A shortest route containing stairs and a longer stair-free alternative
- A route dependent on an elevator
- An active elevator closure
- A scheduled but not-yet-active closure
- An expired closure
- A steep segment at, below, and above the allowed threshold
- A destination with no known compatible route
- Multiple equally valid routes
- Stale accessibility data
- A disconnected graph and malformed data

### 11.3 Privacy and handling

- Automated tests must use synthetic identities and contact details.
- Evaluation records should use participant codes rather than names.
- Precise personal route histories must not be collected unless necessary and approved.
- Consent records must be separated from evaluation responses.
- Access to optional reporter contact information must be tested with least-privilege accounts.
- Evaluation and test data must follow the approved retention and deletion plan.

## 12. Automated Test Suite

### 12.1 Required continuous-integration checks

Every proposed change to the main branch will run:

- Formatting and linting
- Static type and compile checks
- Unit tests
- Component and API integration tests
- Database migration checks
- Dependency vulnerability scan
- Secret detection
- Selected accessibility checks for rendered components or pages
- Build and package verification

### 12.2 Scheduled checks

Nightly or scheduled staging runs will include:

- Full integration suite
- End-to-end public and administrative workflows
- Broader accessibility scan
- Route property tests with larger generated graphs
- Dependency and container scans
- Data-import validation against the current representative dataset
- Performance smoke test

### 12.3 Release-candidate checks

The release candidate will run:

- Complete automated regression suite
- Browser compatibility suite
- Authorization matrix
- Performance and load tests
- Backup and restoration exercise
- Deployment and rollback exercise
- Manual accessibility audit
- Exploratory and failure-mode testing
- Verification of corrected evaluation findings

## 13. Functional Test Matrix

| Test ID | Scenario | Level | Priority | Expected result | Requirements |
|---|---|---|:---:|---|---|
| FT.001 | Plan a route with valid origin and destination | End-to-end | P1 | Route map, text steps, distance, time, and warnings appear | FR.01, FR.02, FR.06 |
| FT.002 | Origin and destination are identical | API/UI | P2 | Request is rejected with a useful correction message | FR.02 |
| FT.003 | Avoid-stairs constraint with longer alternative | Unit/system | P0 | Returned route contains no stair segment | FR.03–FR.05 |
| FT.004 | No stair-free route exists | System | P0 | System reports no compatible route and does not relax the constraint | FR.08 |
| FT.005 | Route depends on an elevator | System | P1 | Elevator dependency appears in route details | FR.07 |
| FT.006 | Multiple qualifying alternatives exist | System | P2 | Up to two materially different alternatives are shown | FR.09 |
| FT.007 | Active closure affects shortest route | Integration | P0 | Affected segment or asset is excluded within 60 seconds | FR.16–FR.20 |
| FT.008 | Closure is scheduled for the future | Integration | P1 | Closure does not affect routes before its start time | FR.17–FR.20 |
| FT.009 | Closure expires | Integration | P1 | Closure stops affecting new routes after expiration | FR.20 |
| FT.010 | Submit complete feedback report | End-to-end | P1 | Report is stored as Unverified and receipt is confirmed | FR.22–FR.24 |
| FT.011 | Public report attempts to change route data | Security/system | P0 | Verified route data remains unchanged | FR.24 |
| FT.012 | Editor reviews feedback | End-to-end | P2 | Valid review status is stored and audited | FR.25 |
| FT.013 | Visitor invokes closure endpoint | API/security | P0 | Request is rejected; no closure is created | FR.27–FR.29 |
| FT.014 | Administrator grants Editor role | Integration | P1 | Role is changed and audit event is created | FR.28, FR.29 |
| FT.015 | Administrative export | Integration | P2 | Authorized data is exported in documented format | FR.31 |
| FT.016 | Relevant data is stale | System/UI | P1 | User receives a visible and understandable freshness warning | FR.13–FR.15 |

## 14. Nonfunctional Test Matrix

| Test ID | Quality area | Method | Pass condition | Requirements |
|---|---|---|---|---|
| NFT.A11Y.01 | Keyboard access | Complete core workflows without a pointing device | All controls are reachable, operable, visible, and logically ordered | NFR.01, NFR.02 |
| NFT.A11Y.02 | Text equivalent | Disable or ignore the visual map | Route and warning information remains available in text | NFR.03 |
| NFT.A11Y.03 | Color independence | Inspect all statuses and routes | Meaning does not depend on color alone | NFR.04 |
| NFT.A11Y.04 | Zoom/reflow | Test at 200% zoom and narrow viewport | No required information or control is lost | NFR.05 |
| NFT.A11Y.05 | Screen reader | Complete public route-planning flow | Names, states, errors, changes, and order are understandable | NFR.01–NFR.06 |
| NFT.PERF.01 | Route latency | Load test with approved workload | At least 95% of route requests complete within 2 seconds | NFR.07 |
| NFT.PERF.02 | API latency | Load test ordinary API requests | At least 95% complete within 500 ms | NFR.08 |
| NFT.PERF.03 | Concurrency | Simulate 100 concurrent route planners | Service remains correct and within approved degradation limits | NFR.09 |
| NFT.REL.01 | Map dependency failure | Block map-tile provider | Text route instructions remain usable | NFR.12 |
| NFT.REL.02 | Backup restoration | Restore latest backup into isolated environment | Database is restored and validation checks pass | NFR.13–NFR.15 |
| NFT.SEC.01 | Transport security | Inspect production endpoints | HTTPS is enforced; insecure requests are redirected or rejected | NFR.16 |
| NFT.SEC.02 | Session protection | Inspect cookie and session behavior | Required protections are enabled and logout invalidates session | NFR.17 |
| NFT.SEC.03 | Authorization | Execute role/endpoint matrix | Every unauthorized operation is rejected server-side | NFR.18 |
| NFT.SEC.04 | Input handling | Submit malicious and malformed content | Content is rejected or safely encoded; no script executes | NFR.20 |
| NFT.SEC.05 | Dependency risk | Scan final dependencies | No unresolved critical finding; high findings resolved or accepted | NFR.21, NFR.22 |
| NFT.PRIV.01 | Anonymous routing | Inspect requests, storage, and logs | No account, disability, or precise route history is required or retained | NFR.24–NFR.26 |
| NFT.PRIV.02 | Contact access | Attempt access with every role | Only authorized reviewers can access optional contact data | NFR.27 |
| NFT.MAINT.01 | New-developer setup | A teammate follows documentation from a clean environment | Application builds, tests, and runs without undocumented steps | NFR.30–NFR.35 |

## 15. Detailed Sample Test Cases

The following cases illustrate the expected level of clarity. The complete test repository may express stable cases as automated tests rather than repeating every implementation step in prose.

### TC-ROUTE-001: Stair-Free Constraint Overrides Shortest Distance

| Field | Value |
|---|---|
| Related requirements | FR.03, FR.05, FR.06; BR.01 |
| Priority | P0 |
| Test level | Unit, integration, and end-to-end |
| Preconditions | TD.02 is loaded; no closure is active |
| Test data | Route A→B: Segment S1 contains stairs and is 100 m; Segments S2+S3 are stair-free and total 160 m |

#### Steps

1. Select Location A as the origin.
2. Select Location B as the destination.
3. Enable **Avoid stairs**.
4. Request a route.

#### Expected results

- A route is returned using S2 and S3.
- S1 does not appear in the returned route.
- The displayed distance is 160 m, subject to documented rounding.
- The system explains that the shorter route was avoided because it contains stairs.
- Logs and telemetry do not record unnecessary personal information.

### TC-ROUTE-002: No Compatible Route

| Field | Value |
|---|---|
| Related requirements | FR.03, FR.05, FR.08 |
| Priority | P0 |
| Test level | Component and end-to-end |
| Preconditions | The only paths to Location C contain stairs |

#### Steps

1. Select Location A as the origin and Location C as the destination.
2. Enable **Avoid stairs**.
3. Request a route.

#### Expected results

- The system displays **No compatible route is known** or approved equivalent wording.
- No route containing stairs is displayed as a substitute.
- The response identifies the limiting constraint when the system can determine it.
- The user can revise the request without reloading the application.

### TC-CLOSURE-001: Active Elevator Outage Changes Route Results

| Field | Value |
|---|---|
| Related requirements | FR.16–FR.21, NFR.10, NFR.23 |
| Priority | P0 |
| Test level | Integration and end-to-end |
| Preconditions | An authenticated Editor exists; baseline Route A→D uses Elevator E1 |

#### Steps

1. Confirm that the baseline route uses E1.
2. Sign in as an Editor.
3. Create and activate a closure for E1 using valid times and a source.
4. Record the publication time.
5. Request Route A→D repeatedly until the update deadline.
6. Review the closure and audit records.

#### Expected results

- The Editor can publish the closure.
- New route results stop using E1 within 60 seconds.
- The route uses a qualifying alternative or reports that no compatible route is known.
- The audit record contains actor, action, target, outcome, and time.
- The audit record contains no authentication secret.

### TC-AUTH-001: Visitor Cannot Publish a Closure

| Field | Value |
|---|---|
| Related requirements | FR.27–FR.30, NFR.18 |
| Priority | P0 |
| Test level | API and security |
| Preconditions | No administrative session is present |

#### Steps

1. Send a syntactically valid closure-creation request to the administrative API.
2. Query the closure list using an authorized test account.
3. Inspect security and audit events.

#### Expected results

- The creation request receives the approved unauthenticated response.
- No closure record is created.
- No route result changes.
- The rejected attempt is recorded according to the security logging policy.
- The response does not expose stack traces, database details, or authorization rules useful to an attacker.

### TC-RECOVERY-001: Restore the Latest Backup

| Field | Value |
|---|---|
| Related requirements | NFR.13–NFR.15 |
| Priority | P1 |
| Test level | Operational recovery |
| Preconditions | A successful backup exists; an isolated recovery environment is available |

#### Steps

1. Record backup identifier, creation time, and expected record counts.
2. Start with an empty recovery database.
3. Follow the documented restoration procedure.
4. Run schema, integrity, and representative route checks.
5. Record elapsed recovery time and recovered data timestamp.

#### Expected results

- Restoration completes without an undocumented manual database change.
- Schema and integrity validation pass.
- Expected records are present within the recovery-point objective.
- Representative route and administrative queries succeed.
- Recovery completes within four hours.
- Any deviation is recorded as a defect or approved exception.

### TC-A11Y-001: Keyboard-Only Route Planning

| Field | Value |
|---|---|
| Related requirements | NFR.01–NFR.06 |
| Priority | P0 |
| Test level | Manual accessibility |
| Preconditions | Supported desktop browser; pointing device is not used |

#### Steps

1. Open the public route-planning page.
2. Navigate through the page using keyboard input only.
3. Select an origin and destination.
4. enable **Avoid stairs**.
5. Submit the request.
6. Navigate through the route summary, warnings, and steps.
7. Change a preference and recalculate.

#### Expected results

- Every interactive control is reachable and operable.
- Focus order is logical and focus remains visibly indicated.
- Selection states and validation errors are perceivable.
- Updated results are announced or otherwise discoverable without forcing the user to search the page.
- Map information required to complete the task is available in text.
- No keyboard trap occurs.

## 16. Exploratory Testing

Automated cases cannot anticipate every interaction. The team will conduct time-boxed exploratory sessions using charters such as:

- Attempt to produce an unsafe or misleading route result.
- Explore the product using only a keyboard and high zoom.
- Interrupt each workflow through refresh, back navigation, timeout, and duplicate submission.
- Combine extreme preferences and boundary values.
- Explore stale, missing, contradictory, and changing data.
- Attempt privileged actions as each role.
- Cause external identity, map, database, and notification failures.
- Inspect whether errors and logs disclose sensitive details.
- Use long names, special characters, and unexpected Unicode input.
- Explore the mobile interface with poor connectivity.

Each session will record its charter, build, environment, tester, duration, observations, defects, and unanswered questions.

## 17. Accessibility Test Plan

Accessibility testing will begin with prototypes and continue throughout development.

### 17.1 Automated checks

Automated tools will identify selected issues such as missing accessible names, invalid relationships, some contrast failures, and structural problems. Automated results are useful but are not evidence of complete accessibility conformance.

### 17.2 Manual checks

The team will test:

- Keyboard navigation and focus management
- Screen-reader names, roles, states, errors, and dynamic updates
- Heading and landmark structure
- Form labels, instructions, validation, and recovery
- Color contrast and non-color communication
- Zoom, reflow, text spacing, and responsive layout
- Touch-target size where applicable
- Text alternatives for meaningful map information
- Reduced motion where motion is introduced
- Clarity of warnings, limitations, and no-route messages

### 17.3 Accessibility evidence

The final report will include:

- Browsers and assistive technologies tested
- Workflows and pages tested
- Automated and manual findings
- Severity and disposition of each finding
- Known limitations and untested combinations
- Confirmation that participants with relevant lived experience were included where feasible and appropriate

## 18. Security and Privacy Test Plan

### 18.1 Security activities

- Review the data-flow and threat model.
- Test authentication success, failure, logout, timeout, and disabled-account behavior.
- Execute an endpoint-by-role authorization matrix.
- Test direct-object and identifier manipulation.
- Test validation and safe output encoding.
- Inspect session and cookie protections.
- Confirm HTTPS and approved security headers.
- Scan dependencies, images, and source for known vulnerabilities and secrets.
- Test rate limiting and abuse controls for public feedback.
- Inspect error responses and logs for information disclosure.
- Verify audit events for successful and rejected privileged activity.

Testing must remain within systems and accounts the team is authorized to test.

### 18.2 Privacy activities

- Inventory data collected by the UI, API, database, logs, analytics, and third parties.
- Confirm anonymous users are not required to identify themselves.
- Confirm precise route history is not stored by default.
- Inspect logs for full IP addresses, contact details, tokens, and route details.
- Test access to optional contact data with every role.
- Test retention and deletion behavior where implemented.
- Compare actual behavior with the privacy notice.

## 19. Performance Test Plan

### 19.1 Workload model

The documented workload will include:

- A representative campus graph at or above expected pilot size
- A mixture of short and long routes
- Requests with and without hard constraints
- Routes affected by active closures
- Read-heavy public traffic plus limited administrative traffic
- Up to 100 concurrent route-planning users

### 19.2 Measurements

The team will record:

- Request count and concurrency
- Median, 95th percentile, and 99th percentile latency
- Throughput
- Error and timeout rate
- CPU, memory, database, and network indicators
- Test-data version, application build, environment, and duration

### 19.3 Pass conditions

- At least 95% of route requests complete within two seconds.
- At least 95% of ordinary API requests complete within 500 milliseconds.
- The system supports 100 concurrent route planners without incorrect results or uncontrolled failure.
- Any approved degradation limit or exception is explicitly documented.

A single fast request on a developer laptop is not sufficient performance evidence.

## 20. Reliability and Recovery Test Plan

The team will test:

- Map-tile provider unavailable
- Identity provider unavailable during sign-in
- Database connection interrupted
- Route calculation timeout
- Duplicate closure or feedback submission
- Application process restart
- Deployment failure and rollback
- Missing or malformed configuration
- Backup creation and restoration
- Monitoring detection of a known failure

For each failure, the team will verify system behavior, user communication, data integrity, logging, alerting, and recovery.

## 21. Usability and Field Validation

### 21.1 Participants

The target is 5–8 representative participants for the formal MVP evaluation. The team will seek variation in familiarity with campus, device use, and relevant mobility or accessibility needs. Recruitment, consent, accommodation, and data collection will follow instructor and university guidance.

### 21.2 Representative tasks

- Plan a stair-free route between two known locations.
- Determine why an accessible route is longer.
- Identify whether the route depends on an elevator.
- Respond to a no-compatible-route result.
- Change preferences and recalculate.
- Report inaccurate route information.

### 21.3 Measures

- Task completion without assistance
- Critical errors and recovery
- Time on task
- Route completion during approved field trials
- Understanding of warnings, uncertainty, and limitations
- Participant comments and observed barriers

### 21.4 Interpretation

The team will report participant count, method, conditions, raw measure definitions, results, and limitations. Findings from a small convenience sample will not be generalized to every possible user.

## 22. Test Schedule

The schedule aligns with the one-semester [Sample Project Plan](./Sample%20Project%20Plan.md).

| Period | Test focus | Exit evidence |
|---|---|---|
| Sep. 14–25 | Requirements review, acceptance criteria, test architecture, minimal route graph | Testable baseline and initial automated suite |
| Sep. 28–Oct. 9 | Technical spikes, data validation, prototype accessibility, CI quality checks | Highest-risk assumptions tested |
| Oct. 12–23 | Route-engine properties, API integration, walking-skeleton end-to-end tests | Core route flow passes in staging |
| Oct. 26–Nov. 6 | Closure, feedback, authorization, audit, browser, and failure tests | Mandatory workflow coverage grows with implementation |
| Nov. 9–13 | Full MVP regression and evaluation readiness | Feature-complete evaluation build |
| Nov. 16–20 | Usability, field-route, accessibility, security, and privacy evaluation | Findings recorded and prioritized |
| Nov. 23–25 | Performance, recovery, corrections, and regression | Release-candidate evidence package |
| Nov. 30–Dec. 2 | Final regression, deployment, rollback, and release verification | Release recommendation |
| Dec. 4 | Final presentation and demonstration | Tagged release and archived evidence |

Testing is continuous; this schedule identifies emphasis rather than the first time each activity occurs.

## 23. Roles and Responsibilities

| Role | Testing responsibilities |
|---|---|
| Product and research lead | Acceptance criteria, participant coordination, usability protocol, product-result interpretation |
| Technical and route-engine lead | Unit/property tests, route-validation set, algorithm correctness, performance analysis |
| Experience and accessibility lead | UI tests, accessibility audit, browser matrix, usability observation |
| Platform and quality lead | CI, integration/end-to-end tests, security, reliability, environment, backup and recovery |
| Entire team | Review, exploratory testing, defect correction, regression, documentation, final evidence |
| Sponsor or domain reviewer | Validate terminology, representative routes, and operational assumptions |
| Faculty advisor | Review scope, ethical concerns, evaluation method, and release evidence |

The author of a change is responsible for initial tests; another team member must review consequential test logic and results.

## 24. Entry and Exit Criteria

### 24.1 Formal evaluation entry criteria

Formal MVP evaluation may begin when:

- The release build is identified and deployed to the evaluation environment.
- All mandatory workflows are integrated.
- P0 automated tests pass.
- No known critical security, privacy, data-loss, or accessibility defect remains open.
- Representative test data has passed validation.
- The evaluation protocol, consent approach, and recruitment are approved as required.
- Monitoring is active and rollback is available.

### 24.2 Release exit criteria

The team may recommend release when:

- Every P0 test passes.
- At least 95% of approved P1 tests pass, with no failed P1 case lacking a documented decision.
- All mandatory requirements have evidence or an approved exception.
- No critical defect or vulnerability remains open.
- High-severity findings are resolved or formally accepted with justification and owner.
- Accessibility, usability, field-route, performance, and recovery evaluation is complete.
- The full regression suite passes on the release candidate.
- Known limitations and residual risks are documented for users and stakeholders.
- Deployment, rollback, monitoring, backup, and restoration evidence is available.

Passing percentages do not override a critical failure. One unsafe routing defect can block release even if hundreds of lower-risk tests pass.

## 25. Defect Management

### 25.1 Defect workflow

1. **New:** Finding has been recorded with evidence.
2. **Triaged:** Severity, priority, owner, and affected requirement are agreed.
3. **In progress:** Correction or investigation is underway.
4. **Ready for verification:** A proposed correction is available in a test environment.
5. **Closed:** Original case and relevant regression tests pass.
6. **Deferred or accepted:** Decision, rationale, risk, owner, and target are documented.

### 25.2 Required defect information

- Concise title
- Build and environment
- Preconditions and data version
- Reproduction steps
- Expected and actual result
- Screenshots, logs, traces, or other useful evidence without sensitive data
- Affected requirement, use case, or risk
- Severity and proposed priority
- Owner and status
- Verification evidence when closed

### 25.3 Severity definitions

| Severity | Definition | Example |
|---|---|---|
| Critical | Safety risk, severe security/privacy exposure, data loss, or mandatory system unavailable | Stair-free route includes stairs; Visitor can publish closures |
| High | Core requirement fails with no reasonable workaround | Route planning fails for valid ordinary requests |
| Medium | Requirement partially fails or a reasonable workaround exists | Alternative route lacks an explanation |
| Low | Limited cosmetic, wording, or convenience issue | Nonessential alignment problem |

Severity describes impact; priority also considers likelihood, affected users, schedule, and correction cost.

## 26. Test Evidence and Reporting

### 26.1 Evidence retained

- Automated test reports linked to a commit and build
- Versioned test data and validation results
- Manual test session records
- Accessibility findings
- Security and dependency reports
- Performance scripts, workload, environment, and results
- Backup and recovery record
- Usability protocol, de-identified results, and analysis
- Defect and exception decisions
- Final requirements traceability matrix

### 26.2 Weekly test status

The team will report:

- Tests added and important risks covered
- P0/P1 pass and failure status
- New, closed, and aging defects by severity
- Unstable or blocked test environments
- Evaluation readiness
- Significant gaps and decisions needed

Raw test counts will not be presented as proof of quality without explaining what risks the tests cover.

### 26.3 Final test summary

The final summary will state:

- Release and environment tested
- Scope completed and omitted
- Requirements verified, failed, or excepted
- Test results by quality area
- Product-validation results and sample limitations
- Open defects and residual risks
- Deviations from this plan
- Release recommendation with rationale

## 27. Requirements Traceability

| Requirement group | Principal test evidence |
|---|---|
| FR.01–FR.10: Route planning | Unit, property, integration, end-to-end, route-validation, and field tests |
| FR.11–FR.15: Accessibility data | Import validation, stale-data, verified/unverified state, and UI tests |
| FR.16–FR.21: Closures | Time-controlled component tests, integration, end-to-end, audit verification |
| FR.22–FR.26: Feedback | API/UI cases, rate-limit and abuse tests, review workflow |
| FR.27–FR.31: Administration | Authentication, endpoint/role matrix, audit, and export tests |
| NFR.01–NFR.06: Accessibility | Automated scan plus keyboard, zoom, reflow, contrast, and screen-reader audit |
| NFR.07–NFR.10: Performance | Benchmarks, load tests, and closure-propagation measurement |
| NFR.11–NFR.15: Reliability | Monitoring observation, dependency failure, backup, and restoration |
| NFR.16–NFR.23: Security | Configuration review, authorization, input, dependency, and audit tests |
| NFR.24–NFR.29: Privacy | Data-flow inspection, storage/log review, role access, retention verification |
| NFR.30–NFR.35: Maintainability | Clean setup, CI, migration, deployment, and external-adapter tests |

The final traceability record should link individual requirements to specific automated cases, manual records, defects, and results.

## 28. Risks to Testing

| Risk | Effect | Mitigation |
|---|---|---|
| Representative users cannot be recruited | Weak evidence of usability and real-world value | Recruit early through approved channels; use prototype sessions before formal evaluation |
| Campus data remains incomplete | Expected route results may be unreliable | Use a bounded verified pilot area and disclose coverage |
| MVP is delivered late | Evaluation and correction time is lost | Freeze lower-priority scope; require walking skeleton by Oct. 23 and MVP by Nov. 13 |
| Test environment differs from release | Results may not predict release behavior | Use production-like versions and repeat critical tests on release candidate |
| Automated tests are flaky | Failures become ignored and confidence falls | Quarantine only with an owner and deadline; diagnose nondeterminism |
| Accessibility testing lacks assistive technology or expertise | Important barriers may remain undetected | Use available university resources, representative users, and disclose gaps |
| Third-party service limits testing | Failure and load behavior remains unknown | Use authorized simulators/test doubles and document untested provider behavior |
| Test evidence contains sensitive data | Privacy harm or policy violation | Use synthetic data, redact artifacts, and restrict evaluation records |

## 29. Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Product owner or sponsor |  |  |  |
| Test-plan owner |  |  |  |
| Project team representative |  |  |  |
| Faculty advisor |  |  |  |

---

## Notes for Students

A strong test plan is not a long inventory of tools or a claim that “we will test everything.” It identifies what could fail, why that failure matters, how the team will detect it, what evidence is required, and what result is sufficient to release.

For your own project:

- Begin with requirements, users, architecture, and risk.
- Write expected results before executing a test.
- Test failure behavior and permission boundaries.
- Combine automation with human evaluation where appropriate.
- Keep test data and environments reproducible.
- Trace important requirements to evidence.
- Protect time to correct what evaluation discovers.
- Report limitations and residual risks honestly.
- Remember that passing tests establish only what those tests actually measured.

