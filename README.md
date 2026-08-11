# Capping (CMPT475/76): Projects 2026

## Beyond Coding: Engineering Intelligent, Secure, and Reliable Systems

> From AI-assisted prototypes to production-ready solutions with measurable real-world value.

---

## The challenge

Artificial intelligence is changing how software is created, but producing code is only one part of solving a meaningful computing problem. Computer scientists must also understand users, evaluate technologies, design systems, work responsibly with data, protect against security threats, and deliver reliable solutions.

This year's Capping projects challenge you to design, implement, deploy, and evaluate a substantial computing system addressing a genuine organizational, community, scientific, or societal need.

Your project may involve artificial intelligence, cloud and enterprise computing, the Internet of Things, interactive experiences, or conventional software engineering. AI is encouraged when it creates demonstrable value, but it is not required and should not be added merely as a decorative feature.

The goal is not simply to show that your team can build an application. The goal is to show that your team can **own a problem and engineer a credible solution**.

## Why this theme?

The computing market increasingly rewards broad engineering ability rather than code production alone. Current projections from the U.S. Bureau of Labor Statistics anticipate strong growth in software development, data science, and information security, while narrower computer-programmer employment is projected to decline.

This theme therefore emphasizes the abilities that distinguish an effective computing professional:

- Defining the right problem before selecting a technology
- Designing and integrating complete systems
- Evaluating whether a solution actually works
- Building for security, privacy, accessibility, and reliability
- Communicating decisions to technical and nontechnical audiences
- Learning and adapting as tools change

## Project tracks

Projects may fit within one track or combine several.

### 1. AI-augmented products and agents

Build an AI-enabled system that improves a real workflow or supports a meaningful decision. Appropriate projects include domain-specific assistants, retrieval and knowledge systems, intelligent automation, multimodal tools, and human-in-the-loop agents.

AI projects must evaluate accuracy, reliability, failure modes, safety, latency, and cost. A generic chatbot interface is not, by itself, a sufficient project.

### 2. Data-intensive and decision systems

Create systems for data acquisition, quality management, real-time processing, analytics, forecasting, visualization, or decision support. Projects must connect data to a specific user decision or operational outcome; a collection of charts without an actionable purpose is not sufficient.

### 3. Cloud and enterprise engineering

Explore distributed applications, developer platforms, observability, deployment automation, reliability engineering, enterprise integration, resource management, or cost optimization. Projects should make architecture and operational trade-offs visible and measurable.

### 4. Internet of Things and edge computing

Connect software with physical environments through sensors, devices, networks, or edge intelligence. Projects must consider device security, intermittent connectivity, data handling, and failure in the physical world.

### 5. Human-centered and public-interest technology

Design technology for accessibility, education, healthcare, civic participation, sustainability, digital well-being, or community needs. Projects should be developed with—not merely for—the intended users whenever possible.

## What every project must demonstrate

Regardless of track or technology, every project must include the following.

### A real and evidenced problem

Identify the users or stakeholders, investigate their present situation, and provide evidence that the problem is worth solving. Avoid beginning with a favored technology and searching afterward for a reason to use it.

### A working end-to-end system

The final result must integrate its important components into a coherent, demonstrable system. A set of disconnected experiments, mockups, or notebook results is not a completed product.

### Technical depth

The work should present meaningful computer science or software-engineering challenges. Your team must explain the architecture, algorithms, data structures, integrations, and engineering trade-offs that matter to the solution.

### Measurable success criteria

Define success before final implementation. Depending on the project, useful measures might include task completion, prediction quality, response time, availability, resource consumption, security coverage, accessibility, usability, or user outcomes.

### Responsible engineering

Address security, privacy, accessibility, ethics, and potential misuse from the beginning of the project. These are design requirements, not optional observations to add at the end.

### Professional execution

Use version control, issue tracking, code review, testing, documentation, and reproducible build or deployment practices. The repository should allow another technically capable person to understand, run, and evaluate the work.

## Project standard

Your final submission should be closer to a small, credible production system than to a classroom demonstration. At minimum, it should include:

- A clearly defined stakeholder and problem
- Documented functional and nonfunctional requirements
- A justified system architecture
- A deployed or reproducibly deployable implementation
- Automated tests appropriate to the project's risks
- Security, privacy, accessibility, and ethical analysis
- Performance, reliability, and operating-cost evidence
- Evaluation with representative users, data, workloads, or threats
- Known limitations and a realistic path for future work
- Technical and user documentation
- A professional presentation and live demonstration

Not every project needs commercial-scale infrastructure. The expectation is that the team makes deliberate choices, validates important claims, and provides evidence proportional to the project's scope and risks.

## Using artificial intelligence

There are two different uses of AI in this course, and both require responsible practice.

### AI as part of the product

When an AI model is a component of the system, the team must:

- Explain why AI is appropriate for the problem
- Compare it with a simpler or non-AI baseline
- Document model and data dependencies
- Create a repeatable evaluation dataset or procedure
- Test important errors, hallucinations, bias, adversarial inputs, and unsafe outputs
- Provide human review or escalation where errors could cause meaningful harm
- Measure relevant quality, latency, and cost trade-offs
- Communicate limitations to users

