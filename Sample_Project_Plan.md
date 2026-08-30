# Sample Project Plan

## AccessPath: Accessible Campus Navigation

> **Purpose of this document:** This is a fictional example for CMPT 475. It demonstrates how a Capping team might organize and manage a one-semester software project. Dates, roles, estimates, and practices should be adapted to each team's actual project.

| Document field | Value |
|---|---|
| Project | AccessPath |
| Document type | Project Plan |
| Version | 1.1 |
| Status | Revised one-semester sample baseline |
| Project period | August 31–December 4, 2026 |
| Team | Sample Student Team |
| Last updated | August 30, 2026 |

## 1. Project Summary

AccessPath is a browser-based application that helps members of a university community plan accessible walking routes across campus. It considers permanent and temporary barriers such as stairs, steep slopes, inaccessible entrances, construction closures, and elevator outages.

The team will deliver a tested and deployed minimum viable product for the main campus. The product will include accessible route planning, route explanations and warnings, closure management for authorized personnel, public feedback, operational monitoring, and project documentation.

This plan translates the approved [Sample Requirements Document](./Sample%20Requirements%20Document.md) into an executable sequence of work. It describes how the team will deliver, evaluate, and communicate the project.

## 2. Project Objectives

The project has five objectives:

1. Validate that accessible campus routing is a real and meaningful user problem.
2. Build an end-to-end system that respects selected accessibility constraints.
3. Evaluate the system with representative users, routes, data, and workloads.
4. Demonstrate professional software-engineering and project-management practices.
5. Deliver a maintainable, documented system with an honest account of its limitations.

## 3. Project Success Criteria

The project will be considered successful when:

- A deployed end-to-end system supports the approved minimum viable product scope.
- All mandatory requirements have evidence of implementation and verification, or an approved exception.
- Every route in the validation set obeys its selected hard constraints.
- At least 85% of representative test participants can plan a route without assistance.
- At least 90% of evaluated field routes can be completed without encountering a known incompatible barrier.
- No critical WCAG 2.2 Level AA issue remains in the tested workflows.
- No known critical security vulnerability remains unresolved at release.
- The project repository, architecture, deployment, testing, and operating procedures are documented.
- Each team member can explain the system, project decisions, and their individual contribution.

## 4. Scope Management

### 4.1 Committed minimum viable product

The team commits to:

- Campus location search and selection
- Accessible route calculation
- Preferences for stairs, slopes, elevators, distance, and indoor/outdoor travel
- Visual and textual route instructions
- Warnings, explanations, and data-freshness information
- Authenticated closure management
- Public reporting of possible barriers and map errors
- Accessible mobile and desktop web interfaces
- Automated tests, monitoring, backup, and reproducible deployment

### 4.2 Explicit exclusions

The team does not commit to:

- Indoor GPS or real-time turn-by-turn positioning
- Native mobile applications
- Emergency evacuation guidance
- Automated detection of all physical barriers
- Additional campuses
- Personalized disability profiles
- Integration with production university systems unless separately approved

### 4.3 Scope priorities

The team will use the MoSCoW method:

| Priority | Meaning | Examples |
|---|---|---|
| Must | Required for a credible release | Constraint-aware routing, accessible route results, closure management, security controls |
| Should | Important but negotiable if risk threatens the release | Alternative routes, data-staleness warnings, administrative export |
| Could | Valuable if time and evidence support it | Saved preferences on the local device, route sharing, optional email notifications |
| Will not | Excluded from this release | Indoor positioning, native apps, additional campuses |

If schedule pressure occurs, the team will remove or defer lower-priority scope before reducing testing, security, accessibility, or documentation for mandatory capabilities.

## 5. Delivery Approach

The team will use an iterative and incremental process with two-week development iterations. Because the project lasts only one semester, discovery, requirements, data work, implementation, documentation, and evaluation must overlap. The team cannot wait for one discipline to finish completely before another begins. Each major phase still has an exit gate to prevent unresolved risk from quietly moving forward.

### 5.1 Working principles

