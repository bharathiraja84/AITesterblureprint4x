# SYSTEM VERIFICATION & VALIDATION TEST PLAN
## SYS.4 â€“ System Integration and Integration Test
## SYS.5 â€“ System Qualification Test

**Project:** [Project Name]  
**Product / ECU:** [Product Name / ECU Name]  
**Customer:** [Customer / OEM]  
**Project ID:** [Project ID]  
**Document ID:** [Document ID]  
**Version:** [Version]  
**Date:** [DD-MMM-YYYY]  
**Prepared by:** [Name / Function]  
**Reviewed by:** [Name / Function]  
**Approved by:** [Name / Function]  

---

# 1. Purpose

This Test Plan defines the verification and validation strategy, scope, responsibilities, environments, methods, entry/exit criteria, test execution approach, defect handling, traceability, reporting, and acceptance criteria for:

- **SYS.4 â€“ System Integration and Integration Test**
- **SYS.5 â€“ System Qualification Test**

The objective is to provide objective evidence that:

1. System elements are correctly integrated and their interfaces and interactions operate as intended.
2. The integrated system fulfils the specified system requirements.
3. Test activities are performed in a systematic, repeatable, traceable, and controlled manner.
4. Test results provide sufficient evidence for release decisions.

---

# 2. Scope

## 2.1 Product Scope

The test scope covers:

**Product:** [e.g., Electronic Braking System ECU]  
**System Variant(s):** [Variant names]  
**Vehicle/Application:** [Truck / Bus / Trailer / Passenger Vehicle]  
**Hardware Version:** [HW Version]  
**Software Version:** [SW Version]  
**Calibration Version:** [Calibration Version]  

Main system elements include:

- ECU hardware
- Embedded software
- Sensors
- Actuators
- Vehicle communication interfaces
- Power supply interfaces
- Mechanical / pneumatic / hydraulic interfaces, where applicable
- External ECUs / simulated vehicle systems
- Diagnostic interfaces

## 2.2 SYS.4 Scope

SYS.4 activities verify correct integration of system elements and interfaces.

The scope includes:

- System element integration
- Interface verification
- Signal and data-flow verification
- Communication verification
- Timing behaviour
- State-transition behaviour
- Interaction between system elements
- Error propagation
- Startup and shutdown behaviour
- Diagnostic interactions
- Failure handling during integration
- Integration regression testing

SYS.4 primarily answers:

> **â€œAre the system elements correctly integrated and interacting as intended?â€**

## 2.3 SYS.5 Scope

SYS.5 activities verify the complete integrated system against the system requirements.

The scope includes:

- Functional requirements
- Performance requirements
- Timing requirements
- Safety-related requirements
- Diagnostic requirements
- Communication requirements
- Environmental operating conditions where applicable
- Degraded-mode behaviour
- Fault handling
- Robustness requirements
- Customer-specific requirements
- Vehicle behaviour requirements
- Regulatory requirements within project scope

SYS.5 primarily answers:

> **â€œDoes the complete system fulfil the specified system requirements?â€**

---

# 3. Applicable Documents

| Document | Document ID | Version |
|---|---|---|
| System Requirements Specification | [ID] | [Ver] |
| System Architecture Specification | [ID] | [Ver] |
| Interface Specification | [ID] | [Ver] |
| Software Requirements Specification | [ID] | [Ver] |
| Hardware Requirements Specification | [ID] | [Ver] |
| Functional Safety Plan | [ID] | [Ver] |
| Technical Safety Concept | [ID] | [Ver] |
| Cybersecurity Requirements | [ID] | [Ver] |
| Customer Requirements Specification | [ID] | [Ver] |
| Communication Matrix / DBC | [ID] | [Ver] |
| Diagnostic Specification | [ID] | [Ver] |
| Calibration Specification | [ID] | [Ver] |
| System Architecture | [ID] | [Ver] |
| Project Test Strategy | [ID] | [Ver] |

---

