# AI Customer Support Agent + RAG

An AI-powered customer support automation system built with n8n, Google Gemini, RAG, PostgreSQL, and Gmail.

The system receives customer support requests through a webhook, validates the request, uses an AI support agent with a knowledge base to analyze and respond to the customer, stores customer and ticket information in PostgreSQL, sends support notifications, and automatically escalates sensitive or high-priority issues to human support.

## Architecture

Customer Request
↓
Receive Customer Request
↓
Prepare Customer Ticket
↓
Validate Customer Request
↓
AI Support Agent
↓
Parse AI Support Result
↓
Upsert Customer CRM
↓
Save Support Ticket
↓
Send Support Notification
↓
Check Human Escalation
↙ ↘
FALSE TRUE
↓ ↓
Return Send Escalation
Response Alert
↓
Return Support Response

## RAG Architecture

Support Knowledge Base
↓
Build Support Knowledge Base
↓
Gemini KB Embeddings

AI Support Agent
↓
Search Support Knowledge Base
↓
Gemini RAG Embeddings
↓
Relevant Support Information

The AI agent retrieves relevant information from the support knowledge base before generating a response.

## Key Features

### AI Customer Support Agent

The AI agent analyzes each customer request and determines:

- Category
- Priority
- Sentiment
- Recommended action
- Customer response

### Retrieval-Augmented Generation (RAG)

The support agent uses a vector-based knowledge base to retrieve relevant support information before answering customers.

The knowledge base covers:

- Payment issues
- Login problems
- Profile changes
- Refund requests
- Account security
- Human escalation rules

The AI is instructed not to invent policies, pricing, refund decisions, account information, or technical information.

### Customer CRM

Customer information is stored in PostgreSQL.

The CRM automatically:

- Creates new customer records
- Updates existing customers using email
- Tracks total tickets
- Stores the latest category
- Stores the latest priority
- Stores the latest sentiment
- Tracks the latest contact date

### Support Ticket Management

Each support request is stored in PostgreSQL with:

- Customer information
- Subject
- Message
- Category
- Priority
- Sentiment
- Recommended action
- AI response
- Customer ID
- Escalation status
- Escalation reason
- Timestamp

### Human Escalation

The workflow automatically identifies requests that require human support.

Escalation can occur for:

- Security-related issues
- Refund requests
- High-priority requests
- Repeated payment failures
- Customers who remain unable to access their account
- Requests requiring account-specific human action

When escalation is required, a separate escalation alert is sent to support.

## Example Workflow

### Normal Support Request

Customer Request
↓
AI Analysis
↓
RAG Knowledge Retrieval
↓
Customer Response
↓
CRM Update
↓
Ticket Saved
↓
Support Notification

### Escalated Support Request

Customer Request
↓
AI Analysis
↓
RAG Knowledge Retrieval
↓
Escalation Detection
↓
CRM Update
↓
Ticket Saved
↓
Support Notification
↓
Human Escalation Alert

## Sample Support Scenarios

### Payment Issue

Customer:

> My subscription payment failed. What should I do?

The AI provides troubleshooting instructions based on the knowledge base.

If the payment continues to fail after troubleshooting, the workflow can escalate the issue to human support.

### Password Reset

Customer:

> I forgot my password. What should I do?

The AI retrieves the relevant login and password-reset instructions from the knowledge base and provides the customer with the appropriate guidance.

### Security Issue

Customer:

> Someone may have accessed my account. What should I do?

The workflow identifies the security-related request and automatically escalates it to human support.

## Technologies

- n8n
- Google Gemini
- Gemini Embeddings
- Retrieval-Augmented Generation (RAG)
- PostgreSQL
- Gmail
- Webhooks
- JavaScript
- Git
- GitHub

## Project Structure

AI-Customer-Support-Automation/
│
├── data/
│   ├── sample-tickets.json
│   └── support-knowledge.md
│
├── workflow/
│   └── AI Customer Support Automation.json
│
├── .gitignore
└── README.md

## Testing

The workflow was tested with multiple customer scenarios, including:

- Password reset
- Payment failure
- Account security issue
- Normal support request
- Human escalation

Test results confirmed:

- Successful webhook requests
- AI classification
- RAG knowledge retrieval
- Customer CRM creation/update
- Support ticket storage
- Customer ID relationship
- Support notification email
- Human escalation email
- JSON webhook response

## Portfolio Value

This project demonstrates practical skills in:

- AI workflow automation
- AI agents
- RAG implementation
- LLM integration
- Vector search
- API/webhook integration
- Database automation
- CRM automation
- Customer support automation
- Conditional workflow logic
- Human-in-the-loop escalation
- PostgreSQL data modeling
- Email automation
- JavaScript data processing
- Git/GitHub version control

## Project Status

**Completed**

Built as part of an AI Automation portfolio focused on real-world business automation systems.