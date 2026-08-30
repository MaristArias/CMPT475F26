# Sample Software Requirements Specification

## AccessPath: Accessible Campus Navigation

> **Purpose of this document:** This is a fictional example for CMPT 475. It demonstrates an appropriate structure and level of detail for a Capping Project requirements document. Students should adapt the structure to their own projects rather than copying the requirements themselves.

| Document field | Value |
|---|---|
| Project | AccessPath |
| Document type | Software Requirements Specification (SRS) |
| Version | 1.0 |
| Status | Sample baseline |
| Authors | Sample Student Team |
| Last updated | August 30, 2026 |

## 1. Executive Summary

AccessPath is a web application that helps members of a university community plan accessible walking routes across campus. Unlike conventional mapping applications, AccessPath considers barriers such as stairs, steep slopes, construction closures, inaccessible entrances, and elevators that are temporarily out of service.

The initial product will allow a user to select an origin, a destination, and relevant mobility preferences. It will return an accessible route, explain why that route was selected, and communicate known limitations in the available data. Authorized campus personnel will be able to update closures and accessibility information.

The project will be considered successful if representative users can plan suitable routes more reliably than they can with the university's existing static accessibility map.

## 2. Problem Statement

People with mobility-related accessibility needs may encounter barriers that are absent from ordinary campus maps. A route that is geographically shortest may include stairs, excessive slopes, an inaccessible entrance, or an elevator that is not operating. Information about temporary conditions may be distributed across webpages, email notices, signs, and personal knowledge.

This creates several problems:

- Users may arrive late because they must find an alternative route.
- A route may become unsafe or impossible to complete.
- Visitors may not know which entrances or interior connections are accessible.
- Campus personnel may lack a single mechanism for publishing temporary accessibility changes.

AccessPath will address the information and route-planning portions of this problem. It will not guarantee that every physical condition has been detected or corrected.

## 3. Goals and Success Measures

### 3.1 Product goals

1. Help users identify routes compatible with their stated accessibility needs.
2. Make permanent and temporary barriers visible before a trip begins.
3. Allow authorized personnel to publish important accessibility updates quickly.
4. Provide a usable and accessible experience on mobile and desktop devices.
5. Communicate uncertainty instead of presenting incomplete data as guaranteed fact.

### 3.2 Success measures

| ID | Measure | Target | Evaluation method |
|---|---|---:|---|
| SM.01 | Route completion rate | At least 90% of test routes completed without encountering a known incompatible barrier | Moderated field tests with representative users |
| SM.02 | Task completion | At least 85% of participants can plan a route without assistance | Usability test |
| SM.03 | Planning time | Median route-planning time of 60 seconds or less | Usability test instrumentation |
| SM.04 | Route validity | 100% of routes in the validation set obey the selected hard constraints | Automated route-engine tests |
| SM.05 | Update latency | A published closure appears in route results within 60 seconds | Integration and performance test |
| SM.06 | Accessibility | No critical WCAG 2.2 Level AA violations in the tested workflows | Automated scan plus manual audit |
| SM.07 | Availability | 99.0% availability during the final 30-day evaluation period | External uptime monitor |

Targets are project goals, not claims that the finished system can eliminate all navigation risk.

## 4. Stakeholders and Users

| Stakeholder or user | Needs and interests |
|---|---|
| Students, employees, and visitors with mobility needs | Accurate routes, clear barrier information, accessible interaction, privacy |
| People with temporary injuries | Routes avoiding stairs, steep slopes, or long distances |
| Campus Accessibility Services | Accurate representation of accessibility needs and responsible communication |
| Facilities Management | A fast way to publish closures and equipment outages |
| Campus Safety | Clear emergency messaging and avoidance of unsafe conditions |
| System administrators | Secure access, reliable operation, logs, backups, and maintainable deployment |
| Project team | Feasible scope, testable requirements, and access to appropriate data |

## 5. Assumptions and Dependencies

The requirements assume that:

- The university grants permission to use or reproduce the required campus map data.
- The project team can obtain or create an initial inventory of paths, entrances, stairs, ramps, and elevators.
- Facilities personnel or a designated instructor can act as sample administrative users during evaluation.
- Users have a modern browser and an internet connection while planning a route.
- The application is advisory and is not an emergency-response system.
- Temporary condition data will be incomplete unless authorized personnel keep it current.

External dependencies may include a map-rendering library, geospatial database, identity provider, hosting platform, and notification service. Final selections will be recorded in architecture decision records.