# 4. Applicable Standards and Guidelines

Applicable standards include, where relevant:

- Automotive SPICE
- ISO 26262
- ISO/SAE 21434
- ISO 14229 â€“ UDS
- ISO 11898 â€“ CAN
- SAE J1939
- OEM-specific standards
- Internal engineering standards
- Product-specific regulatory standards

Applicable Automotive SPICE processes:

- SYS.1 Requirements Elicitation
- SYS.2 System Requirements Analysis
- SYS.3 System Architectural Design
- **SYS.4 System Integration and Integration Test**
- **SYS.5 System Qualification Test**
- SUP.1 Quality Assurance
- SUP.8 Configuration Management
- SUP.9 Problem Resolution Management
- SUP.10 Change Request Management

---

# 5. Test Objectives

## 5.1 SYS.4 Objectives

SYS.4 testing shall demonstrate that:

- System elements can be integrated according to the system architecture.
- Interfaces between system elements behave according to specification.
- Internal communication and data exchange are correct.
- Timing and sequencing between system elements are correct.
- Failure propagation between components is controlled.
- Integration-related defects are identified before system qualification.
- The integrated system is sufficiently mature for SYS.5 qualification testing.

## 5.2 SYS.5 Objectives

SYS.5 testing shall demonstrate that:

- Each applicable system requirement is verified.
- The system behaves correctly under nominal operating conditions.
- The system behaves correctly at defined operating boundaries.
- Defined failure conditions result in specified system reactions.
- Performance requirements are achieved.
- Diagnostic behaviour meets specification.
- Safety-related requirements are verified.
- Customer acceptance criteria are fulfilled.
- No unacceptable open defects remain before release.

---

# 6. Test Strategy

Testing shall follow a risk-based and requirements-driven approach.

The overall sequence is:

**System Element Availability**  
â†“  
**Integration Build**  
â†“  
**SYS.4 Integration Testing**  
â†“  
**SYS.4 Regression Testing**  
â†“  
**Integration Acceptance**  
â†“  
**SYS.5 Qualification Testing**  
â†“  
**SYS.5 Regression Testing**  
â†“  
**System Test Completion Report**  
â†“  
**Release Recommendation**

---

# 7. Verification Methods

Requirements may be verified using one or more of the following methods:

| Method | Description |
|---|---|
| Test | Dynamic execution of the system |
| Analysis | Mathematical or engineering analysis |
| Inspection | Review of implementation or configuration |
| Simulation | Model-based verification |
| Demonstration | Functional demonstration |
| Measurement | Measurement of physical or timing characteristics |

The verification method shall be recorded against each requirement.

---

# 8. Test Levels

## 8.1 SYS.4 â€“ System Integration Test Levels

Typical integration levels may include:

### Level 1 â€“ ECU Internal Integration

Examples:

- Hardwareâ€“software interaction
- I/O interfaces
- Drivers and application software
- Communication stack interactions

### Level 2 â€“ ECU + Simulated Environment

Examples:

- ECU on HIL
- Sensor simulation
- Actuator simulation
- Network simulation
- Rest-bus simulation

### Level 3 â€“ Multi-ECU Integration

Examples:

- ECU-to-ECU communication
- Gateway interactions
- Vehicle network behaviour
- Cross-domain functions

### Level 4 â€“ System Integration

Examples:

- Complete braking system
- Sensors + ECU + modulators
- Vehicle network
- Diagnostics
- Power supply

Project-specific integration levels:

[Insert project integration sequence]

---

# 9. SYS.4 Test Categories

## 9.1 Interface Testing

Verify:

- Input/output signals
- Electrical interfaces
- CAN / LIN / Ethernet interfaces
- Pneumatic / hydraulic interfaces
- Signal scaling
- Signal range
- Update rate
- Endianness
- Timeout behaviour
- Invalid values
- Message counters
- CRC / E2E protection

## 9.2 Communication Testing

Verify:

- CAN messaging
- J1939 messages
- UDS communication
- Network management
- Bus-off recovery
- Communication timeout
- Missing messages
- Corrupted messages
- Communication recovery

## 9.3 Timing Testing

Verify:

- Response time
- Task sequencing
- Message latency
- Signal processing delay
- Startup time
- Shutdown time
- Diagnostic response time

## 9.4 State and Mode Testing

Verify:

- Initialization
- Normal operation
- Standby
- Sleep
- Wake-up
- Degraded mode
- Limp-home mode
- Shutdown
- Recovery

## 9.5 Failure Propagation Testing

Verify system reaction to:

- Sensor failure
- Actuator failure
- Communication failure
- ECU reset
- Power interruption
- Invalid input
- Signal timeout
- Short/open circuit
- Internal software error

---

# 10. SYS.5 Test Categories

## 10.1 Functional Testing

Verify normal system functionality against system requirements.

Examples:

- Control functions
- Driver requests
- Vehicle state processing
- System activation/deactivation
- Control outputs
- Safety interventions

## 10.2 Performance Testing

Verify:

- Response times
- Control accuracy
- Pressure build-up time
- Deceleration targets
- Signal latency
- Processing performance
- Accuracy limits

## 10.3 Boundary Value Testing

Test applicable boundary conditions including:

- Minimum input
- Maximum input
- Just below threshold
- At threshold
- Just above threshold
- Invalid range

## 10.4 Robustness Testing

Verify system behaviour under:

- Rapid input changes
- Repeated activations
- Communication interruptions
- Sensor noise
- Supply voltage disturbances
- ECU resets
- Abnormal operating sequences

## 10.5 Diagnostic Testing

Verify:

- DTC setting
- DTC healing
- DTC ageing
- Freeze-frame data
- Diagnostic sessions
- Diagnostic services
- Fault memory
- Warning lamp behaviour
- Service-tool interaction

## 10.6 Safety Requirement Testing

Applicable technical safety requirements shall be verified according to the safety plan.

Tests may include:

- Fault injection
- Safety mechanism activation
- Fault detection time
- Safe-state transition
- Degraded operation
- Fault-tolerant time interval
- Warning indication
- Recovery behaviour

Safety-related tests shall maintain bidirectional traceability to applicable safety requirements.

---

# 11. Test Design Techniques

Applicable techniques include:

- Requirements-based testing
- Equivalence partitioning
- Boundary value analysis
- State-transition testing
- Decision table testing
- Cause-effect testing
- Error guessing
- Fault injection
- Pairwise / combinatorial testing
- Scenario-based testing
- Use-case testing
- Risk-based testing

Selection of test design technique shall depend on requirement type and risk.

---

# 12. Test Environment

Tests may be performed using:

| Environment | Purpose |
|---|---|
| MIL | Model verification |
| SIL | Software/system simulation |
| HIL | ECU/system verification |
| Test Bench | Hardware/system integration |
| Vehicle | Real-world system validation |
| Environmental Bench | Temperature / voltage / environmental verification |

Primary SYS.4 environment:

[HIL / Bench / SIL / Other]

Primary SYS.5 environment:

[HIL / Vehicle / Bench / Other]

---

# 13. Test Bench Configuration

The test environment shall contain, as applicable:

- DUT ECU
- HIL simulator
- Real-time simulation system
- CAN interface
- Power supply
- Sensor simulation
- Actuator/load simulation
- Pneumatic/hydraulic system
- Measurement equipment
- Diagnostic tester
- Calibration tool
- Automation controller
- Data acquisition system

Configuration shall be uniquely identified for each test execution.

---

# 14. Tools

| Tool | Purpose | Version |
|---|---|---|
| dSPACE / NI / Vector HIL | HIL testing | [Version] |
| CANoe | Network simulation / analysis | [Version] |
| CANalyzer | Network analysis | [Version] |
| ControlDesk | Measurement / calibration | [Version] |
| Automation Framework | Automated testing | [Version] |
| PTC RV&S / DOORS | Requirements management | [Version] |
| Jenkins / CI Tool | Automated execution | [Version] |
| Defect Management Tool | Defect tracking | [Version] |