- Build the riskiest assumptions early.
- Deliver a complete thin slice before adding breadth.
- Keep the main branch releasable.
- Demonstrate working software at the end of each iteration.
- Treat accessibility, security, privacy, and operations as continuing work.
- Use evidence to change scope and priorities.
- Record material decisions and requirement changes.
- Reach feature completeness by mid-November so evaluation is not postponed until the final week.

### 5.2 Iteration rhythm

Each two-week iteration will include:

1. **Planning:** Select an achievable iteration goal and backlog items.
2. **Implementation:** Design, code, test, review, and document the selected work.
3. **Stakeholder check:** Obtain feedback when the work affects users or sponsors.
4. **Demonstration:** Show completed, integrated behavior.
5. **Review:** Compare results with acceptance criteria and metrics.
6. **Retrospective:** Identify one or two concrete process improvements.

Incomplete work returns to the backlog and is not counted as completed.

## 6. Schedule and Milestones

Dates below are illustrative and should be aligned with the official course calendar. The final deadline is the first week of December, so the plan reserves the last two weeks primarily for evaluation, correction, documentation, and presentation rather than new feature development.

| Phase | Illustrative dates | Outcome | Exit gate |
|---|---|---|---|
| 1. Kickoff and framing | Aug. 31–Sep. 4, 2026 | Team agreement, initial problem, stakeholders, tools, and risks | Faculty accepts the initial project direction |
| 2. Discovery and requirements | Sep. 7–Sep. 18, 2026 | User evidence, goals, scope, success measures, initial requirements | Problem and MVP are valuable and testable |
| 3. Feasibility, prototype, and foundation | Sep. 14–Oct. 2, 2026 | Technical spikes, data assessment, prototype feedback, architecture, CI/CD | Highest risks are reduced and a test deployment works |
| 4. End-to-end walking skeleton | Oct. 5–Oct. 23, 2026 | Simplest complete route-planning workflow | Integrated origin-to-destination route works in staging |
| 5. MVP implementation | Oct. 26–Nov. 13, 2026 | Mandatory public and administrative workflows | Feature-complete MVP is deployed to staging |
| 6. Evaluation and hardening | Nov. 16–Nov. 25, 2026 | User, route, accessibility, security, reliability, and performance evidence | Release candidate satisfies quality gates or records exceptions |
| 7. Release and presentation | Nov. 30–Dec. 4, 2026 | Final release, documentation, presentation, handoff, and retrospective | Faculty and sponsor review final evidence |

### 6.1 Major milestones

| ID | Milestone | Target date | Evidence |
|----|---|---:|---|
| M.01 | Project charter approved | Sep. 4, 2026 | Approved charter and stakeholder list |
| M.02 | Problem validation complete | Sep. 18, 2026 | Interview synthesis and revised problem statement |
| M.03 | Requirements baseline approved | Sep. 25, 2026 | Versioned SRS and traceability starter |
| M.04 | Highest technical and data risks tested | Oct. 2, 2026 | Spike results, prototype feedback, and decisions |
| M.05 | Architecture and delivery pipeline ready | Oct. 9, 2026 | Architecture review and automated test deployment |
| M.06 | Walking skeleton demonstrated | Oct. 23, 2026 | Origin-to-destination route in staging |
| M.07 | MVP feature complete | Nov. 13, 2026 | Integrated mandatory workflows in staging |
| M.08 | Evaluation complete | Nov. 25, 2026 | Results for users, routes, security, accessibility, and performance |
| M.09 | Release candidate approved | Dec. 2, 2026 | Quality-gate checklist and accepted exceptions |
| M.10 | Final release and presentation | Dec. 4, 2026 | Tagged release, live demonstration, and final report |

## 7. Work Breakdown Structure

### 7.1 Project discovery and product work

- Identify sponsor and stakeholder representatives.
- Review existing campus maps and accessibility information.
- Conduct stakeholder and user interviews.
- Observe current route-planning behavior where appropriate.
- Define problem, outcomes, assumptions, and exclusions.
- Establish success metrics and evaluation methods.
- Prioritize the MVP and maintain the product backlog.

### 7.2 Requirements and design

