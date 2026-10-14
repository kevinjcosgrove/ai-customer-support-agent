# Voice Agent Prototype

## Status

This is an **early architecture prototype**, not a tested or deployed voice receptionist.

The flow was created to explore how the existing chat project could expand into phone support. Meaningful voice-call testing, tuning, production phone routing, and live deployment have not yet been completed.

## Intended Purpose

The voice prototype was designed around two future situations:

1. Missed calls during normal business hours
2. All inbound calls outside business hours

It was not intended to replace staff answering normal daytime calls.

## Intended V1 Scope

The architecture is designed to support:

- Approved general questions
- Caller-intent identification
- New vs. existing customer routing
- Service and quote-request intake
- Minimal caller information collection
- Human-assistance escalation
- Urgent-safety handling

The prototype must **not** claim to:

- Submit a lead
- Send information to staff
- Arrange a callback
- Book or hold an appointment
- Confirm technician availability
- Transfer the caller to a live person

Those capabilities require production integrations that have not been connected.

## Conversation Structure

The initial voice flow was intentionally kept simple:

1. Greeting & Intent
2. General Q&A
3. Service / Quote / Repair Intake
4. Existing Customer Issue
5. Human Assistance
6. Urgent Safety
7. Wrap-Up
8. End Call

Human Assistance and Urgent Safety were configured as global paths that can be reached from elsewhere in the flow.

## Voice-Specific Design Intent

The planned voice experience differs from chat in several ways:

- Shorter spoken responses
- Usually one or two sentences at a time
- One question at a time
- Interruption-aware behaviour
- Avoid long spoken lists unless requested
- Avoid repeating what the caller already said
- Allow callers to change topics
- Confirm names or phone numbers only when needed
- Stop intake gracefully if the caller changes their mind

These are **design goals**, not validated production behaviours.

## Initial Configuration

The prototype was initially configured with:

- GPT-5.6 Luna as the conversational model
- A default Retell-provided voice
- Moderate interruption sensitivity
- Brisk response timing
- Conservative backchannel behaviour
- General speech recognition

These settings were initial configuration choices only. They have **not** been meaningfully validated through real voice testing and should not be presented as tuned or production-ready settings.

## Call Context Design

The architecture was prepared to support different greetings for:

- **Missed daytime call:** acknowledge that the team was unable to answer
- **After-hours call:** explain that the caller reached the company outside normal business hours
- **Fallback:** use a neutral greeting if call context is unavailable

Production business-hours routing was intentionally left for a future inbound-call integration.

## Structured Analysis Fields

The prototype was configured with internal analysis fields intended to support future testing, such as:

- Customer type
- Caller name
- Callback number
- Location
- Service/request type
- Preferred timeframe
- Safety issue detected
- Call outcome
- Short call summary

These fields are configuration only and do not imply that information was submitted to a production system or that post-call analysis has been validated in live use.

## Future Work

- Run meaningful manual voice tests
- Select and tune a production voice
- Validate interruption and silence behaviour
- Connect missed-call and after-hours routing
- Add structured lead delivery
- Connect a CRM or messaging workflow
- Evaluate booking only after the business scheduling process is defined