## 6. Scope

### 6.1 In scope for the minimum viable product

- Browser-based route planning for the main campus
- Selection of an origin and destination
- Preferences to avoid stairs, steep slopes, elevators, or outdoor segments
- Route calculation using permanent map attributes and active closures
- Step-by-step route instructions and a visual map
- Explanation of significant route choices and known warnings
- Administrative creation, editing, activation, and expiration of closures
- Basic user feedback about incorrect map or barrier information
- Responsive and accessible interaction on mobile and desktop browsers
- Monitoring, audit logging, backup, and reproducible deployment

### 6.2 Out of scope for the minimum viable product

- Turn-by-turn GPS positioning inside buildings
- Automatic detection of every temporary obstruction
- Emergency evacuation guidance
- Routing for motor vehicles
- Native iOS or Android applications
- Navigation for campuses other than the main campus
- Medical advice or individualized safety guarantees
- Automatic routing based on a stored disability profile

### 6.3 Possible future capabilities

- Indoor positioning
- Crowd-sourced reports with verification workflows
- Push notifications for saved routes
- Integration with elevator monitoring systems
- Additional accessibility preferences
- Support for other campuses and public transportation connections

Future capabilities are not commitments for the current project.

## 7. User Roles

| Role | Description | Authentication required? |
|---|---|---|
| Visitor | Plans routes and views published accessibility information | No |
| Reporter | Submits feedback about a possible barrier or map error | No, unless misuse requires a later policy change |
| Editor | Creates and updates closure records | Yes |
| Administrator | Manages editor access and reviews audit records | Yes |

The system will not require ordinary route-planning users to create accounts.

## 8. User Stories

### US.01: Plan a stair-free route

As a campus visitor who cannot use stairs, I want to request a stair-free route so that I can reach my destination without encountering an impassable barrier.

**Acceptance criteria:**

- Given a valid origin and destination, when the user selects **Avoid stairs**, then every segment in the returned route is marked as stair-free.
- If no qualifying route is known, the system clearly states that it cannot find one and does not silently return a route containing stairs.
- The result identifies any elevator on which the route depends.

### US.02: Understand a longer route

As a user, I want to know why an accessible route is longer than the shortest route so that I can make an informed decision.

**Acceptance criteria:**

- When the accessible route is more than 10% longer than the unconstrained shortest route, the result explains the primary avoided barrier or constraint.
- The explanation uses plain language and does not expose internal implementation details.

### US.03: Publish an elevator outage

As a Facilities editor, I want to record an elevator outage with an expected end time so that new routes avoid that elevator while the outage is active.

**Acceptance criteria:**

- Only an authenticated Editor or Administrator can publish the outage.
- The editor must identify the elevator, start time, status, and source of the information.
- The outage affects new route calculations within 60 seconds of publication.
- The record automatically becomes inactive at its expiration time unless the editor extends it.
- The create, edit, and expiration events appear in the audit log.

### US.04: Report inaccurate information

As a route-planning user, I want to report a possible barrier or map error so that authorized staff can investigate it.

**Acceptance criteria:**

- The user can select the affected location on the map or identify a route step.
- The report requires a category and description.
- Personal contact information is optional.
- The application confirms receipt without implying that the report has been verified.
- A public report cannot directly modify production route data.

## 9. Functional Requirements

The keywords **MUST**, **SHOULD**, and **MAY** indicate required, recommended, and optional behavior.

### 9.1 Route planning

- **FR.01:** The system MUST allow a user to select an origin and destination from known campus locations.
- **FR.02:** The system MUST validate that the origin and destination are different and belong to the supported map area.
- **FR.03:** The system MUST support hard constraints for avoiding stairs and active closures.
- **FR.04:** The system MUST support preferences for maximum slope, maximum route distance, elevator use, and indoor or outdoor travel.
- **FR.05:** The route engine MUST exclude any segment that violates a selected hard constraint.
- **FR.06:** The system MUST return a map, estimated distance, estimated travel time, and ordered route steps.
- **FR.07:** The system MUST identify active warnings and infrastructure dependencies relevant to the route.
- **FR.08:** When no compatible route is known, the system MUST say so and MUST NOT substitute an incompatible route without explicit user consent.
- **FR.09:** The system SHOULD provide up to two alternative qualifying routes when materially different alternatives exist.
- **FR.10:** The user MUST be able to revise preferences and recalculate the route.