- Write user stories and acceptance criteria.
- Define functional and nonfunctional requirements.
- Develop the route-data model and domain vocabulary.
- Create wireframes and accessible interaction prototypes.
- Build a threat model and privacy data-flow diagram.
- Document architecture decisions.
- Maintain requirements traceability.

### 7.3 Data acquisition and quality

- Identify permitted data sources.
- Define campus locations, paths, entrances, stairs, ramps, and elevators.
- Create import and validation tools.
- Establish verification status and freshness fields.
- Conduct targeted field verification.
- Create a known-route validation dataset.
- Document coverage gaps and limitations.

### 7.4 Route engine

- Represent the campus as a weighted graph.
- Implement hard-constraint filtering.
- Implement route scoring and preferences.
- Generate warnings and route explanations.
- Return useful failure results when no route is known.
- Create unit, property-based, and performance tests.

### 7.5 Public application

- Implement origin and destination selection.
- Implement accessibility preferences.
- Display map, text instructions, route summary, and warnings.
- Provide clear empty, loading, error, and no-route states.
- Implement the feedback workflow.
- Test keyboard, screen-reader, zoom, and mobile behavior.

### 7.6 Administrative application

- Integrate authentication.
- Implement authorization roles.
- Implement closure creation, editing, activation, and expiration.
- Implement feedback review.
- Implement audit logging and export.
- Test misuse, permission boundaries, and failure cases.

### 7.7 Platform and operations

- Establish repository conventions and branch protections.
- Create development and test environments.
- Configure continuous integration and deployment.
- Manage secrets securely.
- Add structured logs, metrics, error reporting, and uptime monitoring.
- Automate backups and demonstrate restoration.
- Document deployment, rollback, and incident procedures.

### 7.8 Evaluation and delivery

- Recruit representative evaluators.
- Complete usability and field-route studies.
- Perform accessibility audit.
- Run security tests and dependency review.
- Run load and performance tests.
- Resolve defects based on risk and severity.
- Prepare final report, demonstration, poster or presentation, and handoff.

## 8. Team Organization

This example assumes a four-person team. Roles identify primary responsibility, not exclusive ownership.

| Team member | Primary role | Principal responsibilities |
|---|---|---|
| Student A | Product and research lead | Stakeholder coordination, requirements, backlog, user research, evaluation |
| Student B | Technical and route-engine lead | Architecture, graph model, routing, technical decisions, performance |
| Student C | Experience and accessibility lead | Interaction design, frontend, accessibility testing, usability |
| Student D | Platform and quality lead | Backend integration, CI/CD, security, observability, test automation |

### 8.1 Shared responsibilities

Every team member will:

- Contribute production code and documentation.
- Review other team members' work.
- Participate in planning, demonstrations, and retrospectives.
- Maintain assigned backlog items.
- Understand the system beyond their primary role.
- Present evidence of individual contributions.

No critical component may be understood by only one team member.

### 8.2 Responsibility matrix

**R = Responsible, A = Accountable, C = Consulted, I = Informed**

| Activity | Product lead | Technical lead | Accessibility lead | Platform lead | Sponsor/faculty |
|---|:---:|:---:|:---:|:---:|:---:|
| Problem and scope | R | C | C | C | A |
| Requirements baseline | A/R | C | C | C | C |
| Architecture | C | A/R | C | R | I |
| Route engine | I | A/R | C | R | I |
| User experience | C | C | A/R | C | C |
| Accessibility evaluation | C | C | A/R | R | I |
| Security and operations | I | C | C | A/R | I |
| User evaluation | A/R | C | R | C | C |
| Release approval | C | C | C | R | A |
| Final presentation | R | R | R | R | I |

## 9. Communication Plan

