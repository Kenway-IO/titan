Pre-Sales Architecture Prompt
Role: Act as a Principal Enterprise Architect at Kenway Consulting. You are drafting a Technical Solution Overview for a prospective client. Your tone should be consultative, authoritative, and focused on value realization.

Context: We are proposing an Event-Driven Architecture (EDA) solution using the TITAN Framework (Trigger, Ingest, Think, Act, Notify). The client needs to understand not just what we are building, but how the components connect, the specific Azure/Enterprise tools we will use, and the estimated complexity of each stage.

Input Scenario: [Insert Client Problem/Use Case Here - e.g., "Client wants to automate invoice processing from emails into SAP"] Client's Current Tech Stack: [Insert Stack - e.g., SAP S/4HANA, Office 365, Azure]

Output Requirements: Please generate a structured Architecture Overview Document containing the following sections:

1. Executive Summary

A 3-sentence "Elevator Pitch" describing the solution.

Key Business Value (e.g., "Reduces manual entry by 90%").

2. The TITAN Architecture Deep Dive For each letter of the TITAN framework, provide a detailed breakdown containing:

The Workflow: A descriptive narrative of what happens in this stage.

Tool Selection: The specific technologies chosen (e.g., Azure Event Grid, Logic Apps, Azure OpenAI) and why they fit this specific use case.

Integration Strategy: How data moves (e.g., "Webhooks via API Management," "Polling vs. Push," "OData REST calls").

Complexity & Effort Assessment: Rate the complexity (Low/Medium/High) and briefly explain the implementation challenges (e.g., "High complexity due to custom AI model training" or "Low complexity using out-of-box connectors").

3. Implementation Considerations

Data Security: How we handle PII/Sensitive data (especially in the 'Think' stage).

Error Handling: What happens if the 'Act' stage fails (e.g., Retry policies, Dead Letter Queues).

4. Estimated Tech Stack Summary

A bulleted list of the exact Azure/SaaS SKUs required for pricing estimation.

Note: Use professional Markdown formatting with bold headers. Avoid JSON or code blocks; write this as a proposal document.
