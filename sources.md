# RackHead Security Research Sources

This source list is a launch baseline, not a final literature review. It prioritizes authoritative frameworks, current agent-security guidance, practical incident writeups, and open-source tools that RackHead can cite without pretending to be a large lab.

## Key takeaways

- Agent security is shifting from "what the model says" to "what the system can do": tools, permissions, memory, retrieval, and autonomous workflows.
- Prompt injection remains a core primitive, especially indirect injection through web pages, documents, email, chat, tool descriptions, and RAG corpora.
- MCP and agent skills create supply-chain and confused-deputy risks because tool metadata and tool outputs become instructions in the model context.
- Small open-source value is strongest in practical checklists, threat models, safe examples, workflow review templates, and lightweight evaluators.
- Avoid crowded hype: generic AI news, unsourced claims, jailbreak spectacle, and "one guardrail solves prompt injection" narratives.

## Sources

### OWASP Top 10 for LLM Applications 2025

- URL: https://genai.owasp.org/llm-top-10/
- Organization: OWASP Gen AI Security Project
- Date: 2025 edition
- Why it matters: Baseline risk taxonomy for LLM apps covering prompt injection, sensitive information disclosure, supply chain, data/model poisoning, excessive agency, vector weaknesses, misinformation, and unbounded consumption.
- RackHead use: Map checklists and research notes to recognized LLM risk categories.

### OWASP LLM01:2025 Prompt Injection

- URL: https://genai.owasp.org/llmrisk/llm01-prompt-injection/
- Organization: OWASP Gen AI Security Project
- Date: 2025-04-17
- Why it matters: Defines direct and indirect prompt injection and emphasizes that RAG and fine-tuning do not fully mitigate the issue.
- RackHead use: Foundation for safe prompt-injection examples and defensive patterns.

### OWASP Agentic AI - Threats and Mitigations

- URL: https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations
- Organization: OWASP Agentic Security Initiative
- Date: 2025-04-28
- Why it matters: Threat-model-based reference for emerging agentic risks.
- RackHead use: Source for agent threat model templates and roadmap.

### OWASP Top 10 for Agentic Applications 2026

- URL: https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/
- Organization: OWASP Gen AI Security Project
- Date: 2025-12-09
- Why it matters: Peer-reviewed operational framework for autonomous and agentic AI systems.
- RackHead use: Use ASI categories as a mapping layer for issues, checklists, and evaluator rules.

### MITRE ATLAS

- URL: https://atlas.mitre.org/
- Organization: MITRE
- Date: living knowledge base
- Why it matters: Tracks adversary tactics and techniques against AI systems, including agentic AI, tool poisoning, context poisoning, exfiltration, and supply-chain techniques.
- RackHead use: Map threat models to adversary behavior and detection ideas.

### NIST AI Risk Management Framework

- URL: https://www.nist.gov/itl/ai-risk-management-framework
- Organization: NIST
- Date: AI RMF 1.0 released 2023; GenAI Profile released 2024; ongoing revisions
- Why it matters: Governance-oriented framework for managing AI trustworthiness and risk.
- RackHead use: Keep project language aligned with Map, Measure, Manage, and Govern practices.

### Google Secure AI Framework (SAIF)

- URL: https://safety.google/intl/en_in/safety/saif
- Organization: Google
- Date: living framework
- Why it matters: Practical industry framing for secure-by-default AI development, monitoring, and response.
- RackHead use: Source for secure lifecycle and monitoring principles.

### Anthropic Model Context Protocol

- URL: https://www.anthropic.com/news/model-context-protocol
- Organization: Anthropic
- Date: 2024-11-25
- Why it matters: MCP became a major standard for connecting AI assistants to external systems and data.
- RackHead use: Explain why tool interfaces are now security boundaries.

### Invariant Labs MCP Tool Poisoning Attacks

- URL: https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks
- Organization: Invariant Labs
- Date: 2025-04-01
- Why it matters: Demonstrates tool poisoning and tool shadowing risks in MCP-style agent systems.
- RackHead use: Defensive checklist for tool descriptions, trust boundaries, and server provenance.

### Snyk Agent Scan

- URL: https://github.com/snyk/agent-scan
- Organization: Snyk
- Date: active GitHub project
- Why it matters: Open-source scanner for agent components, MCP servers, and skills.
- RackHead use: Competitive/complementary reference for agent-workflow-evaluator scope.

### Promptfoo / PyRIT / Garak ecosystem

- URLs: https://www.promptfoo.dev/ , https://github.com/Azure/PyRIT , https://github.com/NVIDIA/garak
- Organizations: Promptfoo/OpenAI, Microsoft, NVIDIA
- Date: active projects
- Why it matters: Current open-source stack for LLM red teaming, evals, and vulnerability probing.
- RackHead use: Do not duplicate mature scanners; focus on workflow review, templates, and practical agent-specific design checks.

### Prompt Injection attack against LLM-integrated Applications

- URL: https://arxiv.org/abs/2306.05499
- Authors: Liu et al.
- Date: 2023-06-08
- Why it matters: Early systematic work on prompt injection against real LLM-integrated applications.
- RackHead use: Background reading for explaining prompt injection beyond "weird prompts."

### Prompt injection attacks on vision-language models in oncology

- URL: https://www.nature.com/articles/s41467-024-55631-x
- Organization: Nature Communications
- Date: 2025-02-01
- Why it matters: Shows prompt injection is modality-agnostic and can affect high-stakes medical VLM settings.
- RackHead use: Keep examples safe and emphasize domain-specific risk.

### EchoLeak / Microsoft 365 Copilot reports

- URLs: https://www.aim.security/lp/aim-labs-echoleak-blogpost , https://www.rescana.com/post/cve-2025-32711-zero-click-echoleak-vulnerability-in-microsoft-365-copilot-enables-stealth-data-exfiltration-via-prompt-i
- Authors: Aim Security and secondary analysis
- Date: 2025/2026 reporting
- Why it matters: Widely discussed zero-click indirect prompt injection/data exfiltration case in enterprise RAG assistant context.
- RackHead use: Incident note with careful source checking and no operational exploit reproduction.

### Slack AI indirect prompt injection reports

- URL: https://www.promptarmor.com/resources/data-exfiltration-from-slack-ai-via-indirect-prompt-injection
- Organization: PromptArmor
- Date: 2024/2026 reporting
- Why it matters: Shows cross-channel RAG poisoning and private-data exposure risk in workplace assistants.
- RackHead use: Explain retrieval trust boundaries and safe incident lessons.