| Communication | Participants | Frequency | Purpose | Record |
|---|---|---|---|---|
| Team stand-up | Student team | Twice weekly, 15 minutes | Progress, next work, blockers | Brief project-board update |
| Iteration planning | Student team | Every two weeks | Select goal and committed work | Iteration backlog |
| Technical design review | Relevant team members | As needed | Review consequential designs | Architecture decision record |
| Sponsor check-in | Product lead, sponsor, selected team members | Every two weeks | Validate needs, demo work, resolve questions | Meeting notes and decisions |
| Faculty status update | Entire team | As required by course | Report evidence, risks, and next milestone | Status report |
| Iteration demonstration | Team and invited stakeholders | Every two weeks | Demonstrate integrated completed work | Demo notes and feedback |
| Retrospective | Student team | Every two weeks | Improve teamwork and delivery | One or two tracked actions |

### 9.1 Communication expectations

- Decisions that affect scope, architecture, privacy, security, or evaluation must be recorded.
- A blocked task must be raised within one working day, not saved for the next formal meeting.
- Meeting notes must identify decisions, actions, owners, and due dates.
- Important project knowledge must be stored in the shared repository or approved project system.
- Chat messages are coordination tools, not the permanent record of a decision.

## 10. Work Management

### 10.1 Backlog hierarchy

The team will organize work as:

- **Outcome:** A user or project result the team wants to achieve
- **Epic:** A substantial coherent capability
- **User story or requirement:** Testable behavior or quality condition
- **Task:** A concrete piece of implementation or investigation work
- **Defect:** Behavior that fails an approved requirement or expectation
- **Spike:** Time-boxed investigation that reduces uncertainty

### 10.2 Work-item requirements

Before work begins, an ordinary backlog item should include:

- A clear title and reason for the work
- Owner or pair
- Related requirement or user story
- Acceptance criteria
- Dependencies and important risks
- Appropriate test or review expectations

### 10.3 Work-in-progress policy

- Each team member should have no more than one primary implementation item in progress.
- The team should finish and integrate work before starting lower-priority items.
- Reviews and blocked items take priority over starting new work.
- A large item that cannot finish within one iteration must be split into independently verifiable increments.

## 11. Definition of Ready

A backlog item is ready for implementation when:

- Its purpose and stakeholder value are understood.
- Acceptance criteria are testable.
- Relevant designs or data are available, or their creation is part of the item.
- Dependencies are known.
- Security, privacy, accessibility, and operational implications have been considered.
- The team believes the item can be completed within one iteration.

Research spikes may begin with uncertainty, but they must state the question, time limit, and expected decision or evidence.

## 12. Definition of Done

A backlog item is done only when, as applicable:

- Acceptance criteria pass.
- Code and configuration are committed to the shared repository.
- Automated tests have been added and pass.
- Another team member has reviewed the change.
- Security, privacy, accessibility, and failure cases have been addressed.
- User-facing and technical documentation are updated.
- Monitoring or logging is included for important production behavior.
- The change is integrated into the main branch.
- The change is deployed to the agreed environment.
- The product lead has accepted the result.

“Code complete” is not the same as done.

## 13. Quality Management Plan

### 13.1 Quality strategy

Quality will be built throughout development rather than deferred to a final testing phase. The team will use multiple forms of evidence because no single test technique covers all project risks.

| Quality area | Planned activities | Gate |
|---|---|---|
| Functional correctness | Unit, integration, end-to-end, and field-route tests | Mandatory workflows and constraint tests pass |
| Accessibility | Design review, automated checks, keyboard, zoom, contrast, and screen-reader tests | No unresolved critical issue in tested scope |
| Security | Threat model, code review, static analysis, dependency scan, authorization and input tests | No unresolved critical vulnerability |
| Privacy | Data inventory, minimization review, retention review, log inspection | Privacy requirements and notice verified |
| Performance | Route-engine benchmarks and API load tests | Approved percentile targets met |
| Reliability | Failure-mode tests, monitoring, backup and restore exercise | Recovery exercise succeeds |
| Usability | Prototype and MVP studies with representative users | Task and satisfaction evidence reviewed |
| Maintainability | Review, static analysis, documentation, setup test by another developer | Reproducible build and deployment demonstrated |

### 13.2 Defect priorities

