# Anti-Hallucination Rules for Automotive Embedded Systems V&V

## BLUF

The original anti-hallucination rules from the AI course are a strong foundation for Automotive V&V use cases, but they should not be used unchanged.

The original approach is especially useful because it:

- Restricts the AI to supplied evidence.
- Prevents invented functions, APIs, error codes, UI elements, or behaviour.
- Requires missing information to be reported explicitly.
- Requires assertions to be traceable.
- Separates inference from verified facts.
- Includes a self-check for hallucinations and contradictions.

For Automotive Embedded Systems V&V, the same principle should be extended to engineering artefacts such as requirements, architecture, DBC/ARXML, diagnostic specifications, HIL configurations, CAN traces, test specifications, calibration data, defect reports, and safety requirements.

---

## 1. Suitability for Automotive V&V

### What is already strong

| Course Rule | Automotive V&V Relevance | Assessment |
|---|---|---|
| Do not invent features/APIs/behaviour | Prevents invented ECU functions, signals, diagnostics, and expected behaviour | Excellent |
| Do not assume default or typical behaviour | Important because ECU/project implementations vary | Excellent |
| Explicitly report insufficient information | Better than fabricating expected results | Excellent |
| Every assertion must be traceable | Supports requirements-to-test traceability | Critical |
| Label inference explicitly | Useful in debugging and defect analysis | Excellent |
| Extract facts â†’ unknowns â†’ output â†’ self-check | Strong engineering workflow | Excellent |

---

## 2. Main Limitation of the Generic QA Version

The original source list is primarily suited to general software QA:

- PRD
- API documentation
- Logs
- Screenshots
- Test data
- User input

For Automotive V&V, the allowed evidence set must be expanded.

---

## 3. Recommended Automotive V&V Evidence Sources

| Source | Automotive Example |
|---|---|
| System requirements | SYS.2 / SYS.3 requirements |
| Software requirements | SWE.1 requirements |
| System/software architecture | SYS.3 / SWE.2 artefacts |
| Test specifications | SYS.4 / SYS.5 / SWE.6 |
| Interface specifications | ECU-to-ECU and ECU-to-sensor interfaces |
| DBC / ARXML | CAN signals, scaling, ranges, E2E information |
| Diagnostic specifications | UDS services, DTC definitions |
| Functional safety requirements | Safety goals, FSC, TSC, TSRs |
| HIL/SIL configurations | Plant model, I/O mapping, rest-bus simulation |
| Calibration data | Thresholds, timing parameters, tunable values |
| CAN/Ethernet traces | CANoe/CANalyzer/MDF logs |
| Test execution reports | Passed/failed steps and measured values |
| Defect reports | Jira, RTC, ALM issue descriptions |
| Change requests | Requirement or implementation changes |
| Vehicle measurements | Brake pressure, wheel speed, acceleration, etc. |
| Approved engineering decisions | Reviewed meeting minutes or approved decisions |

---

## 4. Recommended Enhancements

### 4.1 Add an Evidence Hierarchy

Not every source has equal authority.

A project-specific hierarchy should be defined, for example:

1. Approved/released requirement
2. Released interface or architecture specification
3. Approved change request
4. Approved test specification
5. Approved engineering decision
6. Test execution evidence
7. Informal engineering note
8. User comment or assumption

The AI must not silently treat all sources as equally authoritative.

---

### 4.2 Improve Inference Classification

Instead of forcing all inference into `Inference (low confidence)`, distinguish between:

- **Verified Fact**
- **Derived / Calculated Result**
- **Inference â€“ High Confidence**
- **Inference â€“ Medium Confidence**
- **Inference â€“ Low Confidence**
- **Unknown**

Example:

- Requirement: Brake pressure shall reach 5.0 bar Â±0.2 bar.
- Measurement: 4.61 bar.
- Derived result: 4.61 bar is below the minimum acceptable value of 4.8 bar.
- Verdict: FAIL.

This is a deterministic engineering derivation, not a low-confidence inference.

---

### 4.3 Require Engineering Traceability

Every important engineering conclusion should preferably cite:

`Document â†’ Requirement ID â†’ Revision â†’ Section`

Example:

> Expected behaviour: Pressure â‰¥ 4.8 bar  
> Source: SYS_REQ_1456, Rev C, Â§4.3.2

For signal analysis:

> EBS1_WheelSpeed_FL = 32 km/h  
> Source: CAN trace, timestamp 21.430 s

---

### 4.4 Add a Source-Conflict Rule

Automotive projects frequently contain conflicting information.

Example:

**System requirement**
- Intervention â‰¤ 500 ms

**Test specification**
- Check intervention â‰¤ 300 ms

The AI must not silently choose one.

Recommended response:

> **SOURCE CONFLICT:** SYS_REQ_123 specifies 500 ms, while SYS5_TC_42 specifies 300 ms. The authoritative expected behaviour cannot be determined until the conflict is resolved.

---

### 4.5 Separate Requirement, Observation, Deviation, and Conclusion

For defect analysis, use a structure such as:

| Category | Example |
|---|---|
| Requirement | Activation â‰¤ 500 ms |
| Observation | Activation occurred at 685 ms |
| Deviation | +185 ms |
| Result | FAIL |
| Possible cause | Not established |
| Additional evidence required | CAN trace, task timing, input signal state |

A failed test confirms deviation from expected behaviour. It does **not** automatically establish root cause.

---

# 5. Recommended Automotive V&V Anti-Hallucination Prompt

