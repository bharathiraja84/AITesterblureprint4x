# Automotive System Requirements Checklist
## For SYS.4 â€“ System Integration & Integration Test and SYS.5 â€“ System Qualification Test

**Project:** [Project Name]  
**Product / ECU:** [Product Name]  
**Requirement Specification:** [Document / Baseline]  
**Review Date:** [DD-MMM-YYYY]  
**Reviewed by:** [Name / Team]  
**Version:** [Version]

---

# 1. Requirement Identification

For each requirement, verify:

- [ ] Unique Requirement ID is available
- [ ] Requirement title is available
- [ ] Requirement source is identified
- [ ] Requirement owner is identified
- [ ] Requirement version / baseline is controlled
- [ ] Requirement status is defined
- [ ] Requirement type is identified

Typical requirement types:

- [ ] Functional
- [ ] Interface
- [ ] Performance
- [ ] Timing
- [ ] Diagnostic
- [ ] Safety
- [ ] Cybersecurity
- [ ] Communication
- [ ] Environmental
- [ ] Regulatory
- [ ] Customer-specific
- [ ] Calibration
- [ ] Robustness

---

# 2. Requirement Quality

## 2.1 Clear
- [ ] Requirement is understandable
- [ ] Terminology is defined
- [ ] No vague wording is used
- [ ] No subjective terms are used

Avoid: Fast, Sufficient, Adequate, Normally, Appropriate, Quickly, User-friendly, As required, Etc.

## 2.2 Atomic
- [ ] Requirement contains only one primary requirement
- [ ] Multiple behaviours are not combined unnecessarily
- [ ] Requirement can be independently verified

## 2.3 Unambiguous
- [ ] Requirement has only one possible interpretation
- [ ] Actors are clearly identified
- [ ] Inputs are clearly identified
- [ ] Outputs are clearly identified
- [ ] Conditions are clearly specified
- [ ] Expected response is explicitly defined

## 2.4 Complete
- [ ] Trigger
- [ ] Preconditions
- [ ] Input
- [ ] Behaviour
- [ ] Output
- [ ] Timing
- [ ] Tolerance
- [ ] Operating mode
- [ ] Boundary conditions
- [ ] Failure reaction
- [ ] Recovery behaviour

## 2.5 Consistent
- [ ] Requirement does not conflict with another system requirement
- [ ] Requirement is consistent with system architecture
- [ ] Requirement is consistent with interface specification
- [ ] Requirement is consistent with customer specification
- [ ] Requirement is consistent with safety requirements
- [ ] Requirement is consistent with communication specification

---

# 3. Testability Checklist

- [ ] Requirement can be tested, analysed, inspected, or demonstrated
- [ ] Verification method is identified
- [ ] Expected result can be objectively determined
- [ ] Input stimulus can be generated
- [ ] Output response can be measured
- [ ] Acceptance criteria are defined
- [ ] Tolerances are specified where required
- [ ] Test environment can reproduce the required conditions
- [ ] Required test equipment is available or identifiable
- [ ] No implementation knowledge is unnecessarily required to verify the requirement

---

# 4. Requirement Structure

Recommended structure:

> **When [condition/trigger], the [system] shall [required behaviour] within [performance/timing constraint].**

Checklist:

- [ ] Condition is specified
- [ ] System/component is specified
- [ ] Mandatory behaviour uses "shall"
- [ ] Output/action is measurable
- [ ] Timing is specified where relevant
- [ ] Units are specified

---

# 5. Preconditions

- [ ] Initial system state is defined
- [ ] Operating mode is defined
- [ ] Vehicle state is defined where required
- [ ] Ignition state is defined
- [ ] Supply voltage condition is defined
- [ ] Communication state is defined
- [ ] Relevant faults are defined
- [ ] Required calibration/configuration is defined

---

# 6. Input Definition

- [ ] Input signal is identified
- [ ] Signal source is identified
- [ ] Valid range is specified
- [ ] Unit is specified
- [ ] Resolution is specified where required
- [ ] Accuracy is specified where required
- [ ] Update rate is specified
- [ ] Invalid input behaviour is defined
- [ ] Out-of-range behaviour is defined
- [ ] Missing input behaviour is defined

---

# 7. Output Definition

- [ ] Expected system output is identified
- [ ] Output signal is identified
- [ ] Physical output is defined where applicable
- [ ] Unit is defined
- [ ] Accuracy / tolerance is defined
- [ ] Timing is defined
- [ ] Output state under fault conditions is defined

---

# 8. Timing Requirements

- [ ] Timing reference point is defined
- [ ] Start condition is defined
- [ ] End condition is defined
- [ ] Maximum response time is specified
- [ ] Minimum response time is specified where applicable
- [ ] Sampling time is considered
- [ ] Communication delay is considered
- [ ] Measurement tolerance is defined

---

# 9. Boundary Conditions

- [ ] Minimum operating value
- [ ] Maximum operating value
- [ ] Threshold value
- [ ] Below threshold
- [ ] At threshold
- [ ] Above threshold
- [ ] Invalid range
- [ ] Saturation behaviour

---

# 10. Operating Modes

- [ ] Power-up
- [ ] Initialization
- [ ] Normal operation
- [ ] Standby
- [ ] Sleep
- [ ] Wake-up
- [ ] Degraded mode
- [ ] Limp-home
- [ ] Diagnostic mode
- [ ] Programming mode
- [ ] Shutdown

---

# 11. Interface Requirements â€“ SYS.4 Focus

- [ ] Interface source identified
- [ ] Interface destination identified
- [ ] Interface type identified
- [ ] Direction identified
- [ ] Data / signal identified
- [ ] Signal range defined
- [ ] Unit defined
- [ ] Scaling defined
- [ ] Offset defined
- [ ] Update rate defined
- [ ] Timing defined
- [ ] Timeout defined
- [ ] Default value defined
- [ ] Invalid value defined
- [ ] Error handling defined
- [ ] Interface ownership defined

---

# 12. Communication Requirements

For CAN / LIN / Ethernet / J1939:

- [ ] Message ID defined
- [ ] Message name defined
- [ ] Transmitter identified
- [ ] Receiver identified
- [ ] Cycle time specified
- [ ] Timeout specified
- [ ] Signal position specified
- [ ] Signal length specified
- [ ] Scaling specified
- [ ] Offset specified
- [ ] Endianness specified
- [ ] Valid range specified
- [ ] Invalid value specified
- [ ] Timeout behaviour specified
- [ ] Alive counter behaviour specified
- [ ] CRC behaviour specified
- [ ] E2E protection defined where applicable
- [ ] Network management behaviour defined

---

# 13. Diagnostic Requirements

- [ ] Fault detection condition defined
- [ ] Fault confirmation condition defined
- [ ] Detection time defined
- [ ] DTC specified
- [ ] DTC status behaviour specified
- [ ] Warning behaviour specified
- [ ] Freeze-frame requirement specified
- [ ] Failure reaction defined
- [ ] Recovery condition defined
- [ ] Healing criteria defined
- [ ] Ageing criteria defined
- [ ] Diagnostic service defined
- [ ] Diagnostic session conditions defined

---

# 14. Fault Handling Requirements

- [ ] Fault condition is defined
- [ ] Detection mechanism is defined
- [ ] Detection time is defined
- [ ] System reaction is defined
- [ ] Degraded behaviour is defined
- [ ] Driver warning is defined
- [ ] DTC behaviour is defined
- [ ] Recovery behaviour is defined
- [ ] Fault latching behaviour is defined
- [ ] Safe state is defined where applicable

---

# 15. Safety Requirements

- [ ] Safety requirement ID available
- [ ] ASIL classification available
- [ ] Safety goal traceability available
- [ ] Technical safety requirement traceability available
- [ ] Safety mechanism defined
- [ ] Fault detection time defined
- [ ] Fault tolerant time interval considered
- [ ] Safe state defined
- [ ] Degraded state defined
- [ ] Warning concept defined
- [ ] Verification method defined
- [ ] Fault injection feasibility assessed

---

# 16. Performance Requirements

- [ ] Response time
- [ ] Accuracy
- [ ] Precision
- [ ] Control stability
- [ ] Pressure build-up
- [ ] Deceleration
- [ ] Latency
- [ ] Processing time
- [ ] Communication timing
- [ ] CPU / resource utilisation where applicable

Each target shall include:
- [ ] Nominal value
- [ ] Tolerance
- [ ] Operating condition
- [ ] Measurement method

---

# 17. Robustness Requirements

- [ ] Rapid input changes
- [ ] Noise
- [ ] Signal oscillation
- [ ] Repeated activation
- [ ] Power cycling
- [ ] ECU reset
- [ ] Communication interruption
- [ ] Communication recovery
- [ ] Invalid sequence
- [ ] Extreme operating conditions
- [ ] Simultaneous faults where applicable

---

# 18. Environmental Conditions

- [ ] Minimum voltage defined
- [ ] Maximum voltage defined
- [ ] Cranking voltage behaviour defined
- [ ] Overvoltage behaviour defined
- [ ] Undervoltage behaviour defined
- [ ] Temperature range defined
- [ ] Pressure range defined
- [ ] Humidity conditions defined
- [ ] Vibration / shock requirements referenced
- [ ] EMC-related requirements referenced

---

# 19. Variant Requirements

- [ ] Applicable product variants identified
- [ ] Vehicle variants identified
- [ ] Hardware variants identified
- [ ] Software variants identified
- [ ] Calibration variants identified
- [ ] Feature coding considered
- [ ] Regional variants considered
- [ ] Customer variants considered
- [ ] Requirement applicability clearly stated

---

# 20. SYS.4 Traceability Checklist