Tool qualification requirements shall be evaluated where required by ISO 26262 or project-specific processes.

---

# 15. Test Data

Test data shall include:

- Requirement inputs
- Vehicle parameters
- Calibration values
- Sensor values
- Communication messages
- Environmental parameters
- Fault injection conditions
- Boundary values
- Initial system states

Test data shall be:

- Controlled
- Versioned where appropriate
- Repeatable
- Traceable to applicable test cases

---

# 16. Test Case Structure

Each test case shall contain at minimum:

- Test Case ID
- Test Case Name
- Requirement ID
- Test Level
- Test Objective
- Preconditions
- Test Setup
- Test Data
- Test Steps
- Expected Results
- Acceptance Criteria
- Actual Results
- Test Status
- Evidence / Log Reference
- Tester
- Execution Date
- Software Version
- Hardware Version
- Test Environment

---

# 17. Requirements Traceability

Bidirectional traceability shall be maintained.

### SYS.4

System Architecture / Interface Requirement  
â†•  
SYS.4 Test Case  
â†•  
SYS.4 Test Result

### SYS.5

System Requirement  
â†•  
SYS.5 Test Case  
â†•  
SYS.5 Test Result

The traceability report shall identify:

- Requirements with test coverage
- Requirements without test coverage
- Test cases without requirements
- Failed requirements
- Blocked requirements
- Not-tested requirements

---

# 18. Test Coverage

Coverage shall be evaluated at minimum using:

### SYS.4

- Architecture element coverage
- Interface coverage
- Integration step coverage
- Interface requirement coverage

### SYS.5

- System requirement coverage
- Safety requirement coverage
- Customer requirement coverage
- Functional coverage

Target:

**Applicable Requirements with Planned Verification = 100%**

Any uncovered requirement shall have documented justification.

---

# 19. Test Prioritization

Tests shall be prioritized based on:

1. Safety criticality
2. Customer importance
3. Functional complexity
4. Change impact
5. Technical risk
6. Defect history
7. Usage frequency
8. Regulatory relevance

Suggested priorities:

| Priority | Description |
|---|---|
| P0 | Safety / release-critical |
| P1 | Major customer functionality |
| P2 | Normal functional behaviour |
| P3 | Low-risk / convenience functionality |

---

# 20. Entry Criteria â€“ SYS.4

SYS.4 testing may begin when:

- System architecture is sufficiently baselined.
- Interface specifications are available.
- Required system elements are available.
- Software build has passed agreed lower-level testing.
- Hardware is available and released for testing.
- HIL/test bench is operational.
- Test cases are reviewed.
- Required test data is available.
- Known limitations are documented.
- Configuration is identifiable.

---

# 21. Exit Criteria â€“ SYS.4

SYS.4 testing is complete when:

- Planned SYS.4 tests are executed.
- Critical interfaces are verified.
- Required integration coverage is achieved.
- No release-blocking integration defect remains open.
- Failed tests are evaluated.
- Regression testing is completed.
- Deviations are documented.
- SYS.4 test report is completed.
- Integrated system is accepted for SYS.5 testing.

---

# 22. Entry Criteria â€“ SYS.5

SYS.5 testing may begin when:

- SYS.4 exit criteria are fulfilled.
- System requirements baseline is available.
- Qualification test cases are reviewed.
- Test environment is validated.
- Testable system release is available.
- Known limitations are documented.
- Required calibrations are available.
- Relevant safety mechanisms are implemented.
- Defect level is within agreed acceptance criteria.

---

# 23. Exit Criteria â€“ SYS.5

SYS.5 is considered complete when:

- All planned qualification tests are executed or dispositioned.
- All applicable system requirements are covered.
- All safety-critical requirements have objective evidence.
- No unacceptable release-blocking defect remains open.
- Regression testing is complete.
- Failed tests are analysed.
- Deviations have documented approval.
- Test results are reviewed.
- Final SYS.5 Test Report is released.

---

# 24. Pass / Fail Criteria

A test shall be:

### PASS

When:

- Actual behaviour meets all expected results and acceptance criteria.

### FAIL

When:

- One or more acceptance criteria are violated.

### BLOCKED

When:

- Test cannot be executed due to environment, dependency, defect, or configuration limitation.

### NOT RUN

When:

- Test execution has not started.

### NOT APPLICABLE

When:

- Test is demonstrated to be outside the applicable configuration or scope.

---

# 25. Defect Management

Defects identified during testing shall be logged in the approved problem-resolution system.

Each defect shall contain:

- Defect ID
- Title
- Description
- Test Case ID
- Requirement ID
- Detected software version
- Hardware version
- Environment
- Reproduction steps
- Expected behaviour
- Actual behaviour
- Evidence / logs
- Severity
- Priority
- Responsible owner
- Target resolution
- Verification status

---

# 26. Defect Severity

| Severity | Definition |
|---|---|
| Critical | Safety impact, regulatory impact, system unavailable |
| High | Major function unavailable or incorrect |
| Medium | Functional issue with workaround |
| Low | Minor behaviour without significant functional impact |

Project-specific release criteria shall define the acceptable number of open defects by severity.

---

# 27. Regression Testing Strategy

Regression tests shall be selected based on change impact.

Regression shall consider changes in:

- System requirements
- Architecture
- Software
- Hardware
- Calibration
- Communication matrix
- Diagnostic specification
- Test environment

Regression suite categories:

- Smoke tests
- Critical functional tests
- Safety regression tests
- Interface regression tests
- Full regression tests

---

# 28. Change Impact Analysis

For every relevant change, the impact shall be evaluated on:

- Requirements
- Architecture
- Interfaces
- Existing tests
- Test environment
- Safety requirements
- Customer requirements
- Regression scope

Affected tests shall be identified and re-executed.

---

# 29. Test Automation Strategy

Tests shall be automated where technically and economically appropriate.

Priority candidates for automation:

- Repetitive regression tests
- Communication tests
- Diagnostics
- Boundary tests
- Fault injection
- Interface verification
- Safety mechanism verification
- Variant testing

Automated tests shall provide:

- Reproducible execution
- Automatic verdict generation
- Timestamped results
- Evidence/log storage
- Software/configuration identification

---

# 30. CI/CT Integration

Where continuous testing is implemented:

Software Build  
â†“  
Deployment to HIL  
â†“  
Smoke Test  
â†“  
Regression Selection  
â†“  
Automated Execution  
â†“  
Automatic Result Analysis  
â†“  
Report Generation  
â†“  
Defect / Dashboard Update

Typical execution triggers:

- New software integration
- Nightly build
- Weekly integration build
- Release candidate
- Critical change

---

# 31. Configuration Management

The following items shall be controlled:

- Software
- Hardware
- Calibration
- Test scripts
- Test cases
- Test data
- HIL configuration
- Plant models
- DBC files
- Diagnostic files
- Test reports

Each test result shall allow reconstruction of the tested configuration.

---

# 32. Variant Management

Applicable product variants shall be identified.

Example:

| Variant | HW | SW | Vehicle | SYS.4 | SYS.5 |
|---|---|---|---|---|---|
| Variant A | HW01 | SW1.x | Truck | Yes | Yes |
| Variant B | HW01 | SW1.x | Bus | Yes | Yes |
| Variant C | HW02 | SW2.x | Trailer | Yes | Yes |

Variant equivalence may be used only with documented technical justification.

---