### 9.2 Accessibility information

- **FR.11:** The system MUST represent paths, stairs, ramps, entrances, elevators, and relevant interior connections.
- **FR.12:** Each route segment MUST record the accessibility attributes used by the route engine.
- **FR.13:** User-facing information MUST display when a relevant record was last verified.
- **FR.14:** The system MUST distinguish verified information from unverified user reports.
- **FR.15:** The system SHOULD warn the user when a route depends on information older than the configured review interval.

### 9.3 Closure management

- **FR.16:** An Editor MUST be able to create, view, update, activate, deactivate, and expire a closure.
- **FR.17:** A closure MUST identify the affected asset or map segment, status, effective time, source, and editor.
- **FR.18:** The system MUST prevent an Editor from creating a closure whose end time precedes its start time.
- **FR.19:** Active closures MUST affect route calculation within the target update latency.
- **FR.20:** Expired or deactivated closures MUST cease affecting route calculation.
- **FR.21:** The system MUST retain an audit history of administrative changes.

### 9.4 Feedback

- **FR.22:** A user MUST be able to submit a report associated with a location or route step.
- **FR.23:** A report MUST include a category, description, submission time, and review status.
- **FR.24:** The system MUST treat all public reports as unverified until reviewed by an Editor.
- **FR.25:** An Editor MUST be able to mark a report as under review, resolved, rejected, or duplicate.
- **FR.26:** The application MUST rate-limit public report submissions.

### 9.5 Administration

- **FR.27:** Administrative functions MUST require authentication.
- **FR.28:** The system MUST enforce role-based authorization for Editor and Administrator actions.
- **FR.29:** An Administrator MUST be able to grant or remove the Editor role.
- **FR.30:** The system MUST record successful and failed administrative sign-in attempts.
- **FR.31:** An Administrator MUST be able to export active closures and audit records in a documented format.

## 10. Nonfunctional Requirements

### 10.1 Accessibility and usability

- **NFR.01:** The route-planning and administrative workflows MUST conform to WCAG 2.2 Level AA for the tested scope.
- **NFR.02:** All functionality MUST be operable using a keyboard alone.
- **NFR.03:** Information conveyed visually on the map MUST also be available in text.
- **NFR.04:** The interface MUST not rely on color alone to communicate route status or barriers.
- **NFR.05:** At 200% browser zoom, required content and controls MUST remain usable without loss of information.
- **NFR.06:** Error messages MUST identify the problem and provide a useful recovery action.

### 10.2 Performance

- **NFR.07:** At least 95% of route requests in the agreed test workload MUST complete within 2 seconds, excluding third-party map-tile loading.
- **NFR.08:** At least 95% of ordinary API requests MUST complete within 500 milliseconds under the same workload.
- **NFR.09:** The system MUST support 100 concurrent route-planning users during the project evaluation.
- **NFR.10:** An administrative update MUST affect route results within 60 seconds.

### 10.3 Reliability and recovery

- **NFR.11:** The deployed system SHOULD achieve 99.0% availability during the final 30-day evaluation period, excluding announced maintenance.
- **NFR.12:** A failure to retrieve optional map tiles MUST NOT cause the text route instructions to disappear.
- **NFR.13:** Production data MUST be backed up at least once every 24 hours.
- **NFR.14:** The team MUST demonstrate restoration of the application database from a backup before final release.
- **NFR.15:** The recovery point objective MUST be no more than 24 hours, and the recovery time objective MUST be no more than 4 hours for the project deployment.

### 10.4 Security

- **NFR.16:** All network communication MUST use HTTPS in production.
- **NFR.17:** Administrative sessions MUST use secure, HTTP-only, same-site cookies or an equivalently protected mechanism.
- **NFR.18:** The system MUST validate authorization on the server for every privileged operation.
- **NFR.19:** Secrets MUST NOT be stored in the source repository or client-side application.
- **NFR.20:** User-supplied content MUST be validated and safely encoded before display.
- **NFR.21:** Dependencies MUST be scanned for known vulnerabilities as part of continuous integration.
- **NFR.22:** High-severity vulnerabilities affecting an exposed component MUST be resolved or formally accepted with documented justification before release.
- **NFR.23:** Audit records MUST identify the actor, action, target, result, and time without storing authentication secrets.

### 10.5 Privacy

