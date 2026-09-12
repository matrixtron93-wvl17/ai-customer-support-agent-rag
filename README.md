# AI Customer Support Automation

## Project Overview

An AI-powered customer support automation workflow built with n8n.

The system receives customer inquiries through a webhook, validates the request, uses AI to analyze the inquiry, classifies the issue and priority, generates a suggested response, stores the ticket in PostgreSQL, and sends a support notification by email.

## Workflow

Customer Inquiry
↓
Webhook
↓
Prepare Ticket Data
↓
Validate Request
↓
AI Customer Support
↓
Parse AI Result
↓
Route by Priority
↓
PostgreSQL
↓
Email Notification
↓
Webhook Response

## AI Analysis

The AI analyzes:

- Category
- Priority
- Sentiment
- Suggested response
- Recommended action

## Technologies

- n8n
- OpenAI API
- PostgreSQL
- Gmail SMTP
- Webhooks
- JavaScript
- Git
- GitHub

## Project Status

In Development