# Testing Notes

## Testing Approach

The project used both manual tests and simulated conversations.

Testing focused on:

- Knowledge-base accuracy
- Routing correctness
- Lead / quote collection
- Appointment-request behaviour
- Existing-customer handling
- Human escalation
- Safety escalation
- Opt-out handling
- False-action prevention
- Retrieval quality
- Response length and tone

## Example Retrieval Test

### Initial Test

A customer asked a combined question about heat-pump pricing and financing availability.

The agent returned accurate pricing but failed to surface financing information in the first response, even though financing information existed elsewhere in the knowledge base.

### Diagnosis

The issue appeared to be knowledge retrieval rather than the language model itself.

### Improvement

The knowledge base was restructured so financing information was cross-referenced near pricing.

### Retest

The same customer question then returned both pricing and financing information in the first response.

This demonstrates iterative debugging of a real conversational-AI retrieval problem rather than only prompt editing.

## Successful Test Areas

- General service questions
- Pricing with non-binding quote language
- Financing after retrieval tuning
- Service-area questions
- Availability uncertainty
- Safety escalation
- Human-assistance routing
- Lead and appointment flow exits
