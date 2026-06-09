# Sovereign Platform / Product Checklist

Use this together with your team.

For each question, assign:
- Fully controlled  
- Partially controlled  
- Not controlled  
- Unknown  

Use the comments column to capture context, assumptions, and decisions.

---

## 1. Control plane and infrastructure dependency

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Can the platform operate without connectivity to a public control plane? | | |
| Can infrastructure be deployed, updated, and managed locally? | | |
| Do you depend on external services for core runtime functionality? | | |
| Can the environment be operated under full network isolation? | | |
| Are platform updates under your control, or forced by a provider? | | |
| Is the control plane fully observable and auditable? | | |
| Are there hidden vendor-managed operational layers? | | |
| Can core functionality be restricted or disabled by the provider? | | |

---

## 2. Identity and privileged access

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Do you fully control your identity provider? | | |
| Can privileged access be revoked immediately and globally? | | |
| Are privileged roles time-bound and approval-based? | | |
| Are there any standing admin privileges? | | |
| Can any identity escalate to full control across platform and data? | | |

---

## 3. Data control and cryptography

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Who owns and controls encryption keys? | | |
| Can you rotate, revoke, or destroy keys independently? | | |
| Does data remain within your defined boundary? | | |
| Can data be exported without governance? | | |
| Are backups fully under your control? | | |
| Can key handling be independently verified? | | |
| Are there vendor override or recovery mechanisms? | | |
| Do you rely on vendor guarantees for key isolation? | | |

---

## 4. Network and data flow control

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Can you fully control outbound traffic? | | |
| Are all ingress paths governed and auditable? | | |
| Can services communicate outside approved boundaries? | | |
| Is lateral movement restricted? | | |
| Can data leave through unmanaged channels? | | |

---

## 5. Governance and policy enforcement

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Are policies enforced as deny-by-default? | | |
| Can non-compliant resources be deployed? | | |
| Are exceptions time-bound and audited? | | |
| Is governance technically enforced or process-based? | | |
| Can governance operate without external services? | | |

---

## 6. Observability, logging, and evidence

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Are all actions attributable? | | |
| Are logs stored within your boundary? | | |
| Can logs be tampered with? | | |
| Can you reconstruct events independently? | | |
| Are boundary violations actively monitored? | | |

---

## 7. Software supply chain and dependencies

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Can you build and release software without external services? | | |
| Are pipelines, agents, and artifacts under your control? | | |
| Do you rely on external package repositories? | | |
| Are licenses gating core functionality? | | |
| Can builds be reproduced independently? | | |
| Does deployment rely on license validation? | | |
| Are development tools fully under your control? | | |
| Can features be disabled through subscription changes? | | |

---

## 8. Application and runtime dependencies

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Do applications rely on external APIs or SaaS services? | | |
| Can workloads run if those services are unavailable? | | |
| Are AI models and inference controlled locally? | | |
| Is configuration dependent on external systems? | | |
| Can workloads degrade gracefully without dependencies? | | |
| Are runtime features tied to license entitlements? | | |
| Can functionality degrade due to vendor decisions? | | |

---

## 9. AI and data processing control

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Where do models run? | | |
| Do prompts or inference data leave the environment? | | |
| Can models be operated locally? | | |
| Do you depend on external inference endpoints? | | |
| Can AI run in fully disconnected mode? | | |

---

## 10. Operational readiness and fire drills

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Have you tested full disconnection? | | |
| Can teams operate without cloud access? | | |
| Are procedures documented and rehearsed? | | |
| Can incidents be handled without vendor involvement? | | |
| Do you know what breaks when dependencies fail? | | |
| Have you tested licensing or subscription failures? | | |
| Do you know where vendor validation is required? | | |

---

## 11. Vendor and commercial dependency

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Can functionality be removed through licensing changes? | | |
| Do you depend on subscription validation at runtime? | | |
| Can vendors control feature availability? | | |
| Do you have exit strategies? | | |
| Can services be replaced without redesign? | | |
| Do you understand upstream dependencies? | | |
| Have you mapped the full value chain? | | |

---

## 12. Organizational control and separation of duties

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Are responsibilities clearly separated (platform, security, keys)? | | |
| Can any team override controls independently? | | |
| Are toxic combinations prevented? | | |
| Is staffing sufficient to maintain separation of duties? | | |
| Are high-impact actions audited and reviewed? | | |

---

## 13. Vendor transparency and platform insight

| Question | Status | Comments / Actions |
|----------|--------|-------------------|
| Do you have visibility into how the platform operates internally? | | |
| Can critical controls be independently verified? | | |
| Do you rely on documentation or trust for key controls? | | |
| Can vendor operations be audited or validated? | | |
| Are there privileged access paths you cannot govern? | | |

---

## Notes

- Treat every "Partially controlled", "Not controlled", or "Unknown" as a dependency  
- Evaluate whether that dependency should have its own checklist  
- Go deeper where it matters, stop where additional detail does not change decisions  

---

## Key signals

- If it cannot be revoked, it is not controlled  
- If it cannot be proven, it is not accountable  
- If it has not been tested, it is not reliable  
- If it depends on licensing or subscriptions, it is a dependency  
- If you do not know, it is a risk  

---

## Final step

List your dependencies and decide:

- Accept  
- Mitigate  
- Eliminate  