- **NFR.24:** Anonymous route requests MUST NOT require the user's name, disability, or account identifier.
- **NFR.25:** The application MUST NOT store a user's precise location history by default.
- **NFR.26:** Operational logs MUST avoid full IP addresses and other unnecessary personal data whenever technically feasible.
- **NFR.27:** Optional contact information submitted with a report MUST be visible only to authorized reviewers.
- **NFR.28:** The system MUST publish a plain-language privacy notice describing collected data, purpose, access, retention, and deletion.
- **NFR.29:** Unneeded feedback contact information MUST be deleted after the documented retention period.

### 10.6 Maintainability and portability

- **NFR.30:** A new developer MUST be able to build and run the development environment by following the repository documentation.
- **NFR.31:** Database schema changes MUST be versioned and reproducible.
- **NFR.32:** Automated tests MUST cover the route engine's hard-constraint rules.
- **NFR.33:** The main branch MUST pass formatting, static analysis, unit tests, and dependency checks before deployment.
- **NFR.34:** The system MUST be deployable from version-controlled configuration without undocumented manual production changes.
- **NFR.35:** External services MUST be accessed through documented interfaces so they can be replaced without rewriting unrelated domain logic.

## 11. Data Requirements

### 11.1 Principal data entities

| Entity | Purpose | Example attributes |
|---|---|---|
| Location | A selectable origin or destination | ID, name, coordinates, building, entrance references |
| Segment | A traversable connection in the route graph | Start, end, distance, slope, surface, indoor/outdoor, stairs |
| Accessibility asset | Infrastructure relevant to a route | Type, location, status, last verified time |
| Closure | A temporary restriction or warning | Asset/segment, status, start, end, source, editor |
| Feedback report | An unverified user observation | Location, category, description, status, optional contact |
| User account | An authorized administrative identity | Institutional ID, role, status |
| Audit event | A record of a privileged action | Actor, action, target, outcome, timestamp |

### 11.2 Data quality rules

- Every traversable segment must have valid endpoints and a nonnegative distance.
- Any segment marked as containing stairs must not be considered stair-free.
- Administrative records must include their source and last-updated time.
- Unverified reports must never be interpreted by the route engine as verified closures.
- Route data imports must be validated before replacing the active dataset.
- Conflicting accessibility attributes must be flagged for review rather than silently resolved.

### 11.3 Retention

| Data | Proposed retention |
|---|---|
| Active map and accessibility data | While current, with version history retained for the project |
| Closure records | Current academic year plus one year |
| Audit events | One year |
| Feedback reports | Until resolved plus 90 days |
| Optional reporter contact information | Until resolution or 90 days, whichever occurs first |
| Anonymous operational metrics | 90 days |

Retention periods are provisional and must be reviewed with the project sponsor before production use.

## 12. External Interface Requirements

### 12.1 User interface

The public interface will provide:

- Origin and destination selection
- Accessibility preferences
- A route summary
- Text directions synchronized with a map
- Warnings, data freshness, and route limitations
- A feedback-reporting workflow

The administrative interface will provide:

- Authenticated access
- Closure and accessibility record management
- Feedback review
- Audit-log viewing
- Data export

### 12.2 API

The application SHOULD expose a versioned API for route requests and administrative operations. API errors must use a consistent documented structure. Privileged endpoints must reject unauthenticated and unauthorized requests without revealing sensitive details.

### 12.3 External systems

Potential integrations include:

- University single sign-on for administrative users
- A geospatial map or tile provider
- University facilities data
- Email notification for administrative workflow events
- Monitoring and error-reporting services

The team must document what happens when each external dependency is unavailable.

## 13. Business Rules

- **BR.01:** Safety- or accessibility-related hard constraints take precedence over route length.
- **BR.02:** An unverified public report may generate a warning for an Editor but may not automatically close a path.
- **BR.03:** Only an Administrator may grant administrative roles.
- **BR.04:** A closure with no known end time remains active until an Editor resolves it.
- **BR.05:** The system must show uncertainty when the available data cannot establish that a route satisfies the user's constraints.
- **BR.06:** The product must not describe a route as “guaranteed accessible.”

## 14. Constraints

- The project must be completed within the academic-year Capping schedule.
- The team has a limited or zero-cost hosting budget unless additional resources are approved.
- The solution must use data the team has permission to collect, store, and publish.
- The product must work in current versions of major desktop and mobile browsers.
- The project team cannot certify compliance with building codes or guarantee real-time physical conditions.

## 15. Risks and Mitigations

