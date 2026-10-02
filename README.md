# Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

## Project Overview

This project is a Salesforce-based customer support ticket intelligence system built using Agentforce and Salesforce Flow.

The system retrieves the latest support ticket for a customer account, analyzes the ticket description using predefined priority rules, classifies the ticket as High, Medium, or Low priority, and provides the appropriate support assignment.

For High-priority tickets, the Salesforce Flow creates an urgent ticket-handling task.

## Technology Stack

- Salesforce
- Agentforce
- Salesforce Flow
- Salesforce Custom Objects
- GitHub

## Main Components

### Custom Object

**Support Ticket Intelligence**

API Name:

`Support_Ticket_Intelligence__c`

The object stores customer support ticket information including:

- Customer Account
- Contact
- Issue Type
- Description
- Priority Level
- Status
- Created Date
- Assigned To
- SLA Breach Risk
- Resolution Time

## Agentforce

Agent:

**NM Support Agent**

Subagent:

**Support Ticket Priority Analysis**

Agent Action:

**Analyze Support Ticket Priority**

The Agentforce action accepts the customer Account Name and invokes the Salesforce Flow.

## Automation Flow

Flow:

`Support_Ticket_Intelligence`

The Flow:

1. Retrieves the customer Account.
2. Retrieves the latest support ticket.
3. Checks whether a ticket exists.
4. Analyzes the ticket description.
5. Determines High, Medium, or Low priority.
6. Creates an urgent task for High-priority tickets.
7. Determines the appropriate support assignment.
8. Returns the result to Agentforce.

## Priority Rules

### High Priority

Triggered by keywords such as:

- urgent
- not working
- failure

### Medium Priority

Triggered by keywords such as:

- issue
- slow
- delay

### Low Priority

Tickets that do not match the High or Medium keyword rules are classified as Low.

## Testing

The implementation was tested with:

- High-priority ticket
- Medium-priority ticket
- Low-priority ticket
- Missing Account Name
- No Support Ticket

The runtime tests were completed successfully for the documented scenarios.

## Documentation

The complete project implementation report is included in this repository.

## Project Structure

```text
force-app/
└── main/
    └── default/
        ├── aiAuthoringBundles/
        ├── flows/
        ├── layouts/
        ├── objects/
        └── permissionsets/

config/
├── project-scratch-def.json
└── ...

sfdx-project.json
README.md
