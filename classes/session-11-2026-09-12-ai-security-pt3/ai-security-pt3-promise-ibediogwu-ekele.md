# My Notes — Promise Ibediogwu

---

## Key Concepts I Learned

- AI security needs to be applied across four control planes, not just one: Workloads (infrastructure/apps), Agents (governance/permissions), Data (posture/sensitivity), and Operations (monitoring/incident response) — each catches a different class of risk.
- The real risk with AI usually isn't the model itself, it's the access we give it — if an agent can reach sensitive data it shouldn't, the model will faithfully expose it when asked.
- Copilot's grounding process follows five steps: Prompt → Search → Trim → Reason → Answer. The "Trim" step is the critical security checkpoint — it strips out any content the requesting user isn't personally authorized to see, before the model ever reasons over it.
- AI agents should be managed like digital employees — with a defined role, registration, a scoped set of permissions, and a full lifecycle from onboarding to retirement (an agent nobody retires becomes the AI equivalent of an orphaned user account).
- New attack surfaces specific to AI include prompt injection, tool misuse, identity abuse, memory poisoning (bad data corrupting future outputs), data oversharing, and "agent sprawl" — untracked, forgotten agents accumulating risk in the background.
- Data classification is foundational: if the underlying data in an organization isn't classified, AI security tooling has nothing to enforce boundaries against.

---

## Lab / Hands-On Work

### What I did
I didn't do a personal hands-on for this session — I followed along as the speaker (Faruq Damilola Bakare) walked through the demos live. What was demonstrated:

1. The Agent 365 dashboard — viewing agent risk levels, permissions, and activity metrics, and how an admin can block a specific agent showing suspicious behavior.
2. Security Copilot investigating a complex, multi-stage security incident — showing how it can automatically summarize the incident to cut down the time a SOC analyst would need to investigate manually.

### What happened / Result
The Agent 365 walkthrough showed how agents across an org can be tracked in a single registry with visible risk scores, rather than each team's agents existing invisibly outside any central oversight. The Security Copilot demo showed a multi-stage incident being condensed into a readable summary far faster than manual triage would allow.

### Challenges I faced
Since I observed rather than operated these tools myself, the part I'd want to get hands-on with directly is actually reading and interpreting an agent's "risk level" in Agent 365 — understanding what signals feed into that score rather than just seeing the final number on screen.

---

## My Takeaways

The single line that reframed things for me was: "AI isn't the risk — the access we give it is." That's a much more actionable way to think about security than a vague fear of AI itself; it points straight at permissions and data classification as the actual levers to pull. The "Trim" step in the Copilot data flow also clicked for me — it explains very concretely why Copilot can be safely rolled out even in an org with sensitive data, as long as the underlying document permissions are correct in the first place. And the "digital employee" framing for agents — onboarding, scope, retirement — gives a really practical checklist for thinking about governance instead of treating agents as a black box.

---

## Questions I Still Have


- In practice, how do you catch "agent sprawl" early — is there a recommended review cadence for auditing ownerless or inactive agents in Agent 365, or is it purely reactive?
- For an org that hasn't done thorough data classification yet, what's the realistic starting point — do you classify data first and then deploy AI, or can DSPM help you discover and classify as you go?

---

## Resources I Found Useful

- Session recording/summary notes on Implementing Security for AI (Part 3) — Cloud & AI Security Boot Camp 2026
- [Overview of Microsoft Agent 365](https://learn.microsoft.com/en-us/microsoft-agent-365/overview) — the three pillars (observe, govern, secure) behind the dashboard demonstrated in this session
- [Explore Microsoft Agent 365 (Microsoft Learn training path)](https://learn.microsoft.com/en-us/training/paths/agent-365-solutions/) — modules on monitoring, managing, and governing agents at scale
- [Govern and secure AI agents across the organization](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/governance-security-across-organization) — governance baseline and lifecycle guidance referenced by the "digital employee" analogy
- [What is Microsoft Copilot for Security?](https://learn.microsoft.com/en-us/security-copilot/microsoft-security-copilot?view=o365-worldwide) — how grounding, plugins, and the LLM pipeline work together for incident investigation
- [Defender for Cloud AI security posture management](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-security-posture) — workload-plane discovery and threat detection for AI services

---

*Submitted by: Promise Ibediogwu · https://github.com/promibe*