# 33. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| V&V Lead | Overall test planning and delivery |
| SYS.4 Test Engineer | Integration test design/execution |
| SYS.5 Test Engineer | Qualification test design/execution |
| System Engineer | Requirement clarification |
| System Architect | Architecture/interface clarification |
| Software Team | Defect analysis and correction |
| Hardware Team | Hardware defect analysis |
| Functional Safety Engineer | Safety requirement verification |
| Test Automation Engineer | Automated test development |
| Configuration Manager | Baseline/configuration management |
| Project Manager | Project-level escalation |
| Quality Engineer | Process compliance / QA |

---

# 34. Review Strategy

The following work products shall undergo review:

- Test Plan
- Test Specification
- Test Cases
- Test Scripts
- Test Results
- Traceability Report
- Test Summary Report

Review shall consider:

- Correctness
- Completeness
- Consistency
- Testability
- Traceability
- Requirement coverage
- Acceptance criteria

---

# 35. Test Evidence

Test evidence shall contain, where applicable:

- Test execution logs
- CAN traces
- Measurement files
- Screenshots
- Diagnostic logs
- Automation logs
- Plots
- Vehicle logs
- HIL logs
- Video evidence
- Test reports

Evidence shall be linked to the applicable test execution.

---

# 36. Test Metrics

The following metrics shall be monitored.

### Planning

- Planned test cases
- Test case design progress
- Requirement coverage

### Execution

- Tests executed
- Tests passed
- Tests failed
- Tests blocked
- Tests not run

### Quality

- Defects detected
- Defects by severity
- Defect closure rate
- Defect leakage
- Reopened defects

### Automation

- Automated test percentage
- Automated regression coverage
- Automation success rate

---

# 37. Suggested Dashboard

