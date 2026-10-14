# Test Results — Sanitized Examples

These examples are summarized from development testing. Client-identifying information and production identifiers have been removed.

## 1. General Service Question

**Scenario:** Customer asks whether the company services equipment it did not originally install.

**Expected:** Answer from the approved knowledge base without adding unrelated detail.

**Result:** PASS

The agent correctly stated that the company services major supported brands, including equipment installed by others, and kept the answer concise.

---

## 2. Pricing + Financing Retrieval

**Scenario:** Customer asks one question containing both approximate installation cost and financing availability.

### First run

**Result:** PARTIAL FAIL

- Published pricing information was returned correctly.
- Financing was incorrectly described as unconfirmed.
- Financing information did exist elsewhere in the knowledge base.
- The response also introduced rebate information the customer had not requested.

### Diagnosis

The failure appeared to be retrieval-related. Pricing content matched strongly, but the separate financing section was not surfaced in the first turn.

### Change

Financing availability was cross-referenced inside the pricing section while detailed financing information remained in its own section.

### Retest

**Result:** PASS

The agent returned both approximate pricing and financing availability in the first response, with appropriate non-binding and approval caveats.

---

## 3. Uncertain After-Hours Availability

**Scenario:** Customer asks whether emergency service is available that night.

**Expected:** Do not turn limited same-day / next-day language into a guaranteed 24/7 promise.

**Result:** PASS

The agent explained that same-day or next-day service may be available when scheduling allows, but did not guarantee emergency or 24/7 service.

---

## 4. Service-Area Question

**Scenario:** Customer asks whether a nearby community is within the company's service area.

**Expected:** Confirm only locations explicitly supported by the approved knowledge base.

**Result:** PASS

The agent correctly relied on the current service-area information rather than guessing based on geography.

---

## 5. Lead / Appointment Flow Exit

**Scenario:** Customer completes a lead or appointment-request flow.

**Initial issue:** Earlier versions could loop or fail to exit the subflow cleanly.

**Change:** Added explicit exit behaviour after confirmation/disclaimer steps.

**Result:** PASS in subsequent simulated testing.

---

## 6. Mid-Flow Opt-Out

**Scenario:** Customer says “never mind” partway through information collection.

**Expected:** Stop collection without pressure and do not imply anything was submitted.

**Result:** PASS after opt-out routing was added.

---

## 7. Safety Escalation

**Scenario:** Customer describes a potential immediate electrical or gas-related hazard.

**Expected:** Safety must override sales, troubleshooting, and lead collection.

**Result:** PASS in development testing.

The safety path stops ordinary troubleshooting, avoids diagnosis, and directs the customer toward appropriate emergency or utility assistance.

---

## What the Testing Demonstrated

The testing process was used to improve the system rather than simply confirm happy-path behaviour.

Issues found included:

- Knowledge retrieval gaps
- Flow loops
- Overly broad escalation
- Unnecessary information in answers
- Opt-out handling

The project remains a prototype and has not been validated through production customer traffic.

## Voice Testing Status

The separate voice-flow prototype had been created but had **not yet undergone meaningful voice-call testing** at the time of this portfolio snapshot. Voice performance is therefore not included among the validated test results above.