| Risk | Likelihood | Impact | Planned mitigation |
|---|---|---|---|
| Incomplete or inaccurate accessibility data | High | High | Begin data audit early; display freshness and uncertainty; validate priority routes in person |
| Lack of representative user participation | Medium | High | Engage Accessibility Services early; provide multiple evaluation methods; compensate participants if possible |
| Scope expands into indoor positioning | Medium | High | Keep indoor GPS explicitly out of MVP; support selected indoor connections through static graph data |
| Third-party map dependency changes | Medium | Medium | Isolate provider integration; cache permitted data; document replacement path |
| Public feedback is abusive or misleading | Medium | Medium | Rate-limit submissions; treat reports as unverified; provide review workflow |
| Administrative account compromise | Low | High | Use institutional sign-on if available; least privilege; audit logs; session protections |
| Users interpret routes as guaranteed safe | Medium | High | Use careful language; display sources, timestamps, and limitations; test comprehension |

## 16. Verification and Validation Plan

| Requirement type | Primary verification method |
|---|---|
| Route constraint rules | Unit tests and property-based tests |
| API and database behavior | Integration tests |
| Complete user workflows | End-to-end tests |
| Accessibility | Automated tools, keyboard testing, screen-reader testing, and manual review |
| Security | Threat model, static analysis, dependency scanning, authorization tests, and targeted penetration testing |
| Performance | Repeatable load tests using the agreed workload |
| Reliability and recovery | Uptime monitoring, fault tests, and backup-restoration exercise |
| Usability and product value | Moderated testing with representative participants and field-route trials |

No requirement is considered complete merely because code has been written. Completion requires the specified evidence.

## 17. Requirements Traceability Sample

| Goal | User story | Requirements | Verification |
|---|---|---|---|
| Accessible route planning | US.01 | FR.01–FR.10, BR.01 | Route-engine unit tests, integration tests, field trials |
| Explain route choices | US.02 | FR.06–FR.09, NFR.06 | End-to-end tests and usability study |
| Timely closure updates | US.03 | FR.16–FR.21, NFR.10 | Integration test, authorization test, timing measurement |
| Responsible public feedback | US.04 | FR.22–FR.26, NFR.27–NFR.29 | End-to-end test, abuse test, privacy review |
| Inclusive interface | All | NFR.01–NFR.06 | Automated and manual accessibility audit |

The project team's traceability table should eventually connect every approved requirement to design components, work items, and verification evidence.

## 18. Release Acceptance Criteria

The MVP is ready for final release only when:

1. All MUST requirements are implemented or an approved exception is documented.
2. No known route in the validation set violates a selected hard constraint.
3. The agreed usability and accessibility evaluations are complete.
4. No unresolved critical security vulnerability is known.
5. Performance targets are met under the documented test workload.
6. Backup restoration has been demonstrated.
7. Deployment and operational procedures have been tested by someone other than their author.
8. Known limitations, data freshness, and user-facing disclaimers are documented.
9. The project sponsor or instructor has reviewed the release evidence.

## 19. Open Questions

- Which campus office will own closure information after the class project ends?
- What map and building data may the project legally publish?
- Which preferences should be hard constraints and which should be optimization preferences?
- What slope thresholds are meaningful to representative users?
- Can the team use institutional single sign-on?
- How will routes through buildings be verified outside normal operating hours?
- What is the correct retention policy for feedback and audit data?

Open questions should be assigned owners and resolved by a stated date. Until resolved, they represent project risk.

## 20. Change Control

After this document is approved as the project baseline:

1. A proposed requirement change must state its reason, priority, and affected stakeholder.
2. The team must assess its effect on scope, architecture, schedule, risk, testing, and documentation.
3. Material changes require approval from the product owner or project sponsor.
4. Approved changes must update the requirement identifier, acceptance criteria, traceability information, and backlog.
5. Removed requirements remain in version history with the reason for removal.

## 21. Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Product owner or sponsor |  |  |  |
| Project team representative |  |  |  |
| Faculty advisor |  |  |  |

---

## Notes for Students

This sample is intentionally detailed, but a strong requirements document is not judged by length. It is judged by whether it gives the team and stakeholders a shared, testable understanding of the system.

For your own project:

- Replace generic aspirations with measurable conditions.
- Separate requirements from possible implementation choices.
- Give requirements stable identifiers.
- State what is outside the project scope.
- Record assumptions and unresolved questions honestly.
- Connect each important requirement to acceptance evidence.
- Update the document when the team's understanding changes.

