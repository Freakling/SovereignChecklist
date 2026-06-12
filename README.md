# SovereignChecklist

Move from assumptions to facts.

A practical self-assessment for understanding sovereignty across platforms, products, and workloads.

Use this checklist with real teams, real systems, and real constraints.

---

## What this is

Sovereignty is often reduced to data residency. That is only part of the story.

In practice, sovereignty comes down to three things:

- Who is in control  
- Who can act, and under what conditions  
- What your platform depends on to keep running  

This repository provides a structured way to work through those questions.

[Markdown Checklist](/SovereignChecklist.md)

[Original Excel Checklist - NOT MAINTAINED!](/SovereignChecklist.xlsx)

---

## What it covers

The checklist deliberately goes beyond infrastructure and looks at the full value chain:

- Control plane and infrastructure  
- Identity and access  
- Data and cryptography  
- Network and data flow  
- Governance and policy  
- Logging and evidence  
- Software supply chain  
- Applications and AI workloads  
- Vendor and commercial dependencies  
- Organizational structure  
- Operational readiness  

---

## Why this exists

Control is rarely lost in obvious places.

It is lost in things like:

- Build pipelines that rely on external services  
- APIs you do not control  
- Licensing and subscription models  
- Identity systems you cannot fully govern  
- Vendor functionality you cannot verify  

If you do not account for the full supply-chain, control and reliability becomes an assumption.

The checkist can be used to control your cost vulnerabilities, there have been many instances where vendors change cost models which have significant impact on companies tech stack.

---

## How to use

Use the checklist while assessing systems or parts of systems in a workshop with platform or product teams.

For each question, assign one of:

- Fully controlled  
- Partially controlled  
- Not controlled  
- Unknown  

Anything that is not fully controlled is a dependency.

**Think in layers, not binary states**

A dependency is not just "good" or "bad".

Ask two additional questions for each one:

- How long can we tolerate losing it?
- Who carries the risk when it fails?

Losing something for six hours is a different scenario than losing it permanently.

**After first iteration**
Once you have gone through the full checklist:

1. Identify all:
   - Partially controlled
   - Not controlled
   - Unknown

2. Treat each as a dependency

3. Decide for each:
   - Accept  
   - Mitigate  
   - Eliminate  

Evaluate if each dependancy needs it's own checklist, for a full effect the checklist should be done for each system or vendor in your product supply chain.

---

## Example usage

### Example 1 – Platform review (first pass)

A platform team runs through the checklist at a high level.

Findings:
- Identity is well controlled  
- Infrastructure mostly controlled  
- CI/CD pipeline depends on an external service  
- AI workloads use external inference  

At this point, those are just dependencies.

Instead of stopping there, the team applies the next step:

> Evaluate if each dependency needs its own checklist

They select two dependencies for deeper analysis:
- CI/CD platform  
- AI inference service  

---

### Example 1.1 – Recursive assessment (CI/CD)

The team runs the checklist on the CI/CD platform.

New findings:
- Build agents are externally managed  
- Pipeline depends on license validation  
- Artifact storage not fully controlled  

They add two more variables:

- CI/CD outage tolerance: ~4 hours  
- Risk owner: External vendor  

Comments: Short outages are acceptable, permanent loss is not.  

_The team decides to keep the dependency, but introduces fallback deployment mechanisms._

Outcome:
- The dependency is accepted, but no longer unmanaged  
- Risk is understood in terms of time and ownership, not just control
---

### Example 1.2 – Recursive assessment (AI workload)

The same approach is applied to AI.

High-level finding:
- "AI depends on external inference"

After running the checklist on the AI component:

- Prompts leave the environment  
- Model updates are vendor-controlled  
- No disconnected mode available  
- No visibility into how inference is handled internally  

Outcome:
- AI is no longer treated as a black box  
- The team can now decide if this is acceptable for specific workloads  

---

### Example 2 – Value chain mapping

A more mature team maps the entire chain:

Product -> Platform -> CI/CD -> Identity -> Logging -> AI -> Vendors

For each major dependency, they ask:

> Should this have its own assessment?

They do not go infinitely deep. They stop when:
- The dependency is well understood  
- The risk is acceptable  
- Further analysis does not change decisions  

Outcome:
- The team builds a layered understanding of control and dependency  
- Hidden assumptions are replaced with explicit decisions  

---

### Example 3 – Fire drill applied recursively

The team performs a disconnection test.

Initial result:
- "Platform works, but some functions fail"

Instead of stopping there, they break it down:

- Deployments fail -> traced to CI/CD dependency  
- Monitoring degrades -> traced to external logging  
- Some tools stop working -> traced to license validation  

Each failure becomes its own assessment target.

Outcome:
- Fire drill results are turned into concrete improvements  
- Dependencies are validated, not assumed  

---

## Key takeaway

The checklist is not meant to be done once.

It should be applied:

- At the platform level  
- On critical dependencies  
- On vendor services  
- On specific workloads  

You are not building a perfect model.  
You are building a clearer understanding, layer by layer.

If a dependency matters, it deserves to be understood on its own terms.
``
---

## Guiding principles

- If it cannot be revoked, it is not fully controlled  
- If it cannot be proven, it is not accountable  
- If it has not been tested, it is not reliable  
- If it depends on trust or documentation, it is not fully verified  
- If functionality can be removed through licensing, it is a dependency  
- If you do not know, it is a risk  

---

## What you should get out of it

After using this checklist, you should be able to answer:

- What do we actually control?  
- What do we depend on?  
- What happens when those dependencies fail?  

If those are unclear, sovereignty has not been designed.

---

## Final note

You will always have dependencies.

The goal is not to remove them.  
The goal is to understand them well enough to make deliberate decisions.
``