| KPI | Target | Actual | Status |
|---|---:|---:|---|
| Requirements covered | 100% | [%] | [R/A/G] |
| Test design completion | 100% | [%] | [R/A/G] |
| Test execution completion | 100% | [%] | [R/A/G] |
| Pass rate | â‰¥ [Target]% | [%] | [R/A/G] |
| P0 defects open | 0 | [#] | [R/A/G] |
| P1 defects open | â‰¤ [Target] | [#] | [R/A/G] |
| Regression completion | 100% | [%] | [R/A/G] |
| Automation coverage | â‰¥ [Target]% | [%] | [R/A/G] |

---

# 38. Test Schedule

| Activity | Start | End | Owner |
|---|---|---|---|
| Test planning | [Date] | [Date] | [Owner] |
| SYS.4 test design | [Date] | [Date] | [Owner] |
| SYS.4 test execution | [Date] | [Date] | [Owner] |
| SYS.4 regression | [Date] | [Date] | [Owner] |
| SYS.5 test design | [Date] | [Date] | [Owner] |
| SYS.5 execution | [Date] | [Date] | [Owner] |
| SYS.5 regression | [Date] | [Date] | [Owner] |
| Final reporting | [Date] | [Date] | [Owner] |

---

# 39. Risks and Mitigation

| Risk | Impact | Probability | Mitigation | Owner |
|---|---|---|---|---|
| Late software delivery | High | Medium | Incremental testing | [Owner] |
| HIL unavailable | High | Low | Backup environment | [Owner] |
| Requirement instability | High | Medium | Baseline/change control | [Owner] |
| Test automation failure | Medium | Medium | Manual fallback | [Owner] |
| Missing interfaces | High | Medium | Early architecture review | [Owner] |
| Hardware shortage | High | Low | Prototype planning | [Owner] |

---

# 40. Assumptions

Examples:

- System requirements are baselined before SYS.5 execution.
- Software components have completed applicable SWE.6 testing.
- Test environments represent the intended vehicle/system sufficiently.
- Required customer specifications are available.
- Required hardware is available according to project schedule.

Project-specific assumptions:

[Insert assumptions]

---

# 41. Dependencies

Dependencies include:

- System requirements maturity
- Architecture maturity
- Software delivery
- Hardware availability
- Test bench availability
- Vehicle availability
- Customer input
- Calibration availability
- External ECU availability

---

# 42. Deviations

Any deviation from this Test Plan shall be documented.

Deviation shall include:

- Deviation description
- Reason
- Impact assessment
- Risk assessment
- Compensating action
- Responsible person
- Approval

---

# 43. Deliverables

## SYS.4 Deliverables

- SYS.4 Test Plan / Strategy
- Integration Test Specification
- Integration Test Cases
- Automated Test Scripts
- Integration Test Results
- Traceability Report
- Integration Test Summary Report

## SYS.5 Deliverables

- SYS.5 Test Specification
- System Qualification Test Cases
- Test Scripts
- Qualification Test Results
- Requirements Coverage Report
- Defect Summary
- Qualification Test Summary Report

---

# 44. Release Recommendation

The V&V team shall provide one of the following recommendations:

### RECOMMENDED FOR RELEASE

All mandatory acceptance criteria are satisfied.

### CONDITIONALLY RECOMMENDED

Open issues exist but are assessed and formally accepted.

### NOT RECOMMENDED

One or more release-blocking criteria are not fulfilled.

---

# 45. Final Test Summary

The final SYS.4/SYS.5 report shall summarize:

- Tested configuration
- Test scope
- Requirements coverage
- Test execution status
- Pass/fail status
- Open defects
- Deviations
- Known limitations
- Residual risks
- Regression status
- Release recommendation

---

# 46. Approval

| Role | Name | Approval | Date |
|---|---|---|---|
| V&V Lead | | | |
| System Engineering Lead | | | |
| Functional Safety | | | |
| Quality | | | |
| Project Manager | | | |

---

# Appendix A â€“ SYS.4 / SYS.5 Separation Guide

| Area | SYS.4 | SYS.5 |
|---|---|---|
| Main focus | Integration correctness | System requirement fulfilment |
| Primary input | System architecture | System requirements |
| Interfaces | Major focus | Verified through system behaviour |
| Element interaction | Major focus | End-to-end behaviour |
| Requirement-based tests | Integration/interface requirements | System requirements |
| Typical environment | HIL / Bench | HIL / Vehicle |
| Fault testing | Integration/error propagation | Requirement/safety behaviour |
| Main evidence | Integration test results | Qualification test results |

---

# Appendix B â€“ Recommended Traceability Structure

## SYS.4

Architecture Element  
â†’ Interface / Integration Requirement  
â†’ SYS.4 Test Case  
â†’ Test Script  
â†’ Test Execution  
â†’ Test Result  
â†’ Defect, if applicable

## SYS.5

Customer Requirement  
â†’ System Requirement  
â†’ SYS.5 Test Case  
â†’ Test Script  
â†’ Test Execution  
â†’ Test Result  
â†’ Defect, if applicable

---

# Appendix C â€“ Recommended Test Case Naming Convention

## SYS.4

`SYS4_<Subsystem>_<Interface>_<TestObjective>_<Sequence>`

Example:

`SYS4_ECU_CAN_WheelSpeedTimeout_001`

## SYS.5

`SYS5_<Feature>_<RequirementFunction>_<Scenario>_<Sequence>`

Example:

`SYS5_ABS_WheelSlipControl_HighMu_001`

---

# Appendix D â€“ Minimum ASPICE-Oriented Evidence Set

For an Automotive SPICE assessment, the following evidence should be readily retrievable:

## SYS.4

- Integration strategy
- Integration sequence
- Integration criteria
- Integration test specification
- Test cases
- Interface/architecture traceability
- Test execution evidence
- Test results
- Defects
- Regression evidence
- Test summary

## SYS.5

- Qualification test strategy
- Qualification test specification
- Requirements-to-test traceability
- Test cases
- Test execution evidence
- Test results
- Defect evidence
- Regression evidence
- Requirements coverage
- Qualification test summary

The combination of these work products should demonstrate:

**Strategy â†’ Specification â†’ Traceability â†’ Execution â†’ Evaluation â†’ Reporting â†’ Closure**
