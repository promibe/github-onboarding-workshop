# My Notes — Promise Ibediogwu

---

## Key Concepts I Learned

- AI security needs a defense-in-depth approach across three layers: the Traffic layer (Gateway), the Interaction layer (Guardrails), and the Platform layer (Defender for Cloud) — each one covers a risk the others don't.
- An AI Gateway (built on Azure API Management) acts as the perimeter for AI traffic — it handles authentication, enforces rate limits so no single app burns through the whole token quota, and audits who is doing what.
- Managed identities in Microsoft Entra ID are the recommended way to authenticate to AI services — moving away from static API keys removes the risk of a single leaked key compromising every application that shared it.
- Guardrails protect the interaction layer: Prompt Shields catch jailbreak/injection attempts, Content Filters classify harmful categories like hate or violence, and Block Lists catch specific sensitive terms (like project codenames or salary figures) that generic filters wouldn't know to flag.
- Groundedness detection checks whether a model's response is actually backed by the source data it was given, which helps cut down on hallucinated answers.
- Anomaly-based alerting (e.g. a 10x spike in token consumption, or activity outside business hours) only works once you've established a normal baseline first — you can't detect "unusual" without first knowing "usual."

---

## Lab / Hands-On Work

### What I did
I didn't do a personal hands-on for this session — I followed along as the mentor (Susan Onyekachi-Lawal) worked through the Azure API Management (APIM) demo live. What was demonstrated:

1. Deploying an AI model in Azure AI Foundry.
2. Retrieving the model's endpoint and API keys.
3. Enabling a System-Assigned Managed Identity on the APIM service.
4. Assigning the "Cognitive Services OpenAI User" role to the APIM service so it could securely authenticate to the AI backend without a stored key.
5. Configuring an OpenAPI spec file in APIM to define the traffic rules for the gateway.

### What happened / Result
The mentor successfully wired APIM up to the Azure AI Foundry model deployment using managed identity instead of an API key, showing how the gateway sits between consumers and the model to enforce authentication and traffic control from a single, centralized point.

### Challenges I faced
Since I observed rather than built this myself, the part I'll need to pay closer attention to when I redo it is the role assignment step — making sure the "Cognitive Services OpenAI User" role is scoped correctly to the right resource so the managed identity actually has permission to reach the backend.

---

## My Takeaways

The biggest lesson for me was "stop using shared API keys." It's such a simple statement but it reframes a lot of how I'd think about wiring up an AI app — a single shared key is a single point of failure, and managed identity removes that risk entirely by eliminating the key from the picture. I also found the three-layer mental model (Traffic / Interaction / Platform) genuinely useful — it gives me a checklist to run through instead of a vague sense of "is this AI app secure." And the point about baselining before alerting is a good general security habit, not just an AI-specific one.

---

## Questions I Still Have

- In a multi-team org, how do you keep the APIM-level rate limits fair across teams while still using a single centralized gateway, rather than each team fighting over the same token quota?
- How do Block Lists get maintained over time — is there a workflow for teams to request new sensitive terms be added, or does that sit entirely with the security team?

---

## Resources I Found Useful

- Session recording/summary notes on Implementing Security for AI (Part 2) — Cloud & AI Security Boot Camp 2026
- [AI gateway capabilities in Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/genai-gateway-capabilities) — overview of traffic mediation, managed identity auth, and prompt moderation at the gateway layer
- [Configure AI Gateway in API Management for Azure AI Foundry (Microsoft Learn module)](https://learn.microsoft.com/en-us/training/modules/implement-application-interface-security-management/5-configure-application-gateway-management) — closely matches this session's APIM + Foundry hands-on
- [Authenticate and authorize access to Azure OpenAI APIs using Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/api-management-authenticate-authorize-azure-openai) — step-by-step on enabling managed identity and assigning the Cognitive Services OpenAI User role
- [Implement generative AI guardrails with Azure AI Content Safety (Microsoft Learn module)](https://learn.microsoft.com/en-us/training/modules/moderate-content-detect-harm-azure-ai-content-safety/) — covers Prompt Shields, content filtering, and groundedness detection
- [What is Azure AI Content Safety?](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview) — reference for Prompt Shields, groundedness detection, and protected material detection
- [Defender for Cloud AI security posture management](https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-security-posture) — the platform-layer monitoring and posture tooling referenced in this session

---

*Submitted by: Promise Ibediogwu · https://github.com/promibe*