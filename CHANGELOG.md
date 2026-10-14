# Changelog

This is a high-level development timeline for the sanitized portfolio version of the project.

## September 2026 — Knowledge and Agent Foundation

- Consolidated source material into a structured customer-facing knowledge base
- Identified missing and contradictory business information
- Created the initial global agent prompt and grounding rules
- Designed conversation paths for general Q&A, lead collection, appointment requests, existing customers, safety, and human assistance
- Added safeguards against unsupported answers and false booking/submission claims

## September 2026 — Conversation-Flow Testing

- Ran simulated conversations across happy-path and adversarial scenarios
- Fixed subflows that were not exiting correctly
- Refined complaint and human-assistance routing
- Added graceful opt-out behaviour during lead and appointment collection
- Improved safety escalation and unsupported-question handling

## September 2026 — Knowledge Retrieval Tuning

- Updated the knowledge base with newer approved company information
- Tested multi-topic questions involving pricing and financing
- Diagnosed a retrieval failure where financing information was not surfaced on the first turn
- Restructured the knowledge base to cross-reference related information
- Retested successfully with both pricing and financing returned together

## October 2026 — Voice Prototype

- Created a separate voice-agent prototype for missed daytime calls and after-hours calls
- Simplified the architecture into an eight-node voice flow
- Designed an initial voice flow with planned handling for interruptions, silence, caller corrections, and changing topics
- Configured structured post-call analysis fields for future internal testing
- Left phone routing, CRM submission, and booking integrations intentionally unconnected

## Current

- Chat prototype and early voice-flow prototype remain unpublished / in development
- Meaningful voice-call testing and tuning are still future work
- CRM, lead delivery, booking, and production phone routing are future work
- Portfolio materials are being prepared in sanitized form