The [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) and its [Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1) are useful starting points for this analysis.

### AI as a development tool

You may use AI-assisted development tools subject to the course academic-integrity policies. AI assistance does not transfer responsibility: the team remains accountable for every design decision, dependency, claim, and line of submitted code.

Teams must:

- Disclose which AI tools were used and for what purposes
- Review, test, and understand AI-generated material before including it
- Verify licenses, sources, security, and factual claims
- Avoid submitting confidential, private, or restricted data to external services
- Preserve evidence of the team's own reasoning and engineering process

If a team cannot explain or defend part of its submission, that work will not demonstrate mastery, regardless of how it was produced.

## Recommended project lifecycle

| Stage | Central question | Expected evidence |
|---|---|---|
| Problem discovery | Are we solving the right problem? | Stakeholders, research, current workflow, problem evidence |
| Proposal | Is the project valuable and feasible? | Scope, success metrics, risks, preliminary technical approach |
| Architecture | How should the system work? | Requirements, diagrams, data design, threat model, trade-offs |
| Technical proof | Can we resolve the greatest uncertainty? | Focused experiment or prototype addressing the highest risk |
| Minimum viable system | Does the complete workflow function? | Integrated implementation and initial deployment |
| Evaluation and hardening | Does it work well enough, safely enough? | Tests, user or data evaluation, security and performance results |
| Final release | Can others understand, use, and assess it? | Release, documentation, presentation, demonstration, retrospective |

Specific deadlines and submission instructions will be published in Brightspace.

## Initial proposal

The initial proposal should be concise and should answer:

1. Who experiences the problem?
2. What evidence shows that the problem is real and important?
3. How is the problem handled today?
4. What outcome will your system improve?
5. How will the team measure that improvement?
6. What makes the project technically substantial?
7. What is the smallest credible end-to-end version?
8. What are the greatest technical, data, security, ethical, or scheduling risks?
9. Who are the team members, and what initial responsibilities will they hold?

A proposal is not strengthened by listing more features. It is strengthened by a clearer problem, credible evidence, thoughtful constraints, and an achievable evaluation plan.

## Ideas that usually need further development

The following starting points are typically too shallow unless they are connected to a distinctive problem and substantial technical challenge:

- A generic chatbot connected to a model API
- A standard create/read/update/delete application
- A dashboard without a defined decision or action
- A clone of an existing commercial product
- A model comparison based only on headline accuracy
- An application with an AI feature added at the end
- A technically impressive demonstration without real users or evaluation

These technologies and formats are not prohibited. They simply do not constitute a strong Capping Project by themselves.

## How projects will be assessed

Assessment will consider the quality of the complete engineering effort, including:

- Problem understanding and stakeholder value
- Technical ambition and depth
- Architecture and implementation quality
- Evaluation and quality of evidence
- Security, privacy, accessibility, and responsible design
- Project management and teamwork
- Documentation and reproducibility
- Communication, presentation, and demonstration
- Individual understanding and contribution

Exact deliverables and grading weights will be provided with the corresponding assignments.

## Inspiration

Possible directions include:

- An evidence-grounded assistant for a specialized professional workflow
- A software supply-chain risk monitor for open-source projects
- A privacy-aware health or well-being support system
- An accessible campus navigation or event-discovery application
- A platform for measuring and reducing cloud cost or energy use
- An AI-assisted code-review system evaluated against real defects
- A secure IoT monitoring system for campus or community infrastructure
- A system that detects misleading media and communicates supporting evidence
- A digital twin or simulation for transportation, energy, or resource planning
- An interactive training environment for cybersecurity or emergency response
- A multiplayer or adaptive game with a substantive systems or AI challenge
- A developer tool that measurably improves testing, debugging, or deployment

Use these as prompts, not specifications. The strongest projects will emerge from direct investigation of a problem your team genuinely cares about.

## Market and professional references

- [U.S. Bureau of Labor Statistics: Software Developers, Quality Assurance Analysts, and Testers](https://www.bls.gov/ooh/computer-and-information-technology/software-developers.htm)
- [U.S. Bureau of Labor Statistics: Information Security Analysts](https://www.bls.gov/ooh/computer-and-information-technology/information-security-analysts.htm)
- [U.S. Bureau of Labor Statistics: Data Scientists](https://www.bls.gov/ooh/math/data-scientists.htm)
- [U.S. Bureau of Labor Statistics: Computer Programmers](https://www.bls.gov/ooh/computer-and-information-technology/computer-programmers.htm)
- [NIST Secure Software Development Framework](https://csrc.nist.gov/Projects/ssdf)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/)
- [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/)

## Final perspective

Tools will change during your career. The durable skill is the ability to investigate an unfamiliar problem, learn what is necessary, make defensible choices, and deliver a system that other people can trust.

Build something that demonstrates not only what you know, but how you think and what you can responsibly accomplish as a computing professional.

