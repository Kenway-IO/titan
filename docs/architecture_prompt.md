Act as a Principal Enterprise Architect at Kenway Consulting. Your goal is to design a robust, event-driven integration architecture using the **TITAN Framework**.

**The Framework:**
1. **T - Trigger:** The event that initiates the process (Pulse).
2. **I - Ingest:** Gathering context and hydrating data (Context).
3. **T - Think:** The decision logic or AI reasoning layer (Intelligence).
4. **A - Act:** The deterministic state change in the target system (Muscle).
5. **N - Notify:** The resolution, receipt, or human-in-the-loop alert (Closure).

**Input Scenario:**
"[Insert Client Scenario Here, e.g., We need to automatically process vendor invoices received via email]"

**Your Output Requirements:**
Please generate a specific architecture design for this scenario.

**1. The TITAN Flow (5 Steps):**
For each step, specify:
* **Stage:** (Trigger/Ingest/Think/Act/Notify)
* **Label:** A 2-3 word summary of the step (e.g., "Match PO").
* **System:** The specific system or Azure service involved (e.g., "SAP S/4HANA", "Azure OpenAI").
* **Color Logic:**
    * Trigger: Navy (Source System)
    * Ingest: Blue (Data Layer)
    * Think: Purple (Intelligence/AI)
    * Act: Orange (Transactional System)
    * Notify: Green (Communication)

**2. The Tech Stack:**
List 3-4 specific Azure/Enterprise technologies required to build this (e.g., "Azure Event Grid", "Logic Apps", "Cosmos DB").

**3. Success Criteria:**
Define the specific condition that determines the loop is successfully closed (e.g., "Transaction ID write-back to Source").

**4. JSON Output (Optional):**
If possible, format the flow steps into a JSON array compatible with our frontend visualizer: `[{ id: 1, stage: "TRIGGER", label: "...", system: "..." }, ...]`
