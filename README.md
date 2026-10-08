INX: The Decision Engine

The Challenge

Some decisions are easy. Others involve several competing factors.

You may have five possible choices, each with a different cost. One may be cheaper but slower. Another may be faster but use more resources. Another may be reliable but expensive. A fourth may perform well overall but fail an important constraint.

There is no single option that wins across every category.

Build a system that can make a defensible decision when objectives compete, and make the trade-offs behind that decision visible.

The core flow is:

OPTIONS
   ↓
OBJECTIVES
   ↓
CONSTRAINTS
   ↓
EVALUATION
   ↓
TRADE-OFFS
   ↓
RECOMMENDATION
   ↓
EXPLANATION

What to Build

Build a decision engine that evaluates multiple alternatives against competing objectives and recommends an option based on the user’s priorities and constraints.

The system should not simply return:

Option A is best.

It should help the user understand why the option is currently recommended and what would need to change for another option to become better.

1. Represent Multiple Alternatives

Your system must evaluate at least three possible choices.

For example:

Option A
Option B
Option C

Each option should have measurable characteristics relevant to the decision.

2. Define Competing Objectives

The decision must involve at least three meaningful criteria.

For example:

Cost
Speed
Reliability

The criteria should create genuine trade-offs.

A system where one option is always best across every criterion does not meaningfully test decision-making.

3. Allow Priorities to Change

A user must be able to change the importance of at least some objectives or constraints.

For example:

Cost         ████████
Speed        ████
Reliability  ██████████

Changing the priorities should have the potential to change the recommendation.

4. Evaluate the Alternatives

The system must have a defined method for comparing the available options.

Possible approaches include:

* Weighted scoring
* Optimization
* Constraint solving
* Simulation
* Heuristics
* Multi-objective optimization
* Other approaches chosen by the team

The method used must be documented.

5. Produce a Recommendation

The system should produce one of the following:

* A recommended option
* A ranked list
* A set of viable options

The output must follow the inputs and decision model. It must not be a hardcoded result.

6. Explain the Decision

The recommendation must be understandable to the user.

For example:

RECOMMENDATION
Option B
Why:
• Lowest total cost among viable options
• Meets the minimum reliability requirement
• Performs better than Option A under the current priority weights
Trade-off:
Option B is approximately 12% slower than Option A.

The exact explanation format is up to the team.

Decision Dependency

The system must demonstrate that the decision actually depends on the user’s priorities or constraints.

For example:

Scenario 1
Cost is highly important
        ↓
Recommendation → Option A

Then:

Scenario 2
Reliability is highly important
        ↓
Recommendation → Option C

The recommendation should change because the decision conditions changed, not because the application contains a hardcoded switch.

Constraints

No Hardcoded Winner

Do not implement logic such as:

if user chooses X:
    return Option A

The recommendation must emerge from the decision model.

Explain the Model

Document:

* What each criterion means
* How criteria are measured
* How alternatives are compared
* How constraints are applied
* How the final recommendation is produced

Reproducibility

Given the same inputs, the system should produce the same decision unless uncertainty or randomness is intentionally part of the model.

If randomness is used, document why.

Make Assumptions Visible

Real decisions contain assumptions.

Important assumptions should be visible rather than hidden inside the implementation.

Technology

There is no prescribed technology stack.

You may use:

* Mathematical models
* Optimization algorithms
* Constraint solvers
* Simulation
* Heuristics
* Machine learning
* LLMs
* Rules
* Statistical methods
* Hybrid approaches

AI is optional.

An LLM should not be used as a black box to decide which option is “best” without a defensible underlying decision model.

Evaluation

Decision Quality

Does the system produce sensible results from the inputs?

Trade-offs

Does it correctly handle competing objectives?

Flexibility

Does changing priorities or constraints actually affect the outcome?

Explainability

Can a user understand why an option was recommended?

Model Quality

Are the assumptions and scoring or optimization method reasonable?

Engineering

Is the implementation reliable, testable, and understandable?

Team Choices

The team decides:

* The scenario
* The alternatives
* The criteria
* The constraints
* The data model
* The evaluation method
* The optimization approach
* The interface
* The explanation mechanism
* The technology stack

There is no prescribed architecture.

Optional Enhancements

These features are optional:

* What-if analysis
* Sensitivity analysis
* Scenario comparison
* Pareto-front visualization
* Multi-objective optimization
* Uncertainty modelling
* Constraint relaxation
* Interactive trade-off visualization
* Decision reports
* Saving and comparing previous decisions

Do not add complexity simply to make the system look sophisticated.

Acceptance Criteria

* [ ]	At least three alternatives can be evaluated.
* [ ]	At least three competing criteria are represented.
* [ ]	Criteria have a defined meaning.
* [ ]	User priorities can be changed.
* [ ]	Constraints can affect the available choices.
* [ ]	Alternatives are evaluated using a documented method.
* [ ]	A recommendation or ranking is produced.
* [ ]	The recommendation is not hardcoded.
* [ ]	The system explains the major factors behind the result.
* [ ]	Changing a meaningful priority or constraint can change the recommendation.
* [ ]	The same inputs produce a reproducible result.
* [ ]	Important assumptions are documented.

Submission Requirements

The repository must contain enough information for another developer to understand and run the solution.

At minimum, include:

README.md
ARCHITECTURE.md
DECISIONS.md
TESTING.md

ARCHITECTURE.md

Document:

* System components
* Data model
* Decision pipeline
* Evaluation or optimization method
* Constraint handling
* Recommendation generation
* Interface

Include an architecture diagram.

DECISIONS.md

Document important decisions and trade-offs.

For example:

* Why these criteria were selected
* Why this scoring or optimization approach was selected
* How different units are normalized
* How constraints are applied
* What alternatives were considered

TESTING.md

Document:

* Normal decision cases
* Priority-change cases
* Constraint-change cases
* Boundary cases
* Invalid inputs
* Cases where the recommendation should remain unchanged
* Cases where the recommendation should change

Demo Expectations

The demonstration should make the decision model visible.

A recommended flow is:

1. Introduce the decision scenario
        ↓
2. Show available alternatives
        ↓
3. Show the criteria
        ↓
4. Set initial priorities
        ↓
5. Generate recommendation
        ↓
6. Explain the result
        ↓
7. Change an important priority
        ↓
8. Generate the new recommendation
        ↓
9. Change a constraint
        ↓
10. Show the effect
        ↓
11. Explain the model
        ↓
12. Defend the approach

The judges should be able to see that the system is actually making a decision rather than displaying a predetermined answer.

Event-Day Challenge

During evaluation, judges may change one of the major decision conditions.

For example:

"Cost is now twice as important."

or:

"The maximum acceptable delivery time is now 48 hours."

The system should respond according to its decision model.

You should be able to explain:

1. What changed.
2. Which alternatives were affected.
3. Why the recommendation changed or remained the same.
4. What trade-off the new decision represents.

Rules

* Build your own solution.
* AI-assisted development is allowed.
* Public libraries and tools are allowed.
* Do not depend on an ARC-owned backend or private dataset.
* Do not commit private credentials.
* Be prepared to explain the decision model.
* Do not claim mathematical or optimization guarantees that your implementation does not provide.
* Core requirements take priority over optional features.

Final Checklist

Before submission:

* [ ]	Scenario is clearly defined.
* [ ]	At least three alternatives exist.
* [ ]	At least three competing criteria exist.
* [ ]	Criteria are documented.
* [ ]	Priorities can be changed.
* [ ]	Constraints can be changed or applied.
* [ ]	Decision method is documented.
* [ ]	Recommendation is generated from the model.
* [ ]	Recommendation is not hardcoded.
* [ ]	Explanation is provided.
* [ ]	Priority changes have been tested.
* [ ]	Constraint changes have been tested.
* [ ]	Important assumptions are documented.
* [ ]	Edge cases have been tested.
* [ ]	No secrets are committed.
* [ ]	Architecture is documented.
* [ ]	Technical decisions are documented.
* [ ]	Testing is documented.
* [ ]	Demo is ready.

INNOVEX|ARC Club