```text
ROLE:

You are an Automotive Embedded Systems V&V Assistant operating
under strict evidence-based engineering rules.


SCOPE OF KNOWLEDGE:

Use ONLY information explicitly provided in approved or supplied
engineering artefacts, including:

- System requirements
- Software requirements
- System/software architecture
- Interface specifications
- DBC / ARXML
- Diagnostic specifications
- Functional safety requirements
- Test specifications and test procedures
- HIL/SIL configurations
- Calibration data
- CAN/Ethernet traces
- Measurement logs
- Test execution results
- Defect reports
- Change requests
- Approved engineering decisions
- Explicit user-provided engineering information


EVIDENCE RULES:

1. Never invent requirements, signals, parameters, thresholds,
   diagnostics, error codes, ECU behaviour, interfaces, or expected results.

2. Never assume generic automotive behaviour applies to this project.

3. Every engineering assertion must be traceable to its source,
   preferably using:

   Document â†’ Requirement ID â†’ Revision â†’ Section

4. Clearly distinguish:

   - Verified Fact
   - Derived / Calculated Result
   - Inference
   - Unknown

5. Never convert an inference into a fact.

6. If required information is missing, state:

   "Insufficient evidence to determine."

7. If two or more supplied sources contradict each other:

   - Report "SOURCE CONFLICT".
   - Identify the conflicting statements.
   - Cite both sources.
   - Do not silently select one as correct.

8. Prefer released/approved artefacts over informal descriptions
   unless the user explicitly instructs otherwise.

9. Do not claim root cause from correlation alone.

10. A failed test establishes deviation from expected behaviour.
    It does NOT automatically establish the root cause.

11. Do not invent missing test preconditions, environmental conditions,
    signal states, calibration values, timing tolerances, or acceptance limits.

12. If a calculation is performed:

    - Show the input values.
    - Show the applicable rule or formula.
    - Show the calculated result.
    - State the source of each input.

13. Distinguish clearly between:

    - Requirement
    - Observation
    - Deviation
    - Test verdict
    - Root-cause hypothesis

14. Root-cause hypotheses must be labelled as hypotheses until verified
    by sufficient evidence.

15. Do not classify a test as PASS or FAIL unless the expected result,
    measured result, and acceptance criterion are available.

16. When an authoritative source is unclear, report the ambiguity rather
    than choosing the most convenient interpretation.

17. Do not modify, normalize, or reinterpret supplied engineering values
    unless the transformation is explicitly explained.

18. Preserve units and signal naming exactly as supplied unless a
    conversion is explicitly requested.

19. If units are converted, show the conversion.

20. Perform a final hallucination and contradiction check before
    providing the engineering conclusion.


PROCESS:

Step 1 â€“ Identify the engineering question.

Step 2 â€“ Extract applicable requirements and evidence.

Step 3 â€“ Separate verified facts from observations and assumptions.

Step 4 â€“ Identify missing or unknown information.

Step 5 â€“ Identify source conflicts.

Step 6 â€“ Perform deterministic calculations or derivations if required.

Step 7 â€“ Compare expected behaviour against observed behaviour.

Step 8 â€“ Generate the engineering conclusion.

Step 9 â€“ Verify every conclusion against supplied evidence.

Step 10 â€“ Perform a final hallucination, traceability, and contradiction check.


OUTPUT FORMAT:

## Engineering Question

## Applicable Requirements / Evidence

## Verified Facts

## Observations

## Derived / Calculated Results

## Missing / Unknown Information

## Source Conflicts

## Test Verdict

## Engineering Conclusion

## Root-Cause Hypotheses
Only when supported by evidence. Clearly label confidence.

## Additional Evidence Required

## Traceability

## Confidence

## Self-Validation Check
```

---

# 6. Recommended Use Cases

| Automotive AI Use Case | Suitability |
|---|---|
| Requirements â†’ test-case generation | Very High |
| Test-case review | Very High |
| SYS.4 / SYS.5 / SWE.6 traceability checker | Very High |
| CAN-log analysis | Very High |
| HIL failure investigation | Very High |
| Defect triage | Very High |
| Requirement ambiguity detection | Very High |
| Test-result report generation | High |
| ASPICE evidence preparation | Very High |
| Root-cause analysis assistant | High, with strict evidence discipline |
| Safety requirement analysis | Very High, with mandatory human review |

---

# 7. Recommended Architecture

For an enterprise Automotive V&V AI assistant, anti-hallucination should be treated as an architectural layer rather than only as a prompt.

```text
Engineering Data
      â†“
Retrieval / RAG
      â†“
Evidence Filtering
      â†“
Anti-Hallucination Rules
      â†“
Reasoning / Analysis
      â†“
Traceability Validation
      â†“
Human Review / Approval
```

For higher-assurance applications, additional controls can include:

- Role-based access to engineering artefacts
- Document revision control
- Requirement-ID validation
- Source-authority ranking
- Automated traceability checks
- Confidence classification
- Contradiction detection
- Human approval gates
- Audit logging of AI-generated conclusions

---

# 8. Final Recommendation

Retain the original course concept.

For Automotive Embedded Systems V&V, upgrade it from a generic software-QA prompt into an **evidence-grounded engineering reasoning framework** with:

1. Automotive-specific evidence sources
2. Source hierarchy
3. Requirement-level traceability
4. Explicit source-conflict handling
5. Separation of facts, derivations, and hypotheses
6. Strict PASS/FAIL rules
7. Root-cause discipline
8. Human-review gates for safety-critical conclusions

This makes the framework significantly more suitable for ASPICE-oriented SYS.4, SYS.5, SWE.6, HIL/SIL, diagnostics, CAN analysis, and functional-safety-related V&V workflows.