- [ ] System architecture elements are identified
- [ ] Interfaces between system elements are identified
- [ ] Integration requirements exist
- [ ] Interface requirements exist
- [ ] Architecture element â†’ requirement trace exists
- [ ] Requirement â†’ SYS.4 test case trace exists
- [ ] SYS.4 test case â†’ test result trace exists
- [ ] Defects are linked to failed tests
- [ ] Changes are impact-analysed

Recommended trace:

**System Architecture â†’ Interface / Integration Requirement â†’ SYS.4 Test Case â†’ Test Result â†’ Defect**

---

# 21. SYS.5 Traceability Checklist

- [ ] System requirements baseline is available
- [ ] All applicable system requirements have verification methods
- [ ] System requirement â†’ SYS.5 test case trace exists
- [ ] Test case â†’ execution result trace exists
- [ ] Failed requirements can be identified
- [ ] Untested requirements can be identified
- [ ] Safety requirements are traceable
- [ ] Customer requirements are traceable
- [ ] Requirement coverage can be reported

Recommended trace:

**Customer Requirement â†’ System Requirement â†’ SYS.5 Test Case â†’ Test Result â†’ Defect**

---

# 22. Requirement Coverage Classification

| Field | Value |
|---|---|
| Requirement ID | [ID] |
| Requirement Type | [Functional / Interface / etc.] |
| SYS.4 Applicable | Yes / No |
| SYS.5 Applicable | Yes / No |
| Verification Method | Test / Analysis / Inspection / Simulation |
| Test Case Available | Yes / No |
| Automation Candidate | Yes / No |
| Safety Relevant | Yes / No |
| Variant Specific | Yes / No |
| Status | Ready / Not Ready |

---

# 23. Requirement Readiness for Testing

A requirement is **READY FOR TESTING** only if:

- [ ] Requirement is approved/baselined
- [ ] Requirement is understandable
- [ ] Requirement is complete
- [ ] Requirement is unambiguous
- [ ] Requirement is testable
- [ ] Required inputs are defined
- [ ] Expected outputs are defined
- [ ] Acceptance criteria are defined
- [ ] Timing/tolerance is defined where required
- [ ] Applicable variant is defined
- [ ] Test environment can support verification
- [ ] Traceability is available

---

# 24. Requirement Review Status

### GREEN â€“ Test Ready
Clear, complete, testable, traceable.

### AMBER â€“ Clarification Required
Minor information missing; test design may proceed partially.

### RED â€“ Not Testable
Examples:
- Expected result undefined
- Timing undefined
- Interface behaviour undefined
- Ambiguous wording
- Contradictory requirement
- Missing acceptance criteria
- Required operating condition undefined

---

# 25. Requirements Review Summary

| Metric | Value |
|---|---:|
| Total System Requirements | [#] |
| Requirements Reviewed | [#] |
| Green / Test Ready | [#] |
| Amber / Clarification Required | [#] |
| Red / Not Testable | [#] |
| SYS.4 Applicable | [#] |
| SYS.5 Applicable | [#] |
| Safety Relevant | [#] |
| Requirements with Test Cases | [#] |
| Requirements without Test Cases | [#] |
| Overall Test Readiness | [%] |

---

# 26. Recommended Requirement Review Questions

1. **What exactly shall the system do?**
2. **Under what condition shall it do it?**
3. **What input triggers the behaviour?**
4. **What output should be observed?**
5. **How quickly should it respond?**
6. **What tolerance is acceptable?**
7. **What happens at the boundary?**
8. **What happens if the input fails?**
9. **What happens when the condition returns to normal?**
10. **Can I objectively determine PASS or FAIL?**

---

# Appendix A â€“ Quick V&V Requirement Checklist

- [ ] **Unique**
- [ ] **Clear**
- [ ] **Atomic**
- [ ] **Unambiguous**
- [ ] **Complete**
- [ ] **Consistent**
- [ ] **Feasible**
- [ ] **Testable**
- [ ] **Measurable**
- [ ] **Traceable**
- [ ] **Acceptance criteria defined**
- [ ] **Applicable variant identified**

> **Can I generate the input, observe the output, and objectively determine PASS or FAIL?**

If the answer is **No**, the requirement is not yet sufficiently testable.

---

# Appendix B â€“ Recommended Requirement Template

**Requirement ID:** [SYS_REQ_xxxx]

**Requirement:**

> When **[trigger / condition]**, the **[system / component]** shall **[required behaviour]** within **[timing/performance limit]**, under **[operating condition]**.

**Inputs:**  
[Signals / physical inputs]

**Expected Output:**  
[Expected system response]

**Acceptance Criteria:**  
[Quantitative PASS criteria]

**Operating Conditions:**  
[Vehicle / ECU / environment state]

**Failure Behaviour:**  
[Expected reaction]

**Recovery Behaviour:**  
[Expected recovery]

**Applicable Variant:**  
[Variant]

**Verification Method:**  
[Test / Analysis / Inspection / Simulation]

**Test Level:**  
[SYS.4 / SYS.5]

**Safety Classification:**  
[QM / ASIL A / B / C / D / N/A]

**Linked Test Case:**  
[Test Case ID]
