---
name: add-titan-usecase
description: Interactive wizard to add a new use-case to the TITAN inventory
tags: [titan, inventory, workflow]
---

# Add TITAN Use-Case

I'll guide you through adding a new workflow to the TITAN Discovery Inventory. I'll ask questions for each stage of the framework.

## Process

I will collect information in this order:

### Basic Information
1. **Unique ID**: A short, memorable identifier (e.g., "returns", "invoice", "onboard")
2. **Title**: The name of this workflow opportunity
3. **Impact**: Annual value (e.g., "$200k/yr") or "High Risk" for critical processes
4. **Description**: 1-2 sentence overview of what this workflow does

### TITAN Framework Stages

For each of the 5 stages (Trigger → Ingest → Think → Act → Notify), I'll ask:

#### TRIGGER Stage
- **Label**: What event initiates this? (e.g., "Order Placed", "Email Received", "Contract Signed")
- **System**: Source system that generates the trigger (e.g., "Salesforce", "Exchange Online", "SAP S/4HANA")

#### INGEST Stage
- **Label**: What data are we gathering? (e.g., "Fetch Profile", "Parse PDF", "Get Roles")
- **System**: Where does this context come from? (e.g., "Snowflake", "Azure Blob Storage", "Data Lake")

#### THINK Stage
- **Label**: What decision/intelligence is applied? (e.g., "Fraud Check", "Match PO", "Optimize Allocation")
- **System**: What makes the decision? (e.g., "Azure OpenAI (GPT-4)", "Azure ML", "Business Rules Engine")

#### ACT Stage
- **Label**: What action is taken? (e.g., "Issue Refund", "Post Invoice", "Create User")
- **System**: Target system where the change happens (e.g., "Shopify Admin API", "SAP BAPI", "Entra ID")

#### NOTIFY Stage
- **Label**: How is completion confirmed? (e.g., "Email Customer", "Update Portal", "Alert Team")
- **System**: Notification channel (e.g., "SendGrid", "Microsoft Teams", "Twilio")

### Additional Details
7. **Tech Stack**: 3-5 key technologies for implementation (e.g., "Azure Event Grid", "Logic Apps", "Azure OpenAI")
8. **Success Criteria**: What specific proof validates this workflow succeeded? Include technical details like field updates, document IDs, status codes.

## Icon Mapping

I will automatically assign the standard TITAN icons:
- **Trigger**: "Zap"
- **Ingest**: "Database"
- **Think**: "BrainCircuit"
- **Act**: "Activity"
- **Notify**: "CheckCircle"

## Color Scheme

I will automatically assign the standard TITAN colors:
- **Trigger**: bg-kenway-navy
- **Ingest**: bg-kenway-blue
- **Think**: bg-purple-600 (with highlight: true)
- **Act**: bg-orange-500
- **Notify**: bg-green-600

---

Once I collect all information, I will:
1. Show you a preview of the JSON structure
2. Ask for your confirmation
3. Add it to `assets/inventory.json`
4. Confirm the addition

Let's begin! I'll ask you questions one at a time to keep this organized.