| Severity | Meaning | Expected response |
|---|---|---|
| Critical | Safety risk, severe security exposure, data loss, or mandatory workflow unavailable | Stop affected release work and address immediately |
| High | Major requirement fails with no reasonable workaround | Resolve before release candidate |
| Medium | Requirement partially fails or has a usable workaround | Schedule based on risk and remaining capacity |
| Low | Minor issue with limited impact | Fix if justified or document as known limitation |

Severity describes impact. Backlog priority also considers likelihood, affected users, effort, and release timing.

## 14. Evaluation Plan

### 14.1 Product evaluation

The team will evaluate:

- Whether users can plan a route successfully
- Whether selected route constraints are obeyed
- Whether route explanations and warnings are understood
- Whether representative field routes are usable
- Whether administrative closure updates affect routing promptly
- Whether the application meets accessibility, performance, security, and reliability targets

### 14.2 Evaluation stages

| Stage | Timing | Participants or data | Purpose |
|---|---|---|---|
| Concept interviews | Sep. 7–18 | 4–6 relevant stakeholders/users | Validate problem and terminology |
| Prototype review | Sep. 21–Oct. 2 | 3–5 representative users | Correct the interaction before full implementation |
| Route-data validation | Oct. 5–Nov. 13 | Curated route set and targeted field observations | Check graph data and constraint behavior continuously |
| MVP usability and field test | Nov. 16–20 | 5–8 representative participants | Measure task success, route completion, and user understanding |
| Accessibility audit | Nov. 16–23 | Team plus qualified reviewers where available | Evaluate WCAG-related requirements |
| Technical evaluation | Nov. 16–25 | Automated workloads and security tests | Measure performance, reliability, recovery, and security |
| Release-candidate verification | Nov. 30–Dec. 2 | Regression suite and approved evaluation evidence | Confirm corrections and release readiness |

Participation involving people will follow applicable university research, privacy, accessibility, and consent requirements. The team will consult the instructor before recruiting or collecting personal data.

## 15. Technical Management

### 15.1 Repository practices

- Use one shared project repository or a documented multi-repository structure.
- Protect the main branch from direct unreviewed changes.
- Connect pull requests to backlog items and requirements when applicable.
- Require automated checks before merge.
- Use small, reviewable changes.
- Tag milestone and release versions.
- Keep generated artifacts and secrets out of source control.

### 15.2 Environments

| Environment | Purpose | Data policy |
|---|---|---|
| Local development | Individual and paired development | Synthetic or approved non-sensitive data |
| Continuous integration | Automated build and test | Ephemeral test data |
| Staging | Integrated evaluation and demonstrations | Sanitized or approved representative data |
| Production/pilot | Final release and pilot use | Minimum approved production data |

### 15.3 Architecture decisions

The team will create an architecture decision record when a choice:

- Has meaningful long-term consequences
- Introduces a major dependency
- Changes security, privacy, accessibility, or operating risk
- Is difficult to reverse
- Resolves a significant disagreement or uncertainty

Each record will state the context, considered options, decision, trade-offs, and consequences.

## 16. Risk Management

The risk register will be reviewed during iteration planning and before each milestone.

| ID | Risk | Probability | Impact | Early warning | Response | Owner |
|---|---|:---:|:---:|---|---|---|
| R.01 | Accessibility data is incomplete or inaccurate | High | High | Large number of unverified paths or conflicting records | Prioritize core routes, field-verify, expose freshness and uncertainty | Product lead |
| R.02 | Representative users are unavailable for evaluation | Medium | High | No recruitment commitments by September 18 | Work through Accessibility Services immediately; offer flexible methods | Product lead |
| R.03 | Route algorithm cannot satisfy required preferences efficiently | Medium | High | Technical spike exceeds performance target | Prototype early; simplify scoring; preserve mandatory constraints | Technical lead |
| R.04 | Scope expands into indoor positioning or real-time tracking | Medium | High | New stories require sensors or native apps | Enforce exclusions and change-control process | Entire team |
| R.05 | Third-party map service becomes unavailable or costly | Medium | Medium | Policy, quota, or pricing changes | Abstract provider; test fallback; monitor use | Platform lead |
| R.06 | Accessibility defects are found late | Medium | High | Prototype work proceeds without assistive-technology tests | Test components every iteration; involve users early | Accessibility lead |
| R.07 | Team member becomes unavailable | Medium | High | Work and knowledge concentrate with one person | Pair work, reviews, shared documentation, cross-training | Entire team |
| R.08 | Production deployment exposes sensitive or insecure functions | Low | High | Threat-model items remain open near release | Security gates, least privilege, staging tests, review | Platform lead |
| R.09 | One-semester schedule compresses evaluation | High | High | Walking skeleton slips past October 23 or MVP slips past November 13 | Freeze lower-priority features, reduce geographic coverage, and protect the final two weeks for evaluation | Product lead |
| R.10 | Users over-trust route accuracy | Medium | High | Testing shows warnings are overlooked | Improve risk communication; show sources, freshness, limits | Accessibility lead |

