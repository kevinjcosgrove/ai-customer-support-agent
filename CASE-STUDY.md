# Case Study — AI Customer Support Agent

## The Problem

Home-services businesses often receive repetitive questions about services, pricing, service areas, maintenance, financing, and appointment availability. Staff also have to handle missed calls, after-hours enquiries, quote requests, and existing-customer issues.

The project explored how conversational AI could provide a consistent first point of contact without pretending to replace a technician, estimator, or customer-service employee.

## The Goal

Build a prototype AI customer-support agent that could:

- Answer approved customer questions from a structured knowledge base
- Identify why a customer is contacting the business
- Collect useful information for service and quote requests
- Route existing-customer issues separately from new enquiries
- Recognize when human assistance is required
- Prioritize safety when a customer describes a potentially hazardous situation
- Avoid claiming that a booking, callback, submission, or transfer occurred unless a real integration confirmed it

The project was intentionally kept in prototype form while the business's final CRM, booking, and lead-delivery requirements remained undefined.

## My Role

I designed, configured, tested, and iterated on the customer experience and AI-agent architecture.

My work included:

- Consolidating fragmented business information into a structured knowledge base
- Identifying missing, contradictory, and date-sensitive information
- Designing the conversational architecture and routing logic
- Writing grounding, safety, pricing, rebate, and false-action guardrails
- Building lead, quote, appointment-request, existing-customer, safety, and human-assistance paths
- Testing conversations manually and through simulations
- Diagnosing retrieval and routing failures
- Refining the knowledge base and prompts based on test results
- Designing a separate voice receptionist prototype for missed and after-hours calls
- Using Git to track project changes and iterations

## Solution Architecture

The prototype was built around four layers:

1. **Business knowledge** — approved customer-facing information
2. **Knowledge retrieval** — relevant information supplied to the AI at conversation time
3. **Conversation logic** — routing, intake, safety, escalation, and wrap-up paths
4. **Future integrations** — CRM, booking, messaging, and lead delivery

The agent was deliberately prevented from presenting future integrations as if they already existed.

## Key Design Decisions

### Grounding over general knowledge

The agent was instructed to use only approved company information for business-specific answers. It was not allowed to fill missing details with generic HVAC or electrical knowledge.

### No false actions

A major design rule was that the assistant could not say a lead was submitted, an appointment was booked, a callback was arranged, or information was sent unless an authorized tool actually confirmed the action.

### Safety overrides sales

Potential hazards such as fire, smoke, sparking, suspected gas leaks, exposed wiring, carbon-monoxide alarms, flooding near electrical equipment, and shock risk bypass normal sales or intake flows.

### Minimal information collection

The agent collects only the information needed for the customer's current request instead of forcing every visitor through a long form.

### Human escalation is selective

Human assistance is used when a customer explicitly asks for a person or needs a binding decision, technical diagnosis, exception, refund, guarantee, or information the approved knowledge base cannot support.

## A Real Retrieval Problem I Found

One of the strongest debugging examples came from a normal customer question that asked about both pricing and financing.

### Initial result

The agent correctly returned the company's published pricing ranges but incorrectly said financing could not be confirmed.

The financing information was present in the knowledge base, so the problem was not simply missing content.

### Diagnosis

The combined question strongly matched the pricing material, while the financing information lived in a separate section. The retrieval system returned pricing-related context but did not surface the financing section during the first response.

### What I changed

I restructured the knowledge base so financing was also cross-referenced near pricing, while keeping the full financing details in their dedicated section.

### Retest

The same question was asked again. The agent then returned both the pricing information and the financing availability in the first response.

This was a useful example of treating an AI failure as a system problem — retrieval, information structure, and prompt context — rather than simply changing the model or adding more instructions.

## Testing

Testing included:

- General customer questions
- Pricing and financing
- Service-area questions
- Repair and maintenance questions
- Lead and quote intake
- Appointment-request flows
- Existing-customer complaints and service issues
- Human-assistance requests
- Safety hazards
- Opting out midway through information collection
- Unsupported questions
- Multi-topic knowledge retrieval

Both simulated conversations and manual tests were used.

## Voice Prototype

After the chat agent reached a stable prototype stage, I designed and configured an **initial voice-flow prototype** intended for:

- Missed calls during business hours
- All calls outside business hours

The voice prototype uses a simplified eight-node architecture designed for shorter spoken interactions. At this stage, it represents the planned voice conversation structure rather than a validated voice experience.

Meaningful voice testing and tuning have **not yet been completed**. Production call forwarding, phone-number assignment, CRM submission, and booking were also intentionally left out while the business workflow was still being defined.

## Technology

- Retell AI
- GPT-5.6 Luna
- Retrieval-augmented knowledge bases
- Conversation-flow routing
- Prompt and guardrail design
- Post-conversation structured analysis
- Voice-agent prototyping
- Git
- Markdown documentation

## Current Status

### Completed in the prototype

- Structured knowledge base
- Core chat-agent prompt
- General Q&A
- Lead and quote intake
- Appointment-request flow design
- Existing-customer routing
- Human escalation
- Urgent-safety handling
- Opt-out behaviour
- Retrieval tuning
- Manual and simulated testing
- Initial voice-agent flow prototype

### Still in development

- Voice testing and tuning
- Production CRM integration
- Lead delivery
- Email / SMS / webhook automation
- Callback workflow
- Calendar and booking integration
- Production phone routing
- Final client-approved operational details
- Live deployment
- Production performance measurement

## What This Project Demonstrates

This project demonstrates practical experience with:

- Customer experience design
- Conversational AI
- Prompt engineering
- Knowledge management
- Requirements gathering
- Workflow design
- AI testing and debugging
- Safety and escalation design
- Technical troubleshooting
- Iterative product development

No production deployment, revenue impact, conversion improvement, or customer-service performance gains are claimed because those outcomes have not yet been verified.