### 16.1 Risk scoring

Probability and impact will be rated Low, Medium, or High. A High-impact risk requires a named owner and response even when probability is Low. A risk that occurs becomes an issue and is tracked with an action, owner, and due date.

## 17. Change Management

A change request is required when proposed work materially affects approved scope, a mandatory requirement, schedule, budget, architecture, data collection, security, privacy, accessibility, or evaluation.

The change request must state:

- The requested change and its rationale
- The affected stakeholder and expected benefit
- Requirements and deliverables affected
- Schedule, technical, quality, and risk impact
- Work that will be removed or delayed, if any
- Recommendation and decision

The sponsor or faculty advisor approves changes to major outcomes and course deliverables. The team may reprioritize ordinary implementation tasks within the approved baseline.

## 18. Decision Management

Material decisions will be recorded in one of the following forms:

| Decision type | Record |
|---|---|
| Product scope or requirement | Requirements document and change log |
| Architecture or major technology | Architecture decision record |
| Project process | Project plan or retrospective action |
| Risk acceptance | Risk register with approving person |
| Release exception | Release checklist with justification and owner |

A decision is not complete until affected people can find and understand it.

## 19. Project Metrics

Metrics are indicators for learning and decision-making, not individual performance scores.

### 19.1 Delivery indicators

- Iteration goal achieved: yes/no, with explanation
- Work-item age and blocked time
- Milestone forecast and confidence
- Mandatory requirements implemented and verified
- Unplanned work and defect demand

### 19.2 Quality indicators

- Automated test results and important coverage gaps
- Open defects by severity and age
- Accessibility findings by severity
- Known vulnerability findings by severity
- Route validation pass rate
- Deployment success and rollback events
- Availability, latency, and error rate

### 19.3 Product indicators

- Route-planning task completion
- Median task time
- Route completion in field evaluation
- Frequency and type of no-route results
- User comprehension of warnings and limitations
- Feedback-report resolution time during the pilot

Commit counts, lines of code, and hours online will not be used as primary measures of individual productivity.

## 20. Status Reporting

A concise weekly status report will contain:

1. **Overall status:** Green, Yellow, or Red with a one-sentence explanation
2. **Completed evidence:** Demonstrable outcomes, not activity alone
3. **Next objective:** The most important outcome for the coming week
4. **Milestone forecast:** On track, at risk, or delayed
5. **Top risks and issues:** Changes, owners, and actions
6. **Decisions needed:** Decision, owner, and required date
7. **Metrics:** Only the small set needed to understand current project health

### Sample status summary

> **Yellow — The October 23 walking-skeleton milestone remains achievable, but two central paths lack verified slope data.** The team deployed origin/destination selection and completed a route-engine spike. During the next week, Student A and Student C will validate the two paths while Student B integrates hard-constraint filtering. If the data is not available by October 16, the pilot map will exclude those paths and display the coverage limitation.

## 21. Budget and Resources

### 21.1 Illustrative resource limits

| Resource | Limit or assumption |
|---|---|
| Hosting and managed services | Target: free academic tiers; maximum $200 with prior approval |
| Mapping data and tiles | Must permit educational pilot use and expected request volume |
| Test devices | Team laptops and available mobile devices; borrow additional assistive technology if possible |
| Participant incentives | Subject to faculty and university approval |
| Team capacity | Four students working within course expectations |

Any service that could generate variable charges must have budget alerts, documented limits, and a shutdown or degradation strategy.

## 22. Deliverables

| ID | Deliverable | Principal contents |
|----|---|---|
| D.01 | Project charter | Problem, stakeholders, goals, scope, team, initial risks |
| D.02 | Research summary | Methods, evidence, findings, limitations, product implications |
| D.03 | Requirements baseline | Stories, functional and quality requirements, acceptance criteria |
| D.04 | Architecture package | Context, containers/components, data model, threat model, decisions |
| D.05 | Project plan | Schedule, responsibilities, quality, risks, communication, change control |
| D.06 | Working system | Source, configuration, database changes, test suites, deployed environments |
| D.07 | Evaluation package | Protocols, approved data, results, analysis, limitations |
| D.08 | Operational documentation | Setup, deployment, monitoring, backup, recovery, incident and handoff guides |
| D.09 | Final report | Problem, solution, evidence, decisions, results, ethics, limits, future work |
| D.10 | Final presentation and demonstration | Coherent story, live system, technical depth, evaluation, reflection |
| D.11 | Team retrospective | Outcomes, process, individual contributions, lessons, recommended next steps |

## 23. Release Plan

### 23.1 Release stages

1. **Internal build:** Used only by the project team.
2. **Staging release:** Used continuously for integration, demonstrations, and structured testing.
3. **Evaluation release:** Feature-frozen by November 13 for formal user and technical evaluation.
4. **Release candidate:** Only critical fixes and approved documentation changes allowed.
5. **Final release:** Tagged, deployed, documented, and accompanied by known limitations by December 4.

### 23.2 Release readiness checklist

- Mandatory requirements have verification evidence.
- Required automated checks pass.
- No open critical defect or vulnerability remains.
- Data validation completes successfully.
- Accessibility audit is complete for core workflows.
- Performance targets are met under the documented workload.
- Monitoring and alerting are active.
- Backup and restoration have been demonstrated.
- Rollback procedure has been tested.
- User, administrator, and operational documentation are current.
- Known limitations and accepted exceptions are approved.
- The live demonstration has a tested fallback plan.

## 24. Contingency Plan

If the project falls materially behind schedule, the team will respond in this order:

1. Stop starting new optional work.
2. Complete and integrate work already in progress.
3. Remove Could requirements.
4. Defer Should requirements after reviewing stakeholder impact.
5. Reduce geographic coverage while preserving a valid end-to-end experience.
6. Replace unavailable external integrations with documented test doubles or manual workflows.
7. Request a formal baseline change if mandatory outcomes cannot be met.

The team will not hide schedule problems by silently eliminating evaluation, security, accessibility, testing, or documentation.

## 25. Project Closeout

Before closing the project, the team will:

- Confirm acceptance or document unresolved exceptions.
- Tag and archive the final release.
- Export and preserve approved project records.
- Remove unused credentials and revoke unnecessary access.
- Confirm ownership or shutdown of hosted resources.
- Transfer documentation and known issues to the sponsor or faculty advisor.
- Present evaluation results and known limitations.
- Complete team and individual retrospectives.
- Identify recommended future work without presenting it as completed scope.
- Record what future teams would need to reproduce or continue the project.

## 26. Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Project sponsor or product owner |  |  |  |
| Project team representative |  |  |  |
| Faculty advisor |  |  |  |

---

## Notes for Students

A useful project plan is a decision-making tool, not a promise that nothing will change. Your plan should be detailed enough to expose dependencies, risks, responsibilities, and evidence of progress, but simple enough that the team actually uses and updates it.

For your own project:

- Plan around outcomes and evidence, not only activities.
- Protect time for integration and evaluation.
- Give every significant risk and action an owner.
- Make scope exclusions explicit.
- Connect the schedule to requirements and deliverables.
- Update forecasts when evidence changes.
- Record important decisions and approved changes.
- Treat the final presentation as the communication of completed work, not the deadline for first integration